---
layout: post
title: "Principios de seguridad de Saltzer y Schroeder"
date: "Wed Nov 29 17:10:01 +0100 2017"
category: seguridad
tags: [seguridad, principios, leyes, saltzer, schroeder]
imagefeature: https://c1.staticflickr.com/3/2129/32458949350_cd2410fa6d_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/32458949350" title="Grabado en piedra"><img src="https://c1.staticflickr.com/3/2129/32458949350_cd2410fa6d_m.jpg" width="240"  alt="Grabado en piedra" style="float:left; margin:5px"></a>
Es bien conocida la frase de Groucho Marx: 'Estos son mis principios. Si no le gustan… tengo otros'. Sin embargo, los principios tiene su interés y utilidad como conceptos o valores que nos guían en el comportamiento: cuando nos enfrentamos a una nueva situación o nos movemos en terreno incierto, los principios nos pueden ayudar a tomar decisiones.

En ese sentido traemos hoy aquí [The Security Principles of Saltzer and Schroeder](http://emergentchaos.com/the-security-principles-of-saltzer-and-schroeder) que presentaron sus principios sobre protección de la información en sistemas informáticos. Serían:

* Economía en el mecanismo (tan simple y pequeño como sea posible).
* Fallo en modo seguro por defecto (si algo va mal, el sistema queda en un estado seguro).
* Mediación completa (para cada acceso a un objeto del sistema se debe comprobar la autorización).
* Mínimo privilegio (Cada agente debe tener los permisos necesarios para realizar su tarea, pero no más).
* Mínimo mecanismo común (no compartir estado entre diferentes agentes. Si alguien puede corromperlo, podrá influir en el comportamiento de los que dependan de él).
* Separación de privilegios (separar las acciones de manera que cada una tenga permiso para realizar la parte que sea necesaria para su actividad; evitar hacer una única pieza que tiene permiso para realizar las distintas tareas).
* Diseño abierto (el diseño no debería ser secreto o, al menos, su seguridad no debería depender de la ignorancia de los atacantes sobre sus internalidades).
* Psicológicamente aceptable (si las reglas no son razonables, será difícil que sean aceptadas y seguidas con cierto rigor).

El autor juega con los principios y la saga de 'Star Wars' así que puede valer la pena echarle un vistazo, más allá de los principios.
