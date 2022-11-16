---
layout: post
title: "Colisiones en el sistema de resumen SHA1"
date: "Fri Feb 23 15:18:01 +0100 2018"
category: seguridad
tags: [seguridad, colisiones, hash, SHA1, firma, resumen]
imagefeature: https://3.bp.blogspot.com/-Ca6n5XsDQU4/WK6ljCSebeI/AAAAAAAAAa4/MXeyy0z13yIqp9DEWVLiqjJ_xSP2u7YOgCLcB/s640/Collision-illustrated.png
---


<a href="https://www.flickr.com/photos/fernand0/3046816128" title="Colisiones ensistemas de resumen"><img src="https://3.bp.blogspot.com/-Ca6n5XsDQU4/WK6ljCSebeI/AAAAAAAAAa4/MXeyy0z13yIqp9DEWVLiqjJ_xSP2u7YOgCLcB/s640/Collision-illustrated.png" width="240"  alt="Colisiones ensistemas de resumen" style="float:left; margin:5px"></a>
En una bitácora como esta, que no sólo no es de actualidad sino que suele traer temas con bastantes meses, no se si tiene mucho sentido traer estas cosas pero me gusta guardarlas para tenerlas en algún sitio recopiladas. 

Por eso traigo [Announcing the first SHA1 collision](https://security.googleblog.com/2017/02/announcing-first-sha1-collision.html) que habla de una colisión en un sistema de firma (hash). La idea de estos sistemas es sencilla: no debería ocurrir que dos 'mensajes' diferentes produzcan el mismo resumen. En este caso anunciaban una forma de generar una colisión para el algoritmo SHA1. Para el común de los mortales esto significa, esencialmente, que ya podemos ir pensando en dejar de usarlo (si es que lo hacíamos).
También es un recordatorio de que los 'estándares' que alguien nos recomendó en algún momento van quedando obsoletos y que no podemos dejarnos llevar por la costumbre y la comodidad.

> A collision occurs when two distinct pieces of data—a document, a binary, or a website’s certificate—hash to the same digest as shown above. In practice, collisions should never occur for secure hash functions. However if the hash algorithm has some flaws, as SHA-1 does, a well-funded attacker can craft a collision. 

En esa entrada nos recomendaban utilizar SHA-256 y SHA-3.
