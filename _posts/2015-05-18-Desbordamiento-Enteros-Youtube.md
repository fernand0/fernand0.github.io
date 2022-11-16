---
layout: post
title: "Desbordamiento de enteros en YouTube"
date: "Mon May 18 11:30:01 +0100 2015"
category: desarrollo
tags: desarrollo bugs integer entero tamaño size cambios
---




<a href="https://www.flickr.com/photos/blakespot/8033280835/" title="Psy en pantallas"><img src="https://farm9.staticflickr.com/8174/8033280835_a2c6981fef.jpg" width="500"  alt="Psy" style="float:left; margin:5px"></a>

A veces tenemos coincidencias curiosas: acabo de encontrarme con un desbordamiento de un rango de índices para un vector en Pascal, de la mano de un par de estudiantes que no habían tenido las prevenciones adecuadas (con el compilador de [Free Pascal](http://www.freepascal.org/): ponían (por ejemplo) vector[-1] y no saltaba ningún error, así que colocaba datos en otra parte del registro (estamos trabajando estructuras de datos 'más' complejas) y el programa funcionaba mal.

La coincidencia es que al ir a mirar qué poner hoy en este sitio me he encontrado con que hace algunos días guardé la historia del desbordamiento de enteros en YouTube, por gentileza de Psy y el número de visualizaciones que ha tenido su vídeo en esa plataforma: [Gangnam Style overflows INT_MAX, forces YouTube to go 64-bit](http://arstechnica.com/business/2014/12/gangnam-style-overflows-int_max-forces-youtube-to-go-64-bit/)

> The maximum value of this number type, 2,147,483,647, is well known to C programmers as INT_MAX. Once INT_MAX is reached, attempting to record another view will normally roll over to -2,147,483,648.
>
>YouTube isn't the only software that this number is a problem for. Unix systems record time values as the number of seconds since 00:00:00 UTC on January 1, 1970. 32-bit systems use a signed 32-bit integer for this, so they will wrap around 2,147,483,647 seconds after that date. Two billion seconds is about 68 years; on January 19, 2038, at 03:14:07 in the morning, 32-bit Unix clocks will roll over.

Son ese tipo de errores en los que se piensa: ¿cómo podría llegar a alcanzarse esta cantidad? 
Y un buen día se alcanza. 
El próximo límite, con sus 64 bits, tardará un poco más en ser un prolema (4 mil millones de años, si los cálculos del artículo son correctos).

También lo cuentan en [We never thought a video would be watched in numbers greater than a 32-bit integer ...](https://plus.google.com/u/0/wm/4/+youtube/posts/BUXfdWqu86Q).

Si alguien tiene ganas de ver el vídeo:
<br />
<br />
[![Gangnam Style](http://img.youtube.com/vi/9bZkp7q19f0/0.jpg)](https://www.youtube.com/watch?v=9bZkp7q19f0)
