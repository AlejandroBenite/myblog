---
typora-root-url: ../../
typora-copy-images-to ../imagenes/autenticacion1
layout: post
title: "Práctica: Autenticación 1"
categories: jekyll update
---
AUTENTICACIÓN HTTP.

Para este ejercicio se va a utilizar un programa implementado en php para autenticación de usuarios, en este caso el usuario Mario. El programa es el siguiente:

![1](/myblog/imagenes/autenticacion1/1.png)

Además, tendremos un dockerfile donde instalaremos apache2 y php7.3 (procps y telnet no son necesarios).

![3](/myblog/imagenes/autenticacion1/3.png)

Al final, en la carpeta de la práctica estarán los dos ficheros que hemos creado en los pasos anteriores, autenticacion.php y el dockerfile, junto a los scripts build, debug, entrypoint, run, shell y stop.

![2](/myblog/imagenes/autenticacion1/2.png)

Ahora ejecutamos levantamos el contenedor ejecutando primero el build.sh y después el archivo run.sh. Al introducir e ir a la dirección web, se pide un usuario y una contraseña.

![4](/myblog/imagenes/autenticacion1/4.png)

Si no introducimos el usuario 'Mario' con su contraseña, volverá a aparecer el cuadro pidiendo de nuevo las credenciales de acceso. SI introducimos correctamente los parámetros, aparecerá un mensaje de bienvenida en la pantalla.

![5](/myblog/imagenes/autenticacion1/5.png)

