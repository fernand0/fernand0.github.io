--- 
layout: post
title: "Gestión de sistemas grandes distribuidos"
date: "Fri Nov 22 15:05:01 +0100 2019"
category: sistemas distribuidos
tags: [sistemas, distribuidos, complejidad, pistas, ideas, consejos]
imagefeature: https://live.staticflickr.com/2204/1853829397_2fe702c8ba_m.jpg
---

<a href="https://flickr.com/photos/fernand0/1853829397" title="Complejidad (moderada)"><img src="https://live.staticflickr.com/2204/1853829397_2fe702c8ba_m.jpg" width="240"  alt="Complejidad (moderada)" style="float:left; margin:5px"></a>
Una lectura interesante en [Operating a Large, Distributed System in a Reliable Way: Practices I Learned](https://blog.pragmaticengineer.com/operating-a-high-scale-distributed-system/) sobre la experiencia del autor, Gergely Orosz, en sistemas distribuidos.

Habla de temas como la monitorización, detección de anomalías, gestión de incidentes y muchos otros aspectos que alguien con poca experiencia en este tipo de sistemas podría pasar por alto (o aprender por la vída difícil).

Lo hace desde la experiencia de trabajar con el sistema de pagos de Uber y nos recuerda que cuanto más grande es el sistema, más probable es que se cumpla la máxima aquella de que 'si algo puede ir mal, irá mal'.

> The larger a system, the more Murphy's law of "what can go wrong, will go wrong" applies. This is especially true with frequent deploys, lots of developers deploying code, multiple data centers involved, and the system being used globally by a large number of users. 

Muy interesante.
