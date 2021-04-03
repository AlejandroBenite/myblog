---
typora-root-url: ../../
typora-copy-images-to ../imagenes/autenticacion2
layout: post
title: "Práctica: Autenticación 2"
categories: jekyll update
---
AUTENTICACIÓN. PASSWORDBASICAUTH.

En el fichero dockerfile, añadimos una línea para crear el directorio que vamos a proteger, en la ruta /var/www/html, le cambiamos el propietario y los permisos a la carpeta.

![1](/myblog/imagenes/autenticacion2/1.png)

En este fichero también crearemos las credenciales para que los usuarios puedan acceder a este directorio protegido. Para ello, se crea un fichero con el nombre htpasswd y se mueve dentro de /etc/apache.

![2](/myblog/imagenes/autenticacion2/2.png)

En el fichero 000-default.conf, que se puede copiar desde /etc/apache2/sites-enabled/, añadimos el siguiente código:

![3](/myblog/imagenes/autenticacion2/3.png)

Al final, en la carpeta contaremos con estos ficheros:

![4](/myblog/imagenes/autenticacion2/4.png)

El 000-default.conf, los scripts para el contenedor docker, el archivo dockerfile y el php.conf, que podemos copiar de /etc/apache2.

Ejecutamos el build.sh y seguidamente el run.sh. Desde el navegador entramos en la dirección 127.0.0.1 con el puerto que hayamos especificado en los scripts y el nombre del directorio. Debe aparecer un cuadro en el que se pide el usuario y la contraseña.

![5](/myblog/imagenes/autenticacion2/5.png)

Al introducir las credenciales accedemos al directorio que, en este caso, está vacío.

![6](/myblog/imagenes/autenticacion2/6.png)