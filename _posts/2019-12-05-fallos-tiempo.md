--- 
layout: post
title: "Identificación de características basada en el tiempo"
date: "Thu Dec 5 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, identificación, bug, fallo, chromium, tiempo]
imagefeature: https://live.staticflickr.com/4048/4343951465_bd3ce7dc6e_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/4343951465" title="Reloj"><img src="https://live.staticflickr.com/4048/4343951465_bd3ce7dc6e_m.jpg" width="240"  alt="Reloj" style="float:left; margin:5px"></a>
Una clase de fallos especialmente sugerente y a los que no siempre se presta atención son los relacionados con el tiempo: un ejemplo serían las condiciones de carrera (cuando algo cambia entre el momento de verificar que una operación está permitida y el momento en que la operación se realiza); el que traemos hoy aquí tiene que ver con el tiempo que se tarda en realizar alguna operación dependiendo de las circunstancias que rodean a nuestro sistema. Un ejemplo clásico de este tipo de errores era cuando buscamos algo: típicamente es más rápido cuando lo encontramos que cuando no está (y eso da pistas sobre valores de algunos datos).

En esta ocasión traemos [Detecting incognito mode in Chrome 76 with a timing attack](https://blog.jse.li/posts/chrome-76-incognito-filesystem-timing/) que habla justamente de un problema de este tipo. En Chrome 76 era posible determinar si el usuario utilizaba el modo incógnito por la velocidad de escritura, al utilizar APIs diferentes.

Había un precedente, basado en la cantidad de espacio disponible para poder utilizarse (en [Bypassing anti-incognito detection in Google Chrome](https://mishravikas.com/articles/2019-07/bypassing-anti-incognito-detection-google-chrome.html))

> Recently, security researcher Vikas Mishra discovered that we can infer incognito state based on the amount of space which the API makes available.

Y el autor habla de la medición de escrituras, en este nuevo tipo de fallo, que se basa en medir el tiempo que cuesta escribir repetidamente cadenas de caracteres largas:

> In this blog post, I present a proof-of-concept of a technique which websites could use to detect incognito users by measuring the speed of writes to the API.

...

> The setup is relatively simple: benchmark the filesystem by repeatedly writing large strings to it and measuring how long that takes. Because memory is faster than disk, we should be able to tell by the speed whether the site visitor is in incognito.

Interesante.
