---
typora-root-url: ../../
typora-copy-images-to ../imagenes/command_injection
layout: post
title: "Command Injection"
categories: jekyll update
---
COMMAND INJECTION.

Se va a realizar una variante del File Upload. Para ello vamos a utilizar Mutillidae.

El formulario permite al usuario realizar un ping introduciendo una dirección IP. Para ver si es vulnerable al Command Injection, introducimos el comando ls junto a la dirección IP para que muestre el contenido del directiorio en el que estamos.

![1](/../../../myblog/imagenes/command_injection/1.png)

Vemos que hay tanto ficheros como directorios.

Si hacemos un ls del directorio passwords vemos que hay un documento accounts.txt, si hacemos un cat de este fichero, vemos distintos usuarios y contraseñas.

![2](/../../../myblog/imagenes/command_injection/2.png)



![3](/../../../myblog/imagenes/command_injection/3.png)

