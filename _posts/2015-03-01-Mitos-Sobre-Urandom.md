---
layout: post
title: "Mitos sobre /dev/urandom y más sobre aleatoriedad y su medida"
date: "Sun Mar 01 12:45:01 +0100 2015"
category: seguridad
tags: seguridad aleatorio random prng rng medida comparaciones urandom generadores 
---


<a href="https://www.flickr.com/photos/fernand0/1301539362/" title="Dados"><img src="https://farm2.staticflickr.com/1255/1301539362_daa1107f13.jpg" width="240"  alt="Dados"></a>
No se si el año pasado fue el de la aleatoriedad, o que por casualidad yo encontré más lectura sobre el tema. O, a lo mejor, simplemente estaba prestando más atención.

En [Myths about /dev/urandom ](http://www.2uo.de/myths-about-urandom/) una buena lectura sobre el tema, donde se habla de `/dev/urandom`, sus parecidos y diferencias con `/dev/random` y, al final, algunas discusiones sobre "aletaoriedad verdadera".

> I don't want to dive into that issue too deep, because it quickly gets philosophical. Discussions have been known to unravel fast, because everyone can wax about their favorite model of randomness, without paying attention to anyone else. Or even making himself understood. 

Lectura recomendable.

Podemos recomendar también la lectura de [How do you know if an RNG is working?](http://blog.cryptographyengineering.com/2014/03/how-do-you-know-if-rng-is-working.html) donde se aborda justamente ese tema: mucho se habla de números aleatorios y generadores. Pero cuando se piensa en la calidad de lo que se obtiene se dice que hay que medirla y poco más. Aquí da ideas, algún recordatorio interesante y, en definitiva, nos recuerda que el diablo está en (todos) los detalles.

Más sobre aleatoriedad y generadores

* [Números aleatorios y seguridad](https://mbpfernand0.wordpress.com/2012/11/05/numeros-aleatorios-y-seguridad/)
* [Dispositivos Bluetooth para generar números aleatorios](https://mbpfernand0.wordpress.com/2010/01/15/dispositivos-bluetooth-para-generar-numeros-aleatorios/)
* [Números aleatorios seguros en Java](http://fernand0.github.io/Numeros-Aleatorios-Seguros-En-Java/)
* [Generador de números aleatorios de Intel](http://fernand0.github.io/Generador-Numeros-Aleatorios-Intel/) 
