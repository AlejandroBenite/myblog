---
typora-root-url: ../../
typora-copy-images-to ../imagenes/config_apache
layout: post
title:  "Práctica: Configuración básica de Apache"
categories: jekyll update
---
Tarea 1

- Cread dos host virtuales usando el método descrito en este documento (website 1 y website2).

![1](/myblog/imagenes/config_apache/1.png)

![2](/myblog/imagenes/config_apache/2.png)

- Una vez creados, cread un documento markdown con las capturas de pantalla de los directorios sites-available y sites-enabled, así como de los directorios creados dentro del DocumentRoot definido en cada uno de ellos.

![3](/myblog/imagenes/config_apache/3.png)

![4](/myblog/imagenes/config_apache/4.png)

![5](/myblog/imagenes/config_apache/5.png)

- Así mismo debéis adjuntar la configuración de vuestros sitios en apache así como del archivo /etc/hosts.

![6](/myblog/imagenes/config_apache/6.png)

![7](/myblog/imagenes/config_apache/7.png)

![8](/myblog/imagenes/config_apache/8.png)

- Finalmente, adjuntad una captura de pantalla del navegador pidiendo esos dos sitios.

![9](/myblog/imagenes/config_apache/9.png)

![10](/myblog/imagenes/config_apache/10.png)

Tarea 2

- Configurad vuestro servidor apache de esta manera y adjuntad las capturas de pantalla tanto del archivo de configuración de apache como del navegador apuntando a dicho alias.

![11](/myblog/imagenes/config_apache/11.png)

![12](/myblog/imagenes/config_apache/12.png)

Tarea 3

- Realiza esta modificación en tu archivo de configuración de apache. Adjunta el contenido de tu archivo de apache y una captura de pantalla de Firebug donde se vea el Status Code 302.

![13](/myblog/imagenes/config_apache/13.png)

![14](/myblog/imagenes/config_apache/14.png)

Tarea 4

- Realiza esta modificación en tu archivo de configuración. Crea un documento markdown con esta información y adjunta una captura de pantalla del firebug mostrando está pagina y en el que se vea el Status Code 404.

Una opción es la de añadir una línea en el fichero de nuestro host virtual (/etc/apache2/sites-available/website1.conf o website2.conf) con el código de error y el mensaje que se mostrará al introducir la dirección en el navegador.

![15](/myblog/imagenes/config_apache/15.png)

![16](/myblog/imagenes/config_apache/16.png)

Otra opción sería la de crear un documento de error y una vez insertemos la dirección en el navegador, éste muestre lo que contiene el archivo.

![17](/myblog/imagenes/config_apache/17.png)

![18](/myblog/imagenes/config_apache/18.png)

