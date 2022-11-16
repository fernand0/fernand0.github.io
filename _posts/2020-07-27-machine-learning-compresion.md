--- 
layout: post
title: "Machine Learning para elegir un método de compresión"
date: "Mon Jul 27 15:02:01 +0100 2020"
category: compresión
tags: [machine learning, compresión, decisiones]
imagefeature: http://live.staticflickr.com/4208/35074044982_8efb04dd16.jpg
---


<a href="https://www.flickr.com/photos/fernand0/35074044982/" title="Semáforos "><img src="http://live.staticflickr.com/4208/35074044982_8efb04dd16.jpg" alt="Semáforos " width="240" style="float:left; margin:5px"></a>
En el mundo de los programas 'inteligentes', una aproximación con una cierta tradición es aplicar esa inteligencia a la toma de decisiones cuando algunos parámetros pueden cambiar y probar todas las opciones es una tarea difícil o costosa.

De esto hablaba [shrynk - Using Machine Learning to learn how to Compress](https://vks.ai/2019-12-05-shrynk-using-machine-learning-to-learn-how-to-compress) aplicado al tema de la compresión de información (esto es, hacer que ocupe menos espacio). 
Hay muchos métodos de compresión y unos son mejores que otros cuando los datos tienen unas ciertas características:

> Different algorithms exist for different types of data, such as images, video, audio, but also text and general purpose files. Any data can be compressed as long as there is a pattern to use. 


Y el 'machine learning' es una buena herramienta de ayuda a la decisión. En este caso, se utilizan métodos ya conocidos de compresión y se evalúa su comportamiento frente a los datos disponibles.

> For each file, it will apply the compression and gather the values for each compression algorithm on size, write and read columns and converts them to z-scores: this makes them comparable at each dimension and is a novel approach as far as I know. The lowest sum of z-scores given the user weights gets chosen as a classification label. Let’s see that in slow-motion.

En lugar de decidir 'a mano' o por algún méitodo más costoso, este sistema permite elegir un método suficientemente bueno.

> Since having to come up with manual rules for when to use which compression would be very complex and time costly, this was a great case for machine learning. It’s very scalable, as when a new compression algorithm shows up on the market, shrynk will be able to benchmark that one and no new rules have to be figured out.

Curioso.
