# Anthem

Lo primero que haremos será hacerle un nmap a la máquina. 
Antes hemos comprobado si nos hacía ping a la máquna y vemos que no.

![545acec2a18c44e9cef3ba35f14e3ba3.png](img/545acec2a18c44e9cef3ba35f14e3ba3.png)

Debido a esto haremos nmap con -Pn. 

![610cebc4feb450c11d3974a8dbffeb05.png](img/610cebc4feb450c11d3974a8dbffeb05.png)

Podemos ver 2 puertos el 80 que será una página web y el 3389 el cuaĺ es el puerto del RDP de WIndows. 

Vamos a entrar en la web.

![e29ad70ebdd0cbd6f1d0eb53fc8e18b3.png](img/e29ad70ebdd0cbd6f1d0eb53fc8e18b3.png)

Nos apararecen 2 artículos en el blog. Vamos a entrar en los dos a ver si podemos encontrar algo. 
Hemos estado investigando y en uno de los post hay un comentario de un usuario. 

![632d39d6f7c502b3adecc230ace7dd1c.png](img/632d39d6f7c502b3adecc230ace7dd1c.png)


Y encontramos una flag debajo del titulo de un post que subió. 

![60132dd4cab0305f43d74093088e601c.png](img/60132dd4cab0305f43d74093088e601c.png)

THM{L0L_WH0_D15}

Viendo el código de la página vemos otra flag comentada. 

![f05102b2197483ecf088f1b6715a7386.png](img/f05102b2197483ecf088f1b6715a7386.png)

THM{G!T_G00D}

Vemos otra en otro encabezado

![d018d2df52f2a302631caa5182b132f1.png](img/d018d2df52f2a302631caa5182b132f1.png)

THM{L0L_WH0_US3S_M3T4}

Vamos a mirar todos los codigos de las páginas por si encontramos alguna otra flag:

En el segundo blog podemos ver en el código una flag que la verdad esta bastante escondida. Le pase el codigo al chat y me detecto la flag. 

![cc384e07097e610e8f25fc149c8f4e55.png](img/cc384e07097e610e8f25fc149c8f4e55.png)

THM{AN0TH3R_M3TA}

Vamos a mirar en los directorios más típicos de las páginas webs. 

- robots.txt

![bb9d21e254d6243721a7df48286ea0f3.png](img/bb9d21e254d6243721a7df48286ea0f3.png)

Nos aparece la siguinete información donde vemos directorios de umbraco. Buscamos que es umbraco y vemos que es un CMS por lo que la página esta creada con este CMS.

![74c731610aace91a142c4661a858bd3f.png](img/74c731610aace91a142c4661a858bd3f.png)

Lo primero que nos sale es UmbracoIsTheBest!, puede ser una contraseña con que vamos a guardarla. 

Ahora vamos a meternos en todos los directorios que nos sale en el robots.txt a ver si encontramos algo. 

No hay nada

![7368f6ee0f3f484b34ce3b9e79df760e.png](img/7368f6ee0f3f484b34ce3b9e79df760e.png)

Solo nos redirige a la página principal

![5976fca7bee80f5c5b693c19dfeb400a.png](img/5976fca7bee80f5c5b693c19dfeb400a.png)

Si accedemos a /umbraco/ nos redirige a lo que parece un login del cms:
![9ef7bf2e7e291cb44a6f05e13cb81e40.png](img/9ef7bf2e7e291cb44a6f05e13cb81e40.png)

Para el login nos pide usuario o correo y contraseña. La contraseña creemos que es la que salia en robots el usuario tendremos que buscar por la web a ver si hay alguna pista. 

Encontramos en un post este correo: 

![23f7f550748f4e01fda2fafeaeb481dd.png](img/23f7f550748f4e01fda2fafeaeb481dd.png)

Nos da error. 

![4a8362b5de27c2e628f84a9b6a8da690.png](img/4a8362b5de27c2e628f84a9b6a8da690.png)

No encuentro nada de ningún correo y he buscado información preguntadole a chat. Me dice que hay concordancia entre el correo que he encontrado y el usuario que ha subido el post. 

![faeb6527eb9c24d3822d3dbd7836b8c1.png](img/faeb6527eb9c24d3822d3dbd7836b8c1.png)

Como vemos el usuario que lo sube se llama Jana Doe y el correo es JD@anthem.com, el correo se forma con las iniciales del usuario.  El tryhackme hay una pregunta que nos decia cuál era el nombre del administrador. 
Buscando un poema que había estaba dedicado al administrador al blog vemos que el creado se llamaba Solomon Grundy por lo que su correo de administrador debería ser igual en cuanto a formato. 

Por esto hemos llegado a que el correo del administrador es **SG@anthem.com**. Vamos a probar a loguearnos ahora.  (Recalco que era demasiado enrevesado y tuve que preguntarle al chat a ver is encontraba alguna manera de hacerlo)

![1efae4a6750aa0ae89c0f65417de10ff.png](img/1efae4a6750aa0ae89c0f65417de10ff.png)

***
Ya que tenemos usuario y contraseña vamos a meternos en el RDP que vimos que tenía abierto el sistema.

![be17c4d44a26d5ef381b3a584be15639.png](img/be17c4d44a26d5ef381b3a584be15639.png)

(el usuario es SG no el correo)

Nos aparece un user.txt con una flag

![22512ff3faed2d55cba898affcf45582.png](img/22512ff3faed2d55cba898affcf45582.png)

THM nos dice que activemos los archivos y documentos ocultos para poder verlos

![d54af8a74ae6cc13531d26b397238d25.png](img/d54af8a74ae6cc13531d26b397238d25.png)

Dentro de backup encontramos un archivo

![ded6e23e560c693fa91a98e57a44d882.png](img/ded6e23e560c693fa91a98e57a44d882.png)

Nos da error de permisos 

![721ebb85809d4e4b002410f8e3bab209.png](img/721ebb85809d4e4b002410f8e3bab209.png)

Vemos los permisos y nos sale que no hay usuario con permisos

![984945e5aa64c303aeabb2d21a1b97f9.png](img/984945e5aa64c303aeabb2d21a1b97f9.png)

Somos el usuario SG por loq ue vamos a darnos permiso.

![fb367fb81f32f5e2f355da2d5c98da23.png](img/fb367fb81f32f5e2f355da2d5c98da23.png)

Nos damos permisos 

![cd99b79b3aa4851e29c190187a31e181.png](img/cd99b79b3aa4851e29c190187a31e181.png)

Y encontramos la flag

![6612d8a0aee78aeb053daa2e836b6215.png](img/6612d8a0aee78aeb053daa2e836b6215.png)