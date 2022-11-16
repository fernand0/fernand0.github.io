---
layout: post
title: "JavaScript y las prestaciones"
date: "2022-03-28 15:00:00 +0000"
category: javascript
tags:
- programación
- desarrollo
- lenguajes
- optimizaciones
imagefeature: 'https://live.staticflickr.com/5219/5479382650_f269a561d6.jpg'
---
<a href="https://flickr.com/photos/fernand0/5479382650/" title="Motores del puente giratorio "><img src="https://live.staticflickr.com/5219/5479382650_f269a561d6.jpg" alt="Motores del puente giratorio " width="240" style="float:left; margin:5px"></a>
JavaScript no es mi lenguaje favorito y estoy por decir que sus efectos en la web de hoy en día están siendo poco útiles. Sin embargo, simpatizo con cualquier cosa que nos pueda hacer mejorar en algo y en [How JavaScript engines achieve great performance](https://blogg.bekk.no/how-javascript-engines-achieve-great-performance-fb0b36601557) porque, seguramente, se pueda aplicar a más dominios.

Me quedo con dos pinceladas, la detección de funciones 'calientes' (*hot*), esto es, funciones que se llaman con frecuencia y su traducción a instrucciones de máquina (otpimización cuando se necesita y no todo el rato: lo que haríamos con un perfilador).
Con la ventaja de que al haberla ejecutado ya algunas veces se pueden hacer todavía más optimizaciones, estas especulativas, que todavía podrían hacer el código más rápido.

> Whenever the JavaScript engine detects that a function is hot (that is, executed many times) it hands that function over to an optimizing compiler. This compiler translates the virtual machine instructions into actual machine instructions. What’s more, since the function has already been run several times, the optimizing compiler can make several assumptions based on previous runs. In other words, it can perform speculative optimizations to make even faster code.

Si se descubre que las suposiciones son falsas, se puede 'desoptimizar' y volver a comenzar el proceso.

> What happens if, later on, these speculations turn out to be wrong? The JavaScript engine can simply delete the optimized, but wrong, function, and revert to using the unoptimized version. Once the function has been run several more times, it can attempt to pass it to the optimizing compiler again, this time with even more information that it can use for speculative optimizations.

Hay más, pero lo que procede es recomendar la lectura para sacarle todo el partido. Sobre todo si están interesados en el tema.
