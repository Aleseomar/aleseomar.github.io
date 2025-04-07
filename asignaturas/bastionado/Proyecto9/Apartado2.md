# Apartado 2

## Instalación y comprobación del servidor web

Como hemos dicho anteriormente vamos a realizar la instalación del servicio web en la misma máquina del apartado1.

![alt text](img/image11.png)

Actualizamos los respositorios de la máquina.

![alt text](img/image9.png)

Una vez actualizados procedemos a instalar apache en nuestro Amazon Linux. Este paquete en esta SO se llama `httpd`.

![alt text](img/image12.png)

Una vez instalado procedemos a activar el servicio y comprobar que esta activo.

![alt text](img/image13.png)

## Activación firewall de AWS

Para poder acceder desde fuera de la instancia al servidor web deberemos activar las reglas de entrada de nuestra instancia las cuales nos permiten entrar desde fuera a los puertos del servicio web.

Para poder acceder a las reglas de entrada tendremos que irnos a la información de la instancia.

![alt text](img/image14.png)

Entraremos en la pestaña de `Seguridad`.
Aquí podemos ver las reglas que tenemos de entrada y salida. Para poder configurarlas pincharemos en "Grupos de seguridad".

![alt text](img/image15.png)

Una vez aquí podemos ver como nos aparecen las reglas de entrada. Para agregar las reglas que queremos le daremos a "Editar reglas de entrada".

![alt text](img/image17.png)

Dentro nos aparecerá el botón "Agregar regla". Aparte nos aparece la regla que ya esta creada que permite la conexión SSH.

![alt text](img/image16.png)

Al ser un servicio web tendremos que activar reglas para el puerto 80 (HTTP) y 443 (HTTPS). En el apartado de origen pondremos 0.0.0.0/0 (todas las IPs). Una vez acabado le daremos a "Guardar reglas".

![alt text](img/image18.png)

Y ya hemos añadido las dos reglas de entrada.

![alt text](img/image19.png)

Podemos ver como si nos metemos al servicio web en el puerto 80 nos aparece correctamente funcionando.

![alt text](img/image20.png)

Si nos conectamos al puerto 443 o HTTPS vemos que no nos funciona debido a que no tenemos un certificado.

![alt text](img/image21.png)

## Configuración HTTPS

Para el HTTPS nos hace falta registrar un nombre de dominio que apunte a la IP de nuestra instancia y generar nuestro propio certificado dentro del ssistema.

### Resgistrar nombre de dominio

Preguntandole a Perplexity sitios donde poder resgitrar un nombre de dominio gratis que apunte a la IP de nuestra instancia nos recomendo 2 sitios: DuckDNS y NoIP.

Hemos escogido NoIP debido a que tiene interfaz online y es bastante fácil de usar mientras al entrar en la web de DuckDNS había que instalar una aplicación para poder hacerlo.

Hemos generado el siguinete nombre DNS.

![alt text](img/image22.png)

### Generar nuestro propio certificado

Haciendo una búsqueda nos recomiendan Certbot para generar certificados.

Lo primero que haremos será intalar los paquetes y dependencias de apache.

![alt text](img/image23.png)

Crearemos el archivo de configuración para el dominio y metemos la configuración. 

![alt text](img/image24.png)

![alt text](img/image25.png)

Una vez configurado el archivo ejecutamos el comando para generar el certificado. Este nos da un error de que ya hay un certificado en uso que es el de localhost, por lo que tendremos que acceder al archivo y comentar 2 lineas. 

![alt text](img/image26.png)
![alt text](img/image27.png)

Comentamos estas dos lineas para que no utilice ese certificado.
![alt text](img/image28.png)
![alt text](img/image29.png)

Y volvemos a ejecutar el comando de antes forzando a que renueve el certificado.

![alt text](img/image30.png)

Nos pedirá que respondamos a algunas preguntas.

![alt text](img/image31.png)

Comprobamos que este la configuración correcta

![alt text](img/image32.png)

También vamos a crear un archivo de apache para el HTTPS. 

![alt text](img/image33.png)

Le añadiremos los parametros de configuración en relación a nuestro nombre de dominio. 

![alt text](img/image34.png)

Una vez reiniciemos el servicio ya podremos conectarnos a nuestro servidor web a través del nombre de dominio que hemos creado.

![alt text](img/image35.png)

Podemos comporbar que nos detecta el certificado y que lo valida el navegador.

![alt text](img/image36.png)


### Comprobación certificado propio vs certificado otra página

Aquí podemos ver los detalles del certificado que hemos creado.
![alt text](img/image37.png)

![alt text](img/image38.png)

Y aquí podemos ver los detalles del certificado que tiene la gitpage del proyecto 9 de bastionados.

![alt text](img/image39.png)

![alt text](img/image40.png)

Como podemos ver podemos comparar diferentes parametros que salen diferentes:

- Nombre común (CN): E5 vs Sectigo ECC Domain Validation Secure Server CA

- Organización (O): Let's Encrypt vs Sectigo Limited

- Diás para vencimiento: 3 meses vs 1 año

- Algoritmo de firma de certificado: Firma X9.62 ECDSA con SHA-384 vs Firma X9.62 ECDSA con SHA-256