Hacemos ping a la máquina para probar que tenemos conexión. Miraremos que puertos tiene abiertos con nmap. 
![f56a5e4dd43696f029a3ee2168c60402.png](img/f56a5e4dd43696f029a3ee2168c60402.png)

Vemos el 22 y el 80. Vamos a mirar la página web que esta en el puerto 80. 

![a1843cbea0dc72dd0425880225630d39.png](img/a1843cbea0dc72dd0425880225630d39.png)

Vamos a probar a hacer un fuzzeo a ver si vemos algún directorio que nos interese. 


Vamos por partes, primero vamos a mirar la página inicial a ver si podemos encontrar algo.

El post que sale en la página nos aparece posteado por meliodas. Este es un posible usuario. 

![f2f543be685f861ea83941bc7ae3fa81.png](img/f2f543be685f861ea83941bc7ae3fa81.png)

Vemos 3 comentarios en la página, por lo que pueden ser 3 usuarios con los que podamos loguearnos en un futuro aunque aún no tenemos nada. 

![3a898fbad470de02dc596f583d3342ae.png](img/3a898fbad470de02dc596f583d3342ae.png)

En images no encontramos nada. 

![d0d7586fb52c4ecc400947a4c4b4a22c.png](img/d0d7586fb52c4ecc400947a4c4b4a22c.png)

En robots.txt nos reenvia al directorio rockyou. 

![a618d43b0621750cba7b55941ddfcffa.png](img/a618d43b0621750cba7b55941ddfcffa.png)

Pero no nos aparece nada
![9d6a208e05ad24d8c7d3b63c8e96c5aa.png](img/9d6a208e05ad24d8c7d3b63c8e96c5aa.png)

Ya lo unico que nos queda es lo siguiente, hemos visto en el nmap que tenia el ssh en el puerto 22 abierto. Por lo que hemos identificado 4 posibles usuarios a los que poder hacerle fuerza bruta para conseguir la contraseña.
Vamos a probar a hacerlo con hydra. 

Comando del hydran --> `hydra -l usuario -P lista_de_contraseñas servicio://IP -V`

Tenemos los siguientes usuarios: meliodas, root, www-data y Anonymous. Vamos a ello, nosotros lo vamos a hacer sin el -V porque si no nos van a salir todos los intentos y no queremos llenar la terminal de intentos fallidos. 

Con el usuario meliodas parece que nos ha encontrado una contraseña: `iloveyou1`
![ffe7c2560355b1e070d170cbcf1b3161.png](img/ffe7c2560355b1e070d170cbcf1b3161.png)

Ya que tenemos usuario y contraseña probamos a conectarnos con ssh: 
![deec2dce04a5622a1d82daac56156d65.png](img/deec2dce04a5622a1d82daac56156d65.png)

Estamos dentro del sistema. Vamos a ver que permisos tiene el usuario. 
Parece que tenemos permisos para ejecutar el archivo bak.py. 
![dc321dc3b0102c913f18404d09f744dd.png](img/dc321dc3b0102c913f18404d09f744dd.png)

Listamos el directorio y vemos dos archivos el bak.py y el user.txt. 
![41c3dd198f15c0934fd0c3c96e98551e.png](img/41c3dd198f15c0934fd0c3c96e98551e.png)

Vamos a ver que hay en user.txt. Vemos la priemra flag. 
![9d6bedaacbf381bc9a2e5f86458a3708.png](img/9d6bedaacbf381bc9a2e5f86458a3708.png)

Vamos a ver el contenido del archivo bak.py. Le he preguntado el uso que hace el python a ChatGPT. 
Nos dice que este script parece estar diseñado para crear una copia de seguridad comprimida de un sitio web alojado en el servidor. 
![c7d6d225d42ab03fa091a220a3f00530.png](img/c7d6d225d42ab03fa091a220a3f00530.png)

Preguntadole a chat como poder modificarlo, debido a que yo no tengo ni idea de como poder cambiarlo. Y nos propone esta solución alterar el python para abrir una terminal con permisos de root. 
![a135886cfa00c056e9895fe76679bc37.png](img/a135886cfa00c056e9895fe76679bc37.png)

Al editar el archivo nos da error debido a que no tenemos permisos.
![c259fec3838a7e5b52712a865e503f7a.png](img/c259fec3838a7e5b52712a865e503f7a.png)
SI nos damos cuenta el archivo esta creado por el root por lo que tendremos que crear uno nosotros con el mismo nombre. Probamos a borrar el archivo pero nos da error de permisos. 
Al ver los permisos del usuario este tiene todos los permisos en su directorio por lo que si utilizamos -f de force con rm funciona. 
![ad1c9a0a2dd2dc9e8eddf801aef5b113.png](img/ad1c9a0a2dd2dc9e8eddf801aef5b113.png)

Ahora crearemos un nuevo Python con el contenido que queremos para generar la terminal. 
![e0bafeb2c8419915b53b2e8d3bf6cfcf.png](img/e0bafeb2c8419915b53b2e8d3bf6cfcf.png)

Vemos que se haya creado el archivo de nuevo y vemos de nuevo los permisos que tenemos:
![5b5c98e2fd1c2d57715a4f1e4599cbde.png](img/5b5c98e2fd1c2d57715a4f1e4599cbde.png)

Por los permisos que tenemos ejecutaremos el python con el comando `sudo /usr/bin/python /home/meliodas/bak.py
` . Vemos que nos ha cambiado la cmd a root: 
![22a8c0396a5e397d04c759d991c20068.png](img/22a8c0396a5e397d04c759d991c20068.png)

Ahora que somos usuarios root podemos ver el directorio root. 
![020cb1e830f33c196e856faac5669df1.png](img/020cb1e830f33c196e856faac5669df1.png)

Vemos que hay un root.txt y vemos el interior del archivo.
![91e29e762000d111ad16264223c35d87.png](img/91e29e762000d111ad16264223c35d87.png)