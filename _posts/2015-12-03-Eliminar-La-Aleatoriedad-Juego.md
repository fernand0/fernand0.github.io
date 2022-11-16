---
layout: post
title: "Eliminar la aleatoriedad en un juego"
date: "Thu Dec 03 08:50:01 +0100 2015"
category: desarrollo
tags:  [desarrollo, juegos, aleatoriedad, random, pruebas, experimentos, cambios]
---






<a href="https://www.flickr.com/photos/fernand0/3019236841" title="Juegos"><img src="https://c2.staticflickr.com/4/3223/3019236841_1b30fa0093_m.jpg" width="240"  alt="Juegos" style="float:left; margin:5px"></a> 

En [Deterministic Doom](http://jmtd.net/log/deterministic_doom/) hace la prueba de eliminar la aleatoriedad del conocido juego Doom. Para ello, primero observa que el juego no utiliza ninguna fuente de aleatoriedad externa, sino que incluye una tabla de valores de donde se toman los valores para diversas acciones en el juego:

> Rather than consume system randomness, Doom has a fixed 256-value random number table from which numbers are pulled by aspects of the game logic

Por otra parte, los efectos son los que uno podría imaginar (y algunos otros): desde el comportamiento de los atacantes a diversos efectos de imagen, pasando por las armas que se utilizan. 

Prueba con distintos valores, por ejemplo:

> With 0x00, monsters never make their idle noises (breathing etc.) On the other hand, with 0xFF, they always do: so often, that each sample collides with the previous one, and you just get a sort-of monster drone. This is quite overwhelming with even a small pack of monsters.

Curioso.
