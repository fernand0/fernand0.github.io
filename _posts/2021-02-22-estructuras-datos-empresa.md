---
layout: post
title: Algunas estructuras de datos y algoritmos usados en casos reales
date: 2021-02-22 15:00:00 +0000
category: algoritmia
tags:
- algoritmia
- estructuras
- datos
- empresas
- mundo
- real
imagefeature: 'http://live.staticflickr.com/2222/2522548420_08da32b854.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/2522548420/" title="Tricas Invaders... "><img src="http://live.staticflickr.com/2222/2522548420_08da32b854.jpg" alt="Tricas Invaders... " width="240" style="float:left; margin:5px"></a>
En estos tiempos la palabra algoritmo cotiza a la baja: se ha asimilado a decisiones que toma una máquina por nosotros con poca transparencia (ese tufo anti-tecnológico permamente que padecemos). Sin embargo, tan algoritmos es el de la suma como esos otros 'malvados'.
En las clases de algoritmia se explican estrutcturas de datos y algoritmos a los que no siempre se les ve sentido (aunque siempre recordaré a un estudiante que ya tenía su *startup* y todo y cómo estas clases le abrieron un poco los ojos a lo que era pensar los programas, más allá de resolver su problema).
En [Data Structures & Algorithms I Used Working at Tech Companies](https://blog.pragmaticengineer.com/data-structures-and-algorithms-i-actually-used-day-to-day/) nos habla Gergely Orosz de este tema: estructuras de datos y algoritmos que realmente ha utilizado en empresas tecnológicas.

Habla de los árboles y su recorrido (*Trees and tree traversing*) que utilizó en Skype y en  Uber, por ejemplo. Fundamentalmete, parece, para temas de navegación.

> Trees and tree traversing: Skype, Uber and UI frameworks

Grafos con pesos y caminos mínimos (*Weighed graphs and shortest paths*) en Skyscanner. Al tener que calcular precios de rutas que pasan por distintas ciudades el problema se resulve como un camino mínimo a través de un grafo.

> Multi-city was one of the features that took Skyscanner quite a bit of time to build - in all fairness, the difficulty was more on the product side, than anything. The best multi-city deals are calculated by using shortest path algorithms ... 

Ordenación en Skype. Tenemos una lista de contactos, que además pueden llegar en lotes.

> One of the other engineers decided to implement an insertion sort for listing contacts. In 2013, when Skype connected to the network, contacts would arrive in bursts, and it would take some time for all the contacts to arrive. So this engineer thought it's more performant to build the contact list organized by name, using insertion sort. 

Diccionarios (*Hashtables and hashing*) en muchos sitios. Muy útiles para contar, detectar duplicados... 

> The most frequent data structure I've used regularly was hashtables and the hashing function. It's such a handy tool from counting, to detecting duplications, to caching, all the way to distributed systems use cases like sharding. After arrays, it's easily the most common data structure

Pilas y colas (*Stacks and queues*), de vez en cuando. Se trata de buenas herramientas auxiliares.

Criptografía en Uber. Los usuarios siempre nos proporcionan información que puede ser delicada y que hay que tratar adecuadamente.

> User-entered sensitive information coming from mobile or web clients needs to be encrypted before sending through the network, only to be decrypted on a specific service. To do so, a crypto approach needs to be implemented on the client and the backend.

Árboles de decisión en Uber. Cuando nuestra aplicación se hace más compleja, puede ser necesario elegir qué mostrar en función de algunas reglas.

> On one of the projects, we had to implement complex business logic in the mobile application. Based on half a dozen rules, we had to display one of several different screens

Mallas hexagonales e índices jerárquicos, también en Uber. Hay que optimizar los precios de los viajes, y el envío de coches, que es algo que se puede resolver con mallas hexagonales y la adecuada jerarquización.

> The data - and visualization - structure for this is a hexagonal grid with hierarchical indexes, and a couple of internal visualization tools are built on top of it. 

Interesante.
