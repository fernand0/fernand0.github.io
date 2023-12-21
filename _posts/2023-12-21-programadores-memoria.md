---
layout: post
title: "Lo que todo programador debería saber sobre la memoria"
date: "2023-12-21 15:00:00 +0000"
category: desarrollo
tags:
- desarrollo
- programación
- programadores
- memoria
imagefeature: 'https://live.staticflickr.com/3557/3407158925_632643109e_b.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/3407158925/" title="Memoria"><img src="https://live.staticflickr.com/3557/3407158925_632643109e_b.jpg" alt="Memoria" class="img-responsive img-centered"></a>

La semana pasada decía que nadie lee esto y algunas personas me dijeron que sí (hasta alguna errata habían detectado). Reconforta mucho recibir esos comentarios y la realimentación, ¡Muchas gracias!

Programamos con un conjunto de suposiciones bastante básicas (acerca del sistema, el almacenamiento, la memoria,  el procesador, ...), pero a veces puede ser interesante conocer un poco mejor cómo funcionan las cosas para sacar partido (o no meter la pata) de lo que estemos usando.

Sobre la memoria podemos leer [What every programmer should know about memory, Part 1](https://lwn.net/Articles/250967/) que ya tiene unos años, pero que nos puede dar pistas interesantes. Hay hasta nueve partes, que se pueden ver enlazadas al final del texto, justo antes de los comentarios (se echan de menos, ¿eh? Casi nadie los mantiene por la selva en que se ha convertido la red en algunos aspectos).

> In the early days computers were much simpler. The various components of a system, such as the CPU, memory, mass storage, and network interfaces, were developed together and, as a result, were quite balanced in their performance. For example, the memory and network interfaces were not (much) faster than the CPU at providing data.

