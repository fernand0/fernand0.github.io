---
layout: post
title: "Números aleatorios seguros en Javascript"
date: "Fri Dec 30 21:35:01 +0100 2016"
category: seguridad
tags: seguridad random aleatorio prng javascript
imagefeature: https://c2.staticflickr.com/2/1255/1301539362_daa1107f13_m.jpg
---




<a href="https://www.flickr.com/photos/fernand0/152110645" title="Aleatorio"><img src="https://c1.staticflickr.com/1/49/152110645_43aafcb33c_m.jpg" width="240"  alt="Aleatorio" style="float:left; margin:5px"></a>
Otra nota sobre números aleatorios seguros. En este caso nos avisaban en [V8 Javascript Fixes (Horrible!) Random Number Generator](http://hackaday.com/2015/12/28/v8-javascript-fixes-horrible-random-number-generator/) sobre un error en la forma de generar números aleatorios en Javascript que tiene el interés de proporcionar una explicación general bastante buena, como alguien encontró el fallo al encontrar una colisión en un identificador de sesión (tan sólo un mes después de empezar) y cómo los programadores eligieron la versión incorrecta de un método que no estaba mal.

En [TIFU by using Math.random()](https://medium.com/@betable/tifu-by-using-math-random-f1c308c4fd9d) cuentan los detalles sobre la historia en primera persona. Sin olvidar que estaban utilizando un generador de números aleatorios que no era criptográfico.

De paso, podemos probar el generador de nuestro navegador en este [generador de imágenes aleatorias](http://bl.ocks.org/mmalone/bf59aa2e44c44dde78ac).
