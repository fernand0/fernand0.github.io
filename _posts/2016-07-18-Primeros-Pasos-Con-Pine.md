---
layout: post
title: "Primeros pasos con Pine64"
date: "Mon Jul 18 16:30:01 +0100 2016"
category: making
tags: [making, Pine64, soc, ordenador, pruebas, compras]
imagefeature: https://scontent-mad1-1.cdninstagram.com/t51.2885-15/e35/12976346_479978868864256_1204108015_n.jpg
---





<a href="https://www.instagram.com/p/BEvzAYGQB5g/" title="Caja del Pine64"><img src="https://scontent-mad1-1.cdninstagram.com/t51.2885-15/e35/12976346_479978868864256_1204108015_n.jpg" width="240"  alt="Caja del Pine64" style="float:left; margin:5px"></a>
Como decíamos el otro día, tenía pendiente de terminar de poner en marcha mi 
 [Pine64](https://www.kickstarter.com/projects/pine64/pine-a64-first-15-64-bit-single-board-super-comput).

El Pine64 llegó hace bastantes días pero no había encontrado la ocasión de ponerme y cuando la encontré no lo conseguí a la primera. 
Desde luego, no es un proyecto tan bien acabado como el C.H.I.P. [Primeros pasos con el C.H.I.P.](http://fernand0.github.io/Primeros-Pasos-Con-Chip/) y tampoco le había dedicado tiempo suficiente. 
El primer problema que tuve con una distribución Ubuntu que puse en una tarjeta de memoria era que intentaba buscar una conexión ethernet; como no le había puesto el cable, se quedaba atascado hasta que expiraba el tiempo correspondiente (timeout): eso me hizo perder algún rato pensando que la imagen estaba defectuosa.

Cuando por fin me di cuenta y arrancó, configuré la red y seguí teniendo problemas de conexión en la red local (no me detuve mucho a ver qué pasaba, decidí probar otra distribución).

Tampoco ayudó mucho esta entrada negativa [Pine64: the un-review](http://hackaday.com/2016/04/21/pine64-the-un-review/) que exponía bastantes quejas sobre la placa.

A primera vista es una placa gigantesca: ocupa casi el mismo espacio que tres Raspberry Pi (que a la vista de los últimos dispositivos que vamos consiguiendo ya se nos hace algo grande). Además es exigente en cuanto a la alimentación necesaria (no nos servirá cualquier cargador) y la base no está muy refinada (si lo apoyamos en nuestro típico brazo de sillón de casa se enganchará).

Una de las web de referencia sería [Pine64](http://pine64.com/) y allí se puede ver información. En [Downloads](https://www.pine64.pro/downloads/) hay recopiladas diversas imágenes con sistemas operativos que incluyen Android, Remix OS, Debian (la que finalmente instalé), Ubuntu y otras...

<div align="center">
<a href="https://www.instagram.com/p/BEwdAQfQBwe/" title="Pine 64 al lado de la Raspberry Pi y un Arduino"><img src="https://scontent-mad1-1.cdninstagram.com/t51.2885-15/e35/13092485_1034695456607883_1632372728_n.jpg" width="240"  alt="Pine 64 al lado de la Raspberry Pi y un Arduino" style="float:center"></a>
</div>

Una vez que conseguimos que arranque disponemos de un sistema funcionando que configuramos a nuestro gusto y podemos empezar a trabajar. En unas pruebas sencillas se ve que es más rápida que el C.H.I.P. y la vieja Raspberry pero en la práctica la sensación no es de mucha soltura (si me preguntaran sin haber hecho alguna prueba habría dicho que el C.H.I.P. iba más fluído). Eso a pesar de tener un procesador a priori más capaz y cuatro cores.

Seguimos aprovechándonos de la copia de configuraciones desde otras máquinas para poder conectarnos en diferentes sitios y ya podemos gestionarla desde un portátil mediante ssh.

El escritorio:

<div align="center">
<a href="https://www.instagram.com/p/BH7kQKxhHF5/" title="Pine64 Desktop"><img src="https://scontent-mad1-1.cdninstagram.com/t51.2885-15/e35/13768135_272046513171356_894672650_n.jpg" width="240"  alt="Pine64 Desktop" style="float:center"></a>
</div>

En el apartado negativo, pedí dos módulos adicionales y sólo ha llegado uno. Aparentemente están (o han estado colapsados) y sigo sin la cámara que pedí. Confíoen que cuando se normalice todo terminaré recibiéndola.

Entre sus características 

* Procesador 1.2 Ghz Quad-Core ARM Cortex A53 64-Bit con Dual core Mali 400 MP2 GPU.
* 512 Mb, 1Gb o 2Gb de RAM (yo tengo la de 1Gb)
* Bluetooth 4.0 and 802.11BGN (vendida como añadido aparte).
* Salida de vídeo HDMI 920×1200 HDMI v1.4 hasta 4K.
* Dos puertos USB y puerto micro USB OTG (se usa para alimentación)

A ver si damos con algún proyecto adecuado para este chisme.
