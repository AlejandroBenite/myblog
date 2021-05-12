---
typora-root-url: ../../
typora-copy-images-to ../imagenes/upload_files
layout: post
title: "Práctica: FileUpload"
categories: jekyll update
---
Para realizar esta práctica se ha utilizado un contenedor de docker con mutillidae.

FILE UPLOAD.

Para hacer prácticas de file upload en Mutillidae debemos ir a: 

Vamos a utilizar un script para realizar un reverse shell. Una vez descargado el script, cambiamos la dirección IP a la de nuestro ordenador y, si queremos, también el puerto.

![1](/../../../myblog/imagenes/upload_files/1.png)

Ahora seleccionamos el fichero y lo subimos.

![2](/../../../myblog/imagenes/upload_files/2.png)

Nos avisa de que se ha subido con éxito y nos muestra la ruta en el que se encuentra el fichero (en */tmp*).

![3](/../../../myblog/imagenes/upload_files/3.png)

Antes de acceder al archivo, abrimos una consola y ejecutamos el siguiente comando, lo que nos mostrará  un terminal en nuestro ordenador y que será del servidor.

![4](/../../../myblog/imagenes/upload_files/4.png)

Una vez ejecutada la orden, en la url de la web cambiamos lo que hay detrás de *page=* por la ruta del fichero que hemos subido.

![5](/../../../myblog/imagenes/upload_files/5.png)

Al pulsar enter, vemos que en la consola se ha abierto un terminal y que es del servidor ya que, por ejemplo, podemos encontrar un fichero zip llamado mutillidae.

![6](/../../../myblog/imagenes/upload_files/6.png)