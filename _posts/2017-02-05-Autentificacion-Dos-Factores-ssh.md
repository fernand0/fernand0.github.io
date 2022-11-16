---
layout: post
title: "Reforzar el acceso a nuestros sistemas"
date: "Sun Feb 05 16:50:01 +0100 2017"
category: seguridad
tags: [seguridad, ssh, 2fa, latch, acceso, autentificación]
imagefeature: https://c1.staticflickr.com/1/282/32534213772_0900d11508_m.jpg
---





Traemos un par de lecturas sobre cómo podemos reforzar el acceso a nuestros sistemas, añadiendo seguridad de dos formas (que podrían combinarse entre sí, puesto que se ocupan de diferentes partes: acceso y autentificación a un sistema).

<a href="https://www.flickr.com/photos/fernand0/32534213772" title="Candados"><img src="https://c1.staticflickr.com/1/282/32534213772_0900d11508_m.jpg" width="240"  alt="Candados" style="float:center; margin:5px">

En primer lugar, en [Using 2 factor authentication for SSH](https://www.arm-blog.com/using-2-factor-authentication-for-ssh/) unas instrucciones sobre cómo utilizar el app [Google Authenticator](https://support.google.com/accounts/answer/1066447) para establecer un sistema de dos factores para el servicio SSH.

La otra posibilidad es habilitar los servicios cuando los necesitemos, de forma que cuando no los vayamos a usar no estén disponibles. En este caso podríamos utiliar [Latch](https://latch.elevenpaths.com/). Tal y como cuentan en [Fortificar GNU/Linux Ubuntu con Latch: Vídeo Tutorial](http://www.elladodelmal.com/2015/11/fortificar-gnulinux-ubuntu-con-latch.html) se puede usar en cualquiera de los sistemas más comunes.
