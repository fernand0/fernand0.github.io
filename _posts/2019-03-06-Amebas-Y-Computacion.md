--- 
layout: post
title: "Computación biológica y el problema del viajante de comercio"
date: "Wed Mar 6 15:05:01 +0100 2019"
category: algoritmia
tags: [algoritmia, viajante, comercio, tsp, problemas, biología, amebas]
imagefeature: https://farm6.staticflickr.com/5093/5428779311_780bd92543_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/5428779311" title="De viaje"><img src="https://farm6.staticflickr.com/5093/5428779311_780bd92543_m.jpg" width="240"  alt="De viaje" style="float:left; margin:5px"></a>
De vez en cuando nos salimos un poco más del tema y traemos alguna curiosidad. En este caso tiene que ver con amebas y problemas difíciles, de la mano de [An Amoeba-Based Computer Calculated Approximate Solutions to a Very Hard Math Problem](https://motherboard.vice.com/en_us/article/gy7994/an-amoeba-based-computer-calculated-approximate-solutions-to-a-very-hard-math-problem).

El problema difícil es el viejo conocido del viajante de comercio (*Travelling Salesman problem* TSP) y podemos hablar de computación biológica (y no la más habitual, que es la bioinspirada).
No se si vale la pena recordar que el problema consiste en determinar un recorrido óptimo para visitar una serie de ciudades volviendo a la de origen y pasando una vez por cada una. A pesar de lo sencillo que es describirlo, es un problema que es costoso de resolver de forma exacta cuando el número de ciudades crece.

Por lo visto las amebas son capaces de generar soluciones aproximadas al problema (recordamos aquí que cuando los problemas son difíciles -desde el punto de vista del coste, aclaro- nos conformamos con tener soluciones aproximadas suficientemente buenas).

> A team of Japanese researchers from Keio University in Tokyo have demonstrated that an amoeba is capable of generating approximate solutions to a remarkably difficult math problem known as the “traveling salesman problem.” 

Por lo visto, lo resuelven hasta 8 ciudades con una calidad de la solución bastante buena, en un tiempo que crece de manera lineal:

> Yet as these Japanese researchers demonstrated, a certain type of amoeba can be used to calculate nearly optimal solutions to the traveling salesman problem for up to eight cities. Even more remarkably, the amount of time it takes the amoeba to reach these nearly optimal solutions grows linearly, even though the number of possible solutions increases exponentially. 

Por lo visto, este tipo de amebas son capaces de expandir su cuerpo en varias direcciones en busca de alimento, lo que las hace particularmente interesantes:

> The reason this amoeba is considered especially useful in biological computing is because it can extend various regions of its body to find the most efficient way to a food source and hates light. 

¿Cuándo podremos usar esto? De momento son solo experimentos de laboratorio que podrían ser la base para construir computadores biológicos de bajo consumo energético.
Esto es, de momento, no.

> For now, however, the Japanese researchers’ experiment remains in the lab, but it provides the foundation for low-energy biological computers that harness the natural mechanisms of amoebas and other microorganisms to compute. 

