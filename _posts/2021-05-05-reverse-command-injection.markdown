---
typora-root-url: ../../
typora-copy-images-to ../imagenes/reverse_command_injection
layout: post
title: "Reverse Command Injection"
categories: jekyll update
---
REVERSE COMMAND INJECTION.

Para realizar esta práctica vamos a utilizar un script que nos permitirá abrir una consola  del servidor en nuestro ordenador. Primero codificamos el script en base 64.

![1](/../../../myblog/imagenes/reverse_comand_injection/1.png)



![2](/../../../myblog/imagenes/reverse_comand_injection/2.png)



Introducimos la dirección IP seguido de un punto y coma (;) y a continuación, con un echo, insertamos el script en base64 redirigiendo la salida a un archivo en la carpeta tmp.

![3](/../../../myblog/imagenes/reverse_comand_injection/3.png)

Ahora descodificamos el script en base64, guardado en el fichero shell.txt, y lo guardamos en un fichero con extensión php para poder ejecutarlo.

![4](/../../../myblog/imagenes/reverse_comand_injection/4.png)

Visualizamos el contenido de la carpeta tmp para comprobar que se ha creado el fichero. (Ignorar el archivo shell.php, es de la práctica anterior).

![5](/../../../myblog/imagenes/reverse_comand_injection/5.png)

Ahora ejecutamos el siguiente comando en un terminal y esperamos a que se ejecute el archivo nuevo_shell.php que hemos creado anteriormente.

![6](/../../../myblog/imagenes/reverse_comand_injection/6.png)

Para ejecutar el archivo nuevo_shell.php, sustituimos en la url lo que hay despues de page= e introducimos la ruta donde está situado el fichero, así:

![7](/../../../myblog/imagenes/reverse_comand_injection/7.png)

Si volvemos al terminal dónde hemos ejecutado el comando nc -v -n -l -p 1234, vemos que se ha abierto una conexión y ahora estamos dentro del servidor.

![8](/../../../myblog/imagenes/reverse_comand_injection/8.png)