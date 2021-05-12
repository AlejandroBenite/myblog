---
typora-root-url: ../../
typora-copy-images-to ../imagenes/file_inclusion
layout: post
title: "Local and Remote file include"
categories: jekyll update
---
Para realizar esta práctica se ha utilizado un contenedor de docker con mutillidae.

LOCAL FILE INCLUDE.

En primer lugar ponemos en marcha el contenedor. A continuación, para comenzar con la práctica, nos situamos en 'Owasp 2017' --> 'A5 - Broken Access Control' --> 'Insecure Direct Object References' --> 'Local FIle Inclusion'. Saldrá una página como esta:

![1](/../../../myblog/imagenes/file_inclusion/1.png)

Para obtener un archivo local, unicamente se debe modificar la URL quitando lo que hay a continuación de page y añadiendo el fichero que se quiere visualizar, tal y como se muestra en la siguiente imagen.

![2](/../../../myblog/imagenes/file_inclusion/2.png)

El resultado sería el siguiente:

![3](/../../../myblog/imagenes/file_inclusion/3.png)



REMOTE FILE INCLUDE.

Para realizar el remote file include, hay que modificar un par de cosas del fichero php.ini. Para ello hay que abrir un terminal y abrir una consola en el contenedor ejecutando la siguiente orden.

![4](/../../../myblog/imagenes/file_inclusion/4.png)

Habrá aparecido una consola. Se edita con vi el fichero php.ini, especificando la opción 'On' en los valores 'allow_url_fopen' y 'allow_url_include'. Dejará mostrar páginas http.

![5](/../../../myblog/imagenes/file_inclusion/5.png)

Guardamos los cambios con ':wq' y reiniciamos el servicio apache2.service.

Ahora, tal y como se ha hecho en el apartado de local file include, se borra lo que hay a partir de page y se añade la url del sitio que se quiere visualizar. En este ejemplo, se ha puesto la url de google.

![6](/../../../myblog/imagenes/file_inclusion/6.png)

Mostrará el siguiente resultado, mutillidae y el buscador de google.

![7](/../../../myblog/imagenes/file_inclusion/7.png)