--- 
layout: post
title: "La complejidad y la seguridad: el caso de las tarjetas de memoria"
date: "Tue Apr 02 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, tarjetas, microSD, discos, almacenamiento, complejidad]
imagefeature: https://farm3.staticflickr.com/2448/3765903082_4917c2dd9b_m.jpg
---



<a href="https://www.flickr.com/photos/fernand0/3765903082" title="Viejos discos duros"><img src="https://farm3.staticflickr.com/2448/3765903082_4917c2dd9b_m.jpg" width="240"  alt="Viejos discos duros" style="float:left; margin:5px"></a>
En informática todo se vuelve tan complejo que es difícil estar seguro de que nada puede fallar. Es un viejo dicho el de que una forma de mejorar la seguridad es buscar diseños simples, que sean fáciles de comprender, gestionar y utilizar.
En [On Hacking MicroSD Cards](https://www.bunniestudios.com/blog/?p=3554) la enésima prueba de esto: las tarjetas de memoria son tan complejas que algunas permiten algo tan desagradable como la ejecución de código.

> [...] disclosed a finding that some SD cards contain vulnerabilities that allow arbitrary code execution — on the memory card itself.

Por un lado, las tarjeta son tan baratas que contienen de manera inevitable defectos. Estos fallos han de enmascararse mediante sistemas de corrección y esto lleva de forma inevitable a tener problemas:

> Flash memory is really cheap. So cheap, in fact, that it’s too good to be true. In reality, all flash memory is riddled with defects — without exception. The illusion of a contiguous, reliable storage media is crafted through sophisticated error correction and bad block management functions. This is the result of a constant arms race between the engineers and mother nature; with every fabrication process shrink, memory becomes cheaper but more unreliable. Likewise, with every generation, the engineers come up with more sophisticated and complicated algorithms to compensate for mother nature’s propensity for entropy and randomness at the atomic scale. 

Al final, la tarjeta incluye un microcontrolador que hace abstracción del sistema físico que tiene debajo:

> These algorithms are too complicated and too device-specific to be run at the application or OS level, and so it turns out that every flash memory disk ships with a reasonably powerful microcontroller to run a custom set of disk abstraction algorithms.

El motivo casi siempre es el precio: es mucho más barato añadir esta complicación que fabricar mejor las tarjetas.

> Amazingly, the cost of adding these controllers to the device is probably on the order of $0.15-$0.30, particularly for companies that can fab both the flash memory and the controllers within the same business unit. It’s probably cheaper to add these microcontrollers than to thoroughly test and characterize each flash memory chip, which explains why managed flash devices can be cheaper per bit than raw flash chips, despite the inclusion of a microcontroller. 

A mi me ha recordado un poco la presentación aquella de Wietse Venema [[PDF] The broken file shredder Programming traps and pitfalls](https://www.first.org/resources/papers/conference2007/venema-wietse-2-slides.pdf) donde nos hablaba de las complejidades del borrado de información en los abuelos de las tarjetas de memoria, los discos duros. Y me hace recordar cada vez que alguien habla de borrado seguro de información en los medios generalitas. Casi nada es tan fácil como parece.

Interesante.
