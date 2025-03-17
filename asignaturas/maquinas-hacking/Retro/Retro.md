# Retro

Esta máquina se supone que es bastante similar a Blaster por lo que vamos a resolverla de la misma manera. 
![f4668ef8d79841a54b18a4db9035dbca.png](img/f4668ef8d79841a54b18a4db9035dbca.png)


Nos carga la misma pagina en le puerto 80 que en el baster.
![d629dacd727629ee1cd8e3bb38a2d1b9.png](img/d629dacd727629ee1cd8e3bb38a2d1b9.png)

Probamos a fuzzear y nos encuentra el directorio retro. 
![6b04ad293206cb20ed573fd26bb70746.png](img/6b04ad293206cb20ed573fd26bb70746.png)

Vemos que si entramos en reto es tambien el mismo directori que en blaster.
![7f9ba5f7b3079dd89d44dcf4cfb4a05c.png](img/7f9ba5f7b3079dd89d44dcf4cfb4a05c.png)

Los post siguen siendo subidos por Wade por lo que intuimos que el usuario va a seguir siendo Wade. 
![02dfe6d0661e7a0df4db0722d15ab70b.png](img/02dfe6d0661e7a0df4db0722d15ab70b.png)

Investigando encontramos este post donde nos dice que ha publicaod un nuevo post en su nuevo blog por lo que vamos a investigar. 
![686596775df8f19a8afbdd12b14d05ec.png](img/686596775df8f19a8afbdd12b14d05ec.png)

Como en Blaster podemos ver a la derecha como aparece una lista de post y abajo del todo un comentario. 
![f967d710a0babda9cf1fe5f27a6bf54e.png](img/f967d710a0babda9cf1fe5f27a6bf54e.png)

Vamos al comentario y como podemos ver igual que en Blaster la contraseña la deja guardada en una respuesta  a su propio comentario para no olvidarse. Por lo que tenemos usuario: wade y contraseña: parzival. 

![f1868ea155906e19e4efeebe6e569f7e.png](img/f1868ea155906e19e4efeebe6e569f7e.png)

Con los credenciales vimos en nmap que tenia el RDP abierto por lo que con Remmina vamos a probar a entrar al equipo. 
![18d1bc27b5a7d2c288a73301b2880f79.png](img/18d1bc27b5a7d2c288a73301b2880f79.png)

**En este momento ha cambiado la IP debido a que la máquina se apagó.**

Nos metemos dentro del sistema. 
![e39786928c7670d627322960a7b2846b.png](img/e39786928c7670d627322960a7b2846b.png)

Vamos a ver que hay en el archivo user.txt. Encontramos la primera flag. 
![1c49473c13c7a28e1af153a7bf102d03.png](img/1c49473c13c7a28e1af153a7bf102d03.png)

En el escritorio nos queda el Chrome y la papelera. Dentro de papelera hemos encontrado el script que utilizamos en Blaster para escalar privilegios.  


![9e228d304b890f8d7a412cc6db9bff49.png](img/9e228d304b890f8d7a412cc6db9bff49.png)

Si vemos el Chrome nos aparece un CVE guardado en los marcadores. 
![0d19f8b6f3ba77d8b18ab78c393904c8.png](img/0d19f8b6f3ba77d8b18ab78c393904c8.png)

Buscamos como explotar el CVE y nos dan estos pasos:
Pasos para explotar CVE-2019-1388
Identificar un programa que active el UAC:
Encuentra un ejecutable firmado que pueda desencadenar el cuadro de diálogo de UAC al ejecutarse como administrador.

Mostrar más detalles:
Cuando aparezca el cuadro de diálogo de UAC, selecciona la opción "Mostrar más detalles".

Ver información del certificado:
Haz clic en "Mostrar información sobre el certificado del editor" dentro del cuadro de detalles.

Abrir el enlace del emisor del certificado:
En la ventana del certificado, haz clic en el enlace proporcionado por el emisor del certificado. Esto abrirá un navegador web con privilegios elevados (NT Authority SYSTEM).

Usar el navegador para abrir el símbolo del sistema:
Una vez que el navegador esté abierto, utiliza la opción "Guardar como" para abrir una ventana del explorador de archivos.

En la barra de direcciones del explorador, escribe la ruta completa al ejecutable cmd.exe ubicado en C:\WINDOWS\system32\cmd.exe.

Presiona Enter y obtendrás una consola con privilegios elevados.
***
Ejecutamos el script y le damos a "Show more datails"
![c5cade0c2b9599ca6da5f920f7c01b5a.png](img/c5cade0c2b9599ca6da5f920f7c01b5a.png)

Le daremos "Show information about the publisher's certificate"
![6f3264ea714fd824a8dc6f674fbe6187.png](img/6f3264ea714fd824a8dc6f674fbe6187.png)

Y le damos a ver el certificado 
![4a604065400e523c1c2233e097a49ba5.png](img/4a604065400e523c1c2233e097a49ba5.png)

Nos abre esta ventana. El problema es que nos abre esta ventana que nos debería dejar abrirlo con un navegador pero no se porque no me deja ninguna opción. 
![b9d082138ae004bdeb0d6f5771fa4337.png](img/b9d082138ae004bdeb0d6f5771fa4337.png)

He buscado en internet pero lo unico que me aparecia era que podia ser un bug del servidor. Preguntando a compañeros de clase me dijeron que había un exploit en este [repositorio](https://github.com/WindowsExploits/Exploits/tree/master/CVE-2017-0213). 

Este lo pasaremos con un servidor de python debido a que no encontramos otra manera de pasarme el exploit. 

Nos descargamos el exploit del repositorio
![17f67a1c6ca89aaf703b07f0e51c8e80.png](img/17f67a1c6ca89aaf703b07f0e51c8e80.png)

Encenderemos el servidor python 
![e958c09a6700e9e94fdf605a77f68517.png](img/e958c09a6700e9e94fdf605a77f68517.png)

Nos conectamos al servidor python desde el servidor de windows y descargamos el exploit
![a07f96fd02a546a499c318f9b90380d1.png](img/a07f96fd02a546a499c318f9b90380d1.png)

Lo tenemos descargado
![c25c32f22eaddc5399a4f6f824151f60.png](img/c25c32f22eaddc5399a4f6f824151f60.png)

Vamos a ejecutarlo

![9970e543b14c7bd08704814c260bf219.png](img/9970e543b14c7bd08704814c260bf219.png)

Y nos abre la cmd
![4f167b45df1a729a20f85f5901d45600.png](img/4f167b45df1a729a20f85f5901d45600.png)

Comprobamos que somos el usuario sistema

![d194ec9e408388adda5264556c43b866.png](img/d194ec9e408388adda5264556c43b866.png)

Buscaremos ahora que tenemos permisos de administrador, la flag que nos falta en el directorio del Administrador. 

![259f0a216595ffd8dc807d5340b81fca.png](img/259f0a216595ffd8dc807d5340b81fca.png)

En el escritorio del administrador vemos el archivo root.txt
![a3c532f729b8ea67d955be1f1348caf9.png](img/a3c532f729b8ea67d955be1f1348caf9.png)

Miramos la flag. 
![4b39889e9e79c296e3ef93d257c528a3.png](img/4b39889e9e79c296e3ef93d257c528a3.png)