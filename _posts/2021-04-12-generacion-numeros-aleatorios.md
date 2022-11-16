---
layout: post
title: Aleatoriedad en sistemas informáticos. Una introducción breve.
date: 2021-04-12 15:00:00 +0000
category: seguridad
tags:
- seguridad
- aleatoriedad
- random 
- PNRG
imagefeature: 'http://live.staticflickr.com/1255/1301539362_daa1107f13.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/1301539362/" title="Los dados del r5 "><img src="http://live.staticflickr.com/1255/1301539362_daa1107f13.jpg" alt="Los dados del r5 " width="240" style="float:left; margin:5px"></a>
La generación de números aleatorios en sistemas informáticos es un tema que tratamos por aquí de vez en cuando. Por eso me gustó [How Do Computers Generate Random Numbers](https://digitalbunker.dev/2020/09/08/how-do-computers-generate-random-numbers/) donde dan algunos detalles.

Siempre decimos que un computador es un sistema determinista y, por lo tanto, con muchos parámetros predecibles, lo que hace difícil resolver el problema de generar datos impredecibles.

> Anyone with any programming experience understands that computers are deterministic machines. If you provide the same input, you’ll always get the same output. That’s why having computers generate something by chance is trickier than it may seem.

Luego habla de posibbles fuentes de entropia (aleatoriedad), como pueden ser los movimientos del ratón, el ruido del ventilador, la presión atmosférica y otros, como semilla de los algoritmos generadores.

> We just need to pick a seed that an attacker wouldn’t be able to predict. This seed value will then be passed into an algorithm, similar to PRNGs, that will generate a random number to use. 

Finalmente, muestra algunos de los algoritmos y sus implementaciones.

Interesante.
