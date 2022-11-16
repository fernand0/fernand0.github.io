--- 
layout: post
title: "Make y makefiles siguen siendo herramientas de actualidad"
date: "Sun Jul 19 15:02:01 +0100 2020"
category: desarrollo
tags: [desarrollo, programación, make, makefile]
imagefeature: http://live.staticflickr.com/124/415876029_297193f2cb.jpg
---


<a href="https://www.flickr.com/photos/fernand0/415876029/" title="Construcción "><img src="http://live.staticflickr.com/124/415876029_297193f2cb.jpg" alt="Construcción " width="240" style="float:left; margin:5px"></a>
Sigo manteniendo algunos viejos `Makefiles` de proyectos en C que sigo necesitando. Resuelven bien un problema concreto que es el de gestionar las dependencias entre ficheros que continen código y las bibliotecas que hay que generar a partir de ellas, en qué orden y qué es necesario compilar después de cambiar alguna parte del proyecto.

Por eso me gustó leer [The Language Agnostic, All-Purpose, Incredible, Makefile](https://blog.mindlessness.life/2019/11/17/the-language-agnostic-all-purpose-incredible-makefile.html) que aporta una visión actual del programa `Make` y cómo lo usa el autor.

Este programa existe desde 1976 y mucha gente piensa que ya está obsoleto:

> Make was born in 1976, making it one of the oldest tools in a programmer’s toolkit. Any tool that has been around this long is bound to have a mythology, stories, and examples that would be intimidating to someone unfamiliar with it. Additionally, I think many of us have written it off as no longer relevant, as we are not writing C programs, after all. Allow me to show you why it should not be intimidating, and furthermore, is applicable to your everyday workflow as an engineer.


El programa trabaja con objetivos, tiempos y reglas basadas en lo que se necesita para alcanzar esos objetivos:

> This section is just a summary of what we just arrived at. The properties of satisfaction for a target.

>    The target must exist.
>    The target’s timestamp must be newer than the timestamp of the target’s prerequisites.
>    The prerequisite targets must be satisfied.

Un buen recordatorio.

