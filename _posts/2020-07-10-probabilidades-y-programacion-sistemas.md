--- 
layout: post
title: "Teoría de la probabilidad y gestión de sistemas"
date: "Fri Jul 10 15:02:01 +0100 2020"
category: matemáticas
tags: [matemáticas, probabilidad, sistemas, fallos, errores]
imagefeature: 
---


<a href="https://www.flickr.com/photos/fernand0/15324955972/" title="Laplace "><img src="http://live.staticflickr.com/2942/15324955972_9750ce869e.jpg" alt="Laplace fue un matemático interesado en la estadística" width="240" style="float:left; margin:5px"></a>
La teoría de la probabilidad analiza aspectos como cuántas veces tiene que ocurrir un suceso para que se obtena un determinado resultado. Hechos poco probables deberían ocurrir pocas veces (que no significa que no puedan ocurrir) y el problema puede aparecer cuando 'damos muchas oportunidades' para que finalmente el hecho suceda.
En un sistema informático estamos continuamente 'tirando los dados': se trata de hacer muchas veces procesos repetitivos, para evitar tener que repetirlos nosotros a mano.
De esto nos hablaba [Some Useful Probability Facts for Systems Programming](https://theartofmachinery.com/2020/01/27/systems_programming_probability.html) centrándose en el caso de la programación de sistemas.

Por ejemplo, si en un servicio en línea hay una probabilidad de que suceda un incidente cada 20 días, la forma en que se distribuyan esos sucesos nos afectarán de manera desagradable e inevitable de vez en cuando.

> If an online service has a production incident once every 20 days on average, then (assuming unrelated incidents) just over a third of 20-day periods will be dead quiet, just over a third will have the “ideal” single incident, while a quarter of 20-day periods will be extra stressful. In the real world, production incidents are even more tightly clustered because they’re not always independent.

Lectura interesante.
