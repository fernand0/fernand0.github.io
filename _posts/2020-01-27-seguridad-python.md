--- 
layout: post
title: "¿Puedo tener problemas de seguridad utilizando Python? Puedo tener problemas de seguridad utilizando Python"
date: "Mon Jan 27 15:05:01 +0100 2020"
category: seguridad
tags: [programación, python, seguridad, lenguajes, consejos]
imagefeature: https://live.staticflickr.com/1570/25026996146_72dbf4fffa_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/25026996146" title="Serpiente"><img src="https://live.staticflickr.com/1570/25026996146_72dbf4fffa_m.jpg" width="240"  alt="Serpiente" style="float:left; margin:5px"></a>
No se suele hablar mucho de la seguridad en los lenguajes que se consideran más o menos seguros. Nada hay como el C y otros para meter la pata y tener problemas; pero eso no impide que tengamos que tener en cuenta algunas cosas y de eso hablaban en [10 common security gotchas in Python and how to avoid them](https://medium.com/hackernoon/10-common-security-gotchas-in-python-and-how-to-avoid-them-e19fbe265e03).

Empieza hablando de que cuando aprendemos a programar aprendemos cómo se supone que debe usarse un lenguaje o lo que sea; sin embargo, cuando hablamos de seguridad tenemos que cambiar a  pensar en cómo podría ser usado para conseguir algo malo.

> ... you learn how it supposed to be used. When thinking about security, you need to think about how it can be misused

Y, claro, aunque hablemos de lenguajes seguros, algunas cosas malas siguen siendo posibles. La lista:

* Inyección de entrada
* Problemas al analizar XML
* Instrucciones 'assert'
* Ataques basados en el tiempo
* Paquetes maliciosos o el lugar desde donde se importan
* Ficheros temporales
* Problemas al cargar ficheros YAML
* Datos serializado
* Problemas del entorno Python por no estar actualizado
* Problemas por no tener actualizadas las dependencias

Como puede verse, algunos son bastante específicos (aunque casi todos aplicables a diversos lenguajes) pero otros son completamente genéricos.

En todo caso, un buen repaso generalista.
