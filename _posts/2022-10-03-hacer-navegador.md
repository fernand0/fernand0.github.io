---
layout: post
title: "La complejidad de los navegadores y la dificultad de crear uno desde cero"
date: "2022-10-03 15:00:00 +0000"
category: internet
tags:
- internet
- navegador
- browser
- complejidad
imagefeature: 'https://live.staticflickr.com/65535/51350237881_f884096051.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/51350237881/" title="Nasas y barco pesquero "><img src="https://live.staticflickr.com/65535/51350237881_f884096051.jpg" alt="Nasas y barco pesquero " class="img-responsive img-centered"></a>
Hacer un navegador, nos dicen en [The reckless, infinite scope of web browsers](https://drewdevault.com/2020/03/18/Reckless-limitless-scope.html) es una tarea muy complicada.

El problema tiene que ver con la larga historia de la web: no hay límites en lo que se puede ver en el navegador, ni en las características que se van añadiendo:

> This strategy of unlimited scope and perpetual feature creep is reckless, andhas been allowed to go on for far too long.

Hay 1217 [especificaciones de la W3C](https://www.w3.org/TR/) y resulta que alguien interesado debería leerse 114 millones de palabras, que es muchísimo.

> The total word count of the W3C specification catalogue is 114 million words at the time of writing. If you added the combined word counts of the C11, C++17, UEFI, USB 3.2, and POSIX specifications, all 8,754 published RFCs, and the combined word counts of everything on Wikipedia’s list of longest novels, you would be 12 million words short of the W3C specifications.

La conclusión es que es imposible construir un nuevo navegador (y la prueba es que cada vez tenemos menos, aunque parezca que hay más porque se reutilizan dos o tres motores compartidos).

Aunque no nos cuesten dinero, resulta que el navegador puede ser el programa más costoso de los que hay en un sistema típico.

> Browsers are the most expensive piece of software a typical consumer computer runs.

Y también tiene consecuencias desde el punto de vista de la seguridad, siendo estos programas responsables de un montón de problemas.

> Web browsers areresponsible for more than 8,000 CVEs.

Ya queda muy lejos cuando hablábamos de la seguridad de mozilla por su simplicidad frente al Internet Explorer, [Software Complexity: Open Source vs Microsoft
](https://www.spinellis.gr/blog/20031003/index.html).
Por cierto, sorpresa agradable al ver que aún hay entradas recientes (marzo de este año) en ese blog.

**Actualización (2022-10-04)** Me recordaban en Mastodon (no es visible públicamente, no lo enlazo) el reciente anuncio de [Privacy Browser PC](https://www.stoutner.com/privacy-browser-pc/) y lo añado aquí.
