# Blaster

Lo primero que haremos probar la conectividad  máquina, pero vemos que no nos hace ping ni nmap. 

![eaed601fb4fae9b400961643f7f3c5d5.png](img/eaed601fb4fae9b400961643f7f3c5d5.png)

Como nmap lo primero que hace es un ping y hemos visto que no nos deja, usaremos las opciones -Pn para que se salte el ping y nos haga el nmap. Vemos que esta activo el puerto 80 por lo que puede haber una página web. 

![71f84cec090e4e8a6c3fbe38f917f098.png](img/71f84cec090e4e8a6c3fbe38f917f098.png)

POnemos la IP de la máquina en el buscador y nos conectamos a la máquina. 
 
 ![6976333d792c32f4dac45991b67c9b2b.png](img/6976333d792c32f4dac45991b67c9b2b.png)

 Vamos a hacer un fuzzeo de la web a ver si encontramos algún directorio interesante con gobuster. Nos localiza el directorio /retro/
 
![866d5d7788c022fb957f70b5c9bc5756.png](img/866d5d7788c022fb957f70b5c9bc5756.png)

Entramos al directorio y nos mete en lo que parece un foro.
 
![54ee495297382b8b7cd6e7e66b4dfa3c.png](img/54ee495297382b8b7cd6e7e66b4dfa3c.png)

Vemos varios post del usuario Wade. 
 
 ![301af22f979b31acb8d76f4530b92d22.png](img/301af22f979b31acb8d76f4530b92d22.png)
 ![822ecd71516f4e8c22ae96c0ba6900ee.png](img/822ecd71516f4e8c22ae96c0ba6900ee.png)
 
 En los post recientes vemos un apartado de comentarios recientes. THM nos dice que ahí podemos encontrar información relevante. 
 
 ![74e50a805646889259a40d55fb54f2f4.png](img/74e50a805646889259a40d55fb54f2f4.png)
 
 
 Viendo el comentario podemos que habla que su usuario de sesión será Wade. 
 ![d8d5f246bd57d1c8e8d91765b04bc409.png](img/d8d5f246bd57d1c8e8d91765b04bc409.png)

Se responde a si mismo en un comentario donde deja la contraseña del usuario por su se le olvida. 
 
 ![45c940250f94a22b0e652ea7f1d6ad03.png](img/45c940250f94a22b0e652ea7f1d6ad03.png)

Vamos a probar a conectarnos al sistema operativo a través de RDP ya que en el nmap vimos que estaba el puerto abierto. Probaremos a entrar con los credenciales que hemso encontrado.
Usaremos remmina para el RDP.

![feed11af0e51552995381f3a9adb6d93.png](img/feed11af0e51552995381f3a9adb6d93.png)

Crearemos una nueva sesión con los datos que tenemos. 

![82db0be28bbf23b454f753f5b5ec3f45.png](img/82db0be28bbf23b454f753f5b5ec3f45.png)

Y ya estamos dentro de la máquina. 

![88f48e772ad20887da6abb5e7c8bb485.png](img/88f48e772ad20887da6abb5e7c8bb485.png)

Vemos que hay un archivo user.txt en el escritorio donde encontramos una flag. 

![32c40b4554d857f7e7eeffbe39be8939.png](img/32c40b4554d857f7e7eeffbe39be8939.png)  

Flag: THM{HACK_PLAYER_ONE}

Nos dicen que encontremos el CVE que ha buscado el usuario en el historial de explorer. Al parecer no se si es un bug o algo pero no nos aparece nada ni en el histroial ni en los archivos del historial.

En THM nos dicen la solución por lo que vamos a coger la respuesta de ahí.

![32ee56174df60734ad5d8b0181994783.png](img/32ee56174df60734ad5d8b0181994783.png)

![9e1c804f0577ba64acb8d5f7e41d0e5e.png](img/9e1c804f0577ba64acb8d5f7e41d0e5e.png)

CVE-2019-1388

En el escritorio vemos un archivo hhupd. En THM nos dan un vieo con el que ejecutar un exploit.  

![29ead192c71b94c7ddf9006fd0f0d94f.png](img/29ead192c71b94c7ddf9006fd0f0d94f.png)

Video: https://www.youtube.com/watch?v=3BQKpPNlTSo

Ejecutamos el script y le damos a "Show more details"

![a29b253216d064e5c470b785c20df612.png](img/a29b253216d064e5c470b785c20df612.png)

Clickaremos en "Show info about teh publisher's certificate" 

![9cbfea0e7f1fe388df04c286cc0d5c2d.png](img/9cbfea0e7f1fe388df04c286cc0d5c2d.png)

Nos carga el certificado y le damos al enlace que nos aparece en Issued by. 
![da019aaf98df1815520e64391e892ce0.png](img/da019aaf98df1815520e64391e892ce0.png)

Al pinchar nos abre explorer una página pero no nos carga. 

![49d31c4b0576b826dd85a1f981946471.png](img/49d31c4b0576b826dd85a1f981946471.png)

Guardaremos la página como un archivo.

![275ef917502d171c22dbae3899b77d19.png](img/275ef917502d171c22dbae3899b77d19.png)


Buscamos la ruta donde se encuentra la cmd.


![0abdd274c95e6cedc8aaed2eb3372843.png](img/0abdd274c95e6cedc8aaed2eb3372843.png)

Aquí podemos verla

![e3a1717c9279dad5d9dc3edb0bf8602a.png](img/e3a1717c9279dad5d9dc3edb0bf8602a.png)

Le daremos click y lo abriremos con la terminal. 

![bcfbef7d2934a1293b343b84f195d7f8.png](img/bcfbef7d2934a1293b343b84f195d7f8.png)

![6180c52fa763fb508809ce6e61af4cbf.png](img/6180c52fa763fb508809ce6e61af4cbf.png)

Vamos a verificar que usuario somos. El exploit que hemos ejecutado nos ha permitido abrir la cmd como usuario sistema con loq ue tenemos permisos administrador.

![2b4d1b0302857876a88344aa0e5a8c1e.png](img/2b4d1b0302857876a88344aa0e5a8c1e.png)

Ahora nos dicen que busquemos la flag en de root.txt del directorio en la carpeta del Administrador.

![f2fe5ff16f63b72cb8d3c7fbc91f6e11.png](img/f2fe5ff16f63b72cb8d3c7fbc91f6e11.png)

En el directorio Desktop vemos el archivo que se nos menciona.

![1f45b8c1106ddfce11ae5c6d6d97d7ea.png](img/1f45b8c1106ddfce11ae5c6d6d97d7ea.png)

Vemos el contenido del fichero para encontrar la flag.

![bb0cfb26db388c1aaaf6a150a1e74498.png](img/bb0cfb26db388c1aaaf6a150a1e74498.png)

Flag: THM{COIN_OPERATED_EXPLOITATION}

Nos dicen que no cerremos la sesión de la consola. Nos proporcionan el siguiente exploit `exploit/multi/script/web_delivery`, así que lo buscaremos en metaexploit. 

![747c3d35d66cd4ccac0401ab984818da.png](img/747c3d35d66cd4ccac0401ab984818da.png)

Seleccionaremos el primer exploit.

![35a94cf747e0b90c3174a31b46ef10ec.png](img/35a94cf747e0b90c3174a31b46ef10ec.png)

Vemos las opciones de configuración del exploit

![b6dc36363445f3ff2cbb87ed089db96b.png](img/b6dc36363445f3ff2cbb87ed089db96b.png)

Vemos como nos aparece la opción target.

![b76d7b2fec2b6043070fc808c7de2dc4.png](img/b76d7b2fec2b6043070fc808c7de2dc4.png)

Como vemos arriba la opción por defecto es Python, nosotros escogeremos la opción PSH que es la de PowerShell.

![bf4c143f6da7b2a5df69000ec76b7511.png](img/bf4c143f6da7b2a5df69000ec76b7511.png)

Por lo que seleccionaremos el target 2. 
![6656370459a2c39b3ff6321bdbee52b7.png](img/6656370459a2c39b3ff6321bdbee52b7.png)

Configuramos LHOST. 
![0cdb9323d934455534fb3746057c3fee.png](img/0cdb9323d934455534fb3746057c3fee.png)

Configuramos el payload con la reserse shell de meterpreter.
![a7d6dd370ee4efe2fcf4ce80321cdae6.png](img/a7d6dd370ee4efe2fcf4ce80321cdae6.png)

Y ejecutamos el exploit. Como podemos ver nis aparece un comando que deberemos de ejecutarlo en la cmd del Windows.
![b3c7cc12f855dc69f9ca313414a4e3d7.png](img/b3c7cc12f855dc69f9ca313414a4e3d7.png)

Copiamos el comando que nos dio el exploit en la cmd.
![c3abbbbfd26da2e8d966b4480333a96c.png](img/c3abbbbfd26da2e8d966b4480333a96c.png)

Y ya estariamos dentro del sistema operativo a través de meterpreter. 

![12b3f94ffc5b051eec0c69147b327d52.png](img/12b3f94ffc5b051eec0c69147b327d52.png)
