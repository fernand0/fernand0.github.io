---
layout: post
title: "Vale la pena optimizar en el momento adecuado"
date: "2024-01-02 15:00:00 +0000"
category: desarrollo
tags:
- desarrollo
- programación
- optimización
- alphadev
- google
- ordenación
- ia
- inteligencia artificial
imagefeature: 'https://live.staticflickr.com/65535/52228680236_a323b294ed_z.jpg'
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/52228680236/in/photolist-61YvNu-7YMr1V-2nzgD1Q-9rSSCy" title="En orden"><img src="https://live.staticflickr.com/65535/52228680236_a323b294ed_z.jpg" width="640" height="427" alt="En orden"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Hay una cita por ahí que parece que dijo el informático Donal Knuth y que se suele escribir como: 'la optimización prematura es el origen de todos los males'

> premature optimization is the root of all evil 

Bien entendido, claro, que se refería al contexto de la programación y el desarrollo de programas (aunque seguramente se pueda aplicar en más casos).
Sin embargo, también es cierto que en algún momento hay que optimizar (sobre todo para programas o bibliotecas de uso amplio, donde una pequeña mejora puede hacer que nuestros programas sean mucho mejores).

El año pasado alguna gente de Google publicaron [Faster sorting algorithms discovered using deep reinforcement learning](https://www.nature.com/articles/s41586-023-06004-9) donde se hace justamente eso: con aprendizaje reforzado profundo tratan de obtener versiones mejores de los algoritmos que se utilizan habitualmente.

El resultado es interesante, pero lo que más llamó mi atención (sobre todo porque lo contamos en clase, en una versión mucho más grosera y poco refinada) como el manejo de los problemas de tamaño más pequeño puede ser el que marque la diferencia. En este sentido, se pueden ver en el artículo análisis bastante refinados de código en c++, sus versiones en ensamblador y cómo algunas instrucciones pueden ser importantes a la hora de obtener soluciones eficientes.

Por ejemplo, en la figura 4 se puede ver cómo el algoritmo original proponía evaluar la longitud de lo que se quería ordenar y según fuera 2, 3, ó 4, se lanzaba un algoritmo diferente. La propuesta de AlphaDev, sin embargo, primero mira si el tamaño es 2 y lanza un algoritmo especializado, si no, lanza el algoritmo para ordenar 3 elementos; si la longitud ya era 3 el vector ya estará ordenado, y  si no lo era, llama a un algoritmo especializado en ordenar 4 con los 3 primeros ya en orden.

> A flow diagram of the variable sort 4 (VarSort4) human benchmark algorithm. In this algorithm, a sequence of unsorted numbers are input into the algorithm. If the sequence length is four, three or two numbers, then the corresponding sort 4, sort 3 or sort 2 sorting network is called that sorts the resulting sequence. The result is then returned and output by the function. b, The VarSort4 algorithm discovered by AlphaDev. This algorithm also receives sequences of length four, three or two numbers as input. In this case, if the length is two, then it calls the sort 2 sorting network and returns. If the length is three then it calls sort 3 to sort the first three numbers and returns. If, however, the length is greater than three, then it calls sort 3, followed by a simplified sort 4 routine that sorts the remaining unsorted number. It is this part of the routine that results in significant latency savings.

No sé si las palabras (o el gráfico) ayudan a entender bien de lo que estamos hablando pero, desde luego, nos dan una pista de cómo pequeños detalles pueden marcar una diferencia.

Se puede leer un texto de carácter más divulgativo en [AlphaDev discovers faster sorting algorithms ](https://deepmind.google/discover/blog/alphadev-discovers-faster-sorting-algorithms/)

