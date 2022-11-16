---
layout: post
title: "Algunos (pocos) datos sobre generadores de números aleatorios"
date: "2022-01-03 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- aleatoriedad
- random
- PRNG
- generadores
imagefeature: 'https://live.staticflickr.com/49/152110645_43aafcb33c.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/152110645/" title="La suerte (?) "><img src="https://live.staticflickr.com/49/152110645_43aafcb33c.jpg" alt="La suerte (?) " width="240" style="float:left; margin:5px"></a>
De vez en cuando volvemos a hablar de los generadores de números aleatorios. Aunque sólo sea porque alguien la próxima vez lo haga un poco mejor.
Siempre decimos que los sistemas informáticos son muy malos generando aleatoriedad y que utilizan algunos trucos para ello.
En este caso John D. Cook entra en detalle en diversas implementaciones y propuestas en [Evolution of random number generators](https://www.johndcook.com/blog/2021/04/29/reinventing-rng/).

Habla de los generadores basados en congruencias

> x(n+1) = a.x(n) mod m

Y luego hace algunos análisis estadísticos con algunos valores para los parámetros del generador (los valores de a, n y m). No se asusten, es cortito y muy visual.

