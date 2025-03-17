# Ice

Lo primero que haremos sera un Nmap para ver que puertos tiene abierto la máquina. 

![7547287471c1b5bcfd0043665915bb9d.png](img/7547287471c1b5bcfd0043665915bb9d.png)

AÑadiendo a nmap -sV -O nos dirá la versión de los servicios y sus sistema operativo. Vemos que hay en el puerto 8000 de http un servicio llamado Icecast. 

![49197f9cfea9c5967de8819173552a0b.png](img/49197f9cfea9c5967de8819173552a0b.png)

Con -sC  podemos ver entre otras cosas el nombre que tiene el ordenador

![4babac44fd7759f5aa62a2efcbf2029d.png](img/4babac44fd7759f5aa62a2efcbf2029d.png)

Buscaremos Icecast en [https://www.cvedetails.com](https://www.cvedetails.com) para ver su nivel de impacto. 

![875b9ee07e8a7770b9b27b58ceaa9fd2.png](img/875b9ee07e8a7770b9b27b58ceaa9fd2.png)

Vemos que tiene una nota de 6.4 de score. 

![cefe84083e4ba36c8b0cf703518a5c2d.png](img/cefe84083e4ba36c8b0cf703518a5c2d.png)

Si buscamos la versión de icecast encontramso su CVE --> 2004 -1561 

https://www.exploit-db.com/exploits/568

![1767e9aea50f8f1092406b5e6c3e18eb.png](img/1767e9aea50f8f1092406b5e6c3e18eb.png)


Una vez hemos localizado el CVE de Icecast vamos a utilizar metaexploit para buscar posibles exploit. 

![e669dec15d316e9d575ca94a83ddab4f.png](img/e669dec15d316e9d575ca94a83ddab4f.png)

Encontramos uno y lo usamos. 

![a92564c17f0d86c49cf40803a1f77c1c.png](img/a92564c17f0d86c49cf40803a1f77c1c.png)

Editaremos las opciones del exploit. 

![e662ab14db7443e19686bc8c040cd253.png](img/e662ab14db7443e19686bc8c040cd253.png)

Una vez configurada ejecutaremos el exploit. Esto creará una sesión la cuál es una consola remota en el dispositivo objetivo.

![35e1e959ef8ea09b7968b1b482093d1a.png](img/35e1e959ef8ea09b7968b1b482093d1a.png)


COmprobamos que usuarios somos y que arquitectura tiene el SO. Dejaremos la sesión en segundo plano. 
![945c658bbf627585aa4ac417a8a7f3d0.png](img/945c658bbf627585aa4ac417a8a7f3d0.png)

Vamos a ejecutar ahora un exploit para poder escalar privilegios en la sesión que hemos iniciado anteriormente. Buscamos el exploit que nos dice THM y seleccionamos el primero. 

![de3edcc96c4a25ce96f673bdfb42e8ae.png](img/de3edcc96c4a25ce96f673bdfb42e8ae.png)

![b8e38847efe622fb90805697d69f0e4c.png](img/b8e38847efe622fb90805697d69f0e4c.png)

Vemos que opciones tiene para configurar el exploit. 
![139ffc7530edc8d8d2ca4dfc03fa8041.png](img/139ffc7530edc8d8d2ca4dfc03fa8041.png)

Modificaremos SESSION y LHOST. 
![0b0b08604399ea35c6b1ba4c6127f3e0.png](img/0b0b08604399ea35c6b1ba4c6127f3e0.png)

Una vez configurado ejecutamos el exploit. Esto debería de abrirnos la sesión qu ecreamos antes pero con escala de privilegios.
![0d10b0eae5df0c0a617288b06b5bc358.png](img/0d10b0eae5df0c0a617288b06b5bc358.png)

Vemos que privilegios tenemos en la consola. Vemos que tenemos SeTakeOwnershipPrivilege, este permiso otorga control total en todos los arhcivos del sistema pudiendo escribir en ellos o editarlos. 
![8e48992030791937509dbe309b45591a.png](img/8e48992030791937509dbe309b45591a.png)

Listamos los servicios que están activos en el sistema. 

![bd23ffa0b07447d302b848e40bf23e2f.png](img/bd23ffa0b07447d302b848e40bf23e2f.png)

ELegimos un proceso que este ejecutandose por el sistema es decir por NT AUTHORITY\SYSTEM con los que poder ser ese usuario. 
![1139216b1c3ae986fc3d979bde43f44f.png](img/1139216b1c3ae986fc3d979bde43f44f.png)

Con migrate -N seleccionamos el proceso a ejecutar. 
![80cf0180da529b1d09b78ee4393518b7.png](img/80cf0180da529b1d09b78ee4393518b7.png)

Una vez migrado veremos si hemso cambiado de usuario. Efectivamente somos T AUTHORITY\SYSTEM
![b684ac224804353b9d75f0dce765d117.png](img/b684ac224804353b9d75f0dce765d117.png)

Cargaremos la herramienta kiwi en meterpreter, la cuál nos proporciona numerosos comandos. 
![e0047364e35b581180c105bdcaf8ddb9.png](img/e0047364e35b581180c105bdcaf8ddb9.png)

Con creeds_all podemos ver los credenciales parseados. 
![2df8c72cde75f1f4a34085bc27c43dee.png](img/2df8c72cde75f1f4a34085bc27c43dee.png)
Vemos como encuentra los credenciales del usuario Dark es Password01!

![9f67985f3bc0efd651b205cfe9653389.png](img/9f67985f3bc0efd651b205cfe9653389.png)

Con el comando hashdump podemos extraer los hashes de las contraseñas de los usuarios de un sistema.

![81081b6136600f1c6298e5d26b32bde3.png](img/81081b6136600f1c6298e5d26b32bde3.png)

Con el screenshare nos permite transmitir en tiempo real la pantalla del sistema

![27af5fee9f157464b6cd1a3ff9651144.png](img/27af5fee9f157464b6cd1a3ff9651144.png)

Con record_mic permite grabar audio a través del micrófono del sistema
![7ccd9cf46ce687049e6b1f5000977cc2.png](img/7ccd9cf46ce687049e6b1f5000977cc2.png)

Con timestomp permite modificar los atributos de tiempo de los archivos en un sistema

![255963a2d5eefad99dc03fb1736f7142.png](img/255963a2d5eefad99dc03fb1736f7142.png)

Con golden_tiket_create permite generar un ticket Kerberos dorado
![6cc4532f8e223e5d2285442ccc74a569.png](img/6cc4532f8e223e5d2285442ccc74a569.png)

Este exploit permite habilitar el servicio de RDP en la máquina que estamos atacando.

![c9dcb38d67d5febb840a2c0b660ee56f.png](img/c9dcb38d67d5febb840a2c0b660ee56f.png)