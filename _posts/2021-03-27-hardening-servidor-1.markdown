---
typora-root-url: ../../
typora-copy-images-to ../imagenes/hardening1
layout: post
title: "Práctica 1: Hardening del Servidor"
categories: jekyll update
---
CONFIGURAR APACHE.

Una vez levantado el Apache utilizando Docker, suele venir por defecto activados varios modulos que proporcionan información sobre los directorios y las especificaciones (apartado server de la segunda foto) de la página tal y como vemos en las siguientes imágenes.

![1](/myblog/imagenes/hardening1/1.png)

![2](/myblog/imagenes/hardening1/2.png)

Para que no muestre el índice, únicamente se debe deshabilitar el módulo autoindex. Lo podemos hacer directamente desde el Dockerfile.

![3](/myblog/imagenes/hardening1/3.png)

Ahora, cada vez que entremos en la carpeta public_html, no mostrará ningún tipo de contenido, es más, mostrará un mensaje de que no encuentra nada en el servidor.

![4](/myblog/imagenes/hardening1/4.png)

Eso sí, si accedemos a alguno de los archivos que hay en public_html, si que muestra la página.

![6](/myblog/imagenes/hardening1/6.png)

Para evitar que se muestre información a cerca del servidor, debemos añadir las siguientes líneas en el fichero además de reiniciar el servicio.

![9](/myblog/imagenes/hardening1/9.png)

Una vez ejecutado, al pulsar con el botón derecho del ratón y entrar a 'inspecciónar los elementos' en el navegador, vemos que solo dice que es un servidor apache.

![5](/myblog/imagenes/hardening1/5.png)



HSTS

Para configurarlo hay que añadir lo siguiente en el Dockerfile, ya que debemos utilizar certificados.

![7](/myblog/imagenes/hardening1/7.png)

Primero copiamos los arhcivos apache.crt y apache.key en la carpeta /etc/apache2/ssl. Después le cambiamos el nombre al default-ssl.conf del contenedor y añadimos dominioseguro.com a la lista de host. A continuación copiamos el default-ssl.conf en el directorio /etc/apache2/sites-available. Por último habilitamos el default-ssl.conf y volvemos a cargar el servicio de apache.

Una vez se haya hecho el build y se haya ejecutado el contenedor, accedemos poniendo en el navegador: https://www.dominioseguro.com:8081, que es el puerto al que se ha redirigido el 443. Volvemos a entrar en 'Inspeccionar elementos' y vemos que se ha incluido la etiqueta de 'Strict-Transport-Security'.

![8](/myblog/imagenes/hardening1/8.png)