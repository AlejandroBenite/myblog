---
typora-root-url: ../../
typora-copy-images-to ../imagenes/seguridad-docker
layout: post
title: "Práctica: Seguridad en Docker"
categories: jekyll update
---
SEGURIDAD EN HOST.

Es muy importante controlar los permisos de los usuarios, por tanto lo mejor sería crear un grupo de docker y añadir a los usuarios que tengan que utilizar Docker.

![1](/myblog/imagenes/seguridad_docker/1.png)

Para que se apliquen los cambios hay que recargar los permisos o reiniciar.

![2](/myblog/imagenes/seguridad_docker/2.png)

SEGURIDAD EN EL DEMONIO.

Para impedir que los usuarios toquen la configuración y que tampoco puedan ver el socket hay que crear y configurar el archivo daemon.json (en /etc/docker/)

![3](/myblog/imagenes/seguridad_docker/3.png)

Configuramos el debug en false, le indicamos el número máximo de ficheros que se pueden ejecutar con ulimits y por último configuramos los icc en false para que no haya conectividad entre contenedores.

![4](/myblog/imagenes/seguridad_docker/4.png)

Los permisos de los ficheros que hay en /etc/docker, que son el daemon.json y el key.json, los dejamos así:

![5](/myblog/imagenes/seguridad_docker/5.png)

SEGURIDAD EN CONTENEDORES.

El flag ulimit, indica el máximo de ficheros que se pueden abrir simultaneamente dentro del contenedor, podemos indicar un máximo nosotros mismos, en el ejemplo se ha indicado 1000 como máximo, o dejar el que viene configurado por defecto que son 1048576.

![6](/myblog/imagenes/seguridad_docker/6.png)

También podemos limitar el número de CPU's que utiliza el contenedor con el siguiente comando.

![7](/myblog/imagenes/seguridad_docker/7.png)

Con la anterior imagen indicamos que se utilizaría media CPU.

PRIVILEGIOS.

Por defecto el usuario es root. Podemos cambiar el usuario con el flag -u seguido del uuid, pero tendrá problemas de permisos.

![8](/myblog/imagenes/seguridad_docker/8.png)

Con el flag --privileged, el usuario hereda las capabilities de linux. Por ejemplo, sin este flag no puede montar una carpeta en /mnt, aunque sea root.

![9](/myblog/imagenes/seguridad_docker/9.png)

Sin embargo, con el flag --privileged, si que se puede montar.

![10](/myblog/imagenes/seguridad_docker/10.png)

También podemos ejecutar un docker dentro de otro docker con el siguiente comando.

![11](/myblog/imagenes/seguridad_docker/11.png)

Comprobamos que se ha montado correctamente, primero en la máquina real y después en el contenedor.

![13](/myblog/imagenes/seguridad_docker/13.png)

![12](/myblog/imagenes/seguridad_docker/12.png)