---
typora-root-url: ../../
typora-copy-images-to ../imagenes/validacion_entradas
layout: post
title: "Práctica: Validación de entradas"
categories: jekyll update
---
ROBO DE SESIÓN.

En primer lugar iniciamos sesión (como víctima) entrando en la página login.php.

![victima-login(1)](/myblog/imagenes/validacion_entradas/victima-login(1).png)

Al iniciar sesión con nuestro usuario y contraseña, aparece un mensaje de bienvenida.

![victima-logueada(2)](/myblog/imagenes/validacion_entradas/victima-logueada(2).png)

Ahora pulsamos en F12, y a continuación en la pestaña 'Network' y recargamos con F5. Seleccionamos login.php.

![victima-inspeccion-elemento(3)](/myblog/imagenes/validacion_entradas/victima-inspeccion-elemento(3).png)

Buscamos la cookie de la sesión.

![victima-cookie(4)](/myblog/imagenes/validacion_entradas/victima-cookie(4).png)

Ahora interpretamos el papel de atacante. Abrimos una ventana nueva del navegador y vamos a la página login.php (misma dirección que la victima).

![hacker-login(5)](/myblog/imagenes/validacion_entradas/hacker-login(5).png)

Descargamos un plugin para la gestión de cookies y buscamos la IP de localhost.

![hacker- manager-cookies-dominio(6)](/myblog/imagenes/validacion_entradas/hacker- manager-cookies-dominio(6).png)

Cambiamos la cookie que tiene el atacante (primera imagen) por la cookie que le hemos robado a la víctima (imagen 2) tal y como vemos en las imagenes.

![hacker-cookie(7)](/myblog/imagenes/validacion_entradas/hacker-cookie(7).png)

![hacker-cambio-cookie(8)](/myblog/imagenes/validacion_entradas/hacker-cambio-cookie(8).png)

Recargamos la página de login.php y podemos comprobar que hemos iniciado sesión únicamente robando la cookie de la víctima.

![hacker-recarga-pagina(9)](/myblog/imagenes/validacion_entradas/hacker-recarga-pagina(9).png)



FIJACIÓN DE SESIÓN.

En este ataque el atacante le manda la dirección URL a la víctima, ésta inicia sesión y el atacante al recargar la página aparecerá loggeado. Primero entramos con el atacante en la página de login.php.

![victima-login(1)](/myblog/imagenes/validacion_entradas/victima-login(1).png)

Pulsamos F12, vamos a 'Network' y copiamos la cookie.

![cookie_atacante(2)](/myblog/imagenes/validacion_entradas/cookie_atacante(2).png)

Le pasamos la dirección URL a la víctima añadiendo la cookie de sesión del atacante.

![url_victima(3)](/myblog/imagenes/validacion_entradas/url_victima(3).png)

La víctima, no se da cuenta, e inicia sesión con su usuario y contraseña y se le muestra el mensaje de bienvenida.

![inicio_sesion_victima(4)](/myblog/imagenes/validacion_entradas/inicio_sesion_victima(4).png)

El atacante recarga la página web y le aparece este mismo mensaje a él también.

![recarga_atacante(5)](/myblog/imagenes/validacion_entradas/recarga_atacante(5).png)



CONTROL DE ACCESO.

Tenemos un usuario administrador, Mario, y un usuario normal, Juan. El administrador será el único que puede entrar en la página administración.php y el usuario el único que pueda entrar en su perfil en perfil.php.

Primero vamos a iniciar sesión en login.php como administrador.

![login_admin(1)](/myblog/imagenes/validacion_entradas/login_admin(1).png)

Al iniciar sesión como administrador, vemos que podemos acceder a la página administración.php.

![acceso_admin(2)](/myblog/imagenes/validacion_entradas/acceso_admin(2).png)

Sin embargo, no nos deja entrar en la página de perfil de Juan.

![acceso_perfil(3)](/myblog/imagenes/validacion_entradas/acceso_perfil(3).png)

Ahora iniciamos sesión como usuario normal, es decir, como Juan.

![login_usuario(4)](/myblog/imagenes/validacion_entradas/login_usuario(4).png)

Accedemos al perfil de Juan, en perfil.php, y comprobamos que podemos acceder a la página sin problemas.

![acceso_perfil(5)](/myblog/imagenes/validacion_entradas/acceso_perfil(5).png)

Por úlimo comprobamos que no podemos entrar a la página de administración.php, ya que no somos administradores.

![acceso_admin(6)](/myblog/imagenes/validacion_entradas/acceso_admin(6).png)