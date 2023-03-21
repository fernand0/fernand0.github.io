---
layout: post
title: "Sobre caminos mínimos en grafos con pesos negativos"
date: "2031-03-21 15:00:00 +0000"
category: algoritmia
tags:
- desarrollo
- algoritmia
- grafos
- investigación
imagefeature: 'https://live.staticflickr.com/65535/51852171116_497be8d5a6.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/51852171116/" title="Puente "><img src="https://live.staticflickr.com/65535/51852171116_497be8d5a6.jpg" alt="Puente " class="img-responsive img-centered"></a>
No suelo traer aquí con tanta frecuencia otros temas relacionados con mi trabajo (en particular, con mis clases) pero me gusta anotar algunas cosas y en esta ocasión le ha tocado a [Finally, a Fast Algorithm for Shortest Paths on Negative Graphs](https://www.quantamagazine.org/finally-a-fast-algorithm-for-shortest-paths-on-negative-graphs-20230118/) por varios motivos.

El problema de encontrar los caminos mínimos (de menor peso) en un grafo está resuelto hace mucho tiempo (año 1956 por Edsger Dijsktra) con una estrategia vorazsiempre que los pesos sean positivos. Sin embargo, la cosa se complica cuando permitimos que haya pesos negativos en el grafo. Tanto, que sigue siendo un problema a la espera de buenas soluciones.

La existencia de estas soluciones eficientes pueden hacernos pensar que ya no es interesante preocuparse de estos problemas. Sin embargo, de vez en cuando recibimos 'buenas' noticias, como en este caso: se ha publicado una solución [Negative-Weight Single-Source Shortest Paths in Near-linear Time](https://arxiv.org/abs/2203.03456) para el problema más general, que permite ejes de peso negativo.

Aunque dicen que es un algoritmo sencillo de explicar y de programar, conviene rdecir que hay que descomponer el grafo y utilizar técnicas de aleatorización. 
