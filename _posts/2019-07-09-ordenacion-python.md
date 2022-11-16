--- 
layout: post
title: "Eficiencia en Python al ordenar"
date: "Tue Jul 09 15:05:01 +0100 2019"
category: desarrollo
tags: [python, list, lista, sort, ordenar, eficiencia, velocidad]
imagefeature: https://live.staticflickr.com/5511/11297420554_b1f920df87_b.jpg
---


<a href="https://www.flickr.com/photos/fernand0/11297420554" title="Velocidad"><img src="https://live.staticflickr.com/5511/11297420554_b1f920df87_b.jpg" width="240"  alt="Velocidad" style="float:left; margin:5px"></a>
Un artículo muy chulo comparando los métodos de ordenación en Python, que se puede leer en [list.sort() vs. sorted(list)](https://blog.usejournal.com/list-sort-vs-sorted-list-aab92c00e17). 

El primero es un método asociado a los objetos de tipo lista, y el segundo una función estándar para ordenar listas.

Vale la pena leerlo con calma para aprender un poco cómo hacer estas comparaciones, qué hay que tener en cuenta y todo eso. Pero para gente ansiosa, podemos decir que *list.sort* es algo más rápido y consume menos memoria. Tiene el inconveniente, eso sí, de que perdemos la lista original (porque reordena sobre la propia lista).
