---
layout: post
title: "La aleatoriedad y algunas ayudas de la física"
date: "Mon Jun 25 16:02:01 +0100 2018"
category: seguridad
tags: [seguridad, aleatoriedad, random, números, entropía, lava]
imagefeature: https://c2.staticflickr.com/4/3157/2900201894_67c2a742d4_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/2900201894" title="Lava de la de verdad"><img src="https://c2.staticflickr.com/4/3157/2900201894_67c2a742d4_m.jpg" width="240"  alt="Lava de la de verdad" style="float:left; margin:5px"></a>
Ya hemos hablado unas cuantas veces de la necesidad de números aleatorios en lostemas relacionados con la aleatoriedad. Fundamentalmente se obtienen mediante algoritmos, con la prevención de seleccinar las semillas de fuentes aleatorias (entropía obtenida alrededor de la actividad del computador). También se venden tarjetas criptográficas que incluyen algún tipo de generador de números aleatorios.

Por eso fue una noticia curiosa de leer la de que [10% of the Internet Is Encrypted with Lava Lamps](https://www.macobserver.com/columns-opinions/editorial/cloudflare-encrypted-lava-lamps/). Esto es, uno de los proveedores más grandes de internet (Cloudfare), que necesita generar una buena cantidad de números aleatorios recurre a la vieja física del mundo real y a las lámparas de lava. En este caso la dinámica de fluidos (difícil de modelizar y predecir) juega a nuestro favor.

Según nos contaban en [The Hardest Working Office Design In America Encrypts Your Data–With Lava Lamps](https://www.fastcodesign.com/90137157/the-hardest-working-office-design-in-america-encrypts-your-data-with-lava-lamps) Cloudfare tendría un muro lleno de lámparas de este tipo:

> Inspired by an idea from engineers at Sun Microsystems, who thought that lava lamps could help generate randomness since modeling how fluid moves within the lamps is incredibly difficult, Prince decided to create an entire wall of lava lamps. Cloudflare calls it the “Wall of Entropy.”

Fotografían el muro cada milisegundo y mediante un sistema de análisis de la imagen utilizan ciertos parámetros para la generación de los números aleatorios. Esta información se añadiría a los otros sistemas que utilizan (al final, una fotografía cada milisegundo no es mucho, para lo que pueden llegar a necesitar).

Curioso.
