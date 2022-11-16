---
layout: post
title: "Amazon. Elogio de los métodos formales"
date: "Tue Jul 5 17:30:01 +0100 2016"
category: desarrollo
imagefeature: https://c2.staticflickr.com/8/7399/26799157635_e9fcf3afd9_m.jpg
tags: [desarrollo, métodos formales, métodos, formales, model, checking, model checking, amazon, AWS]
---




<a href="https://www.flickr.com/photos/fernand0/26799157635" title="Bicho"><img src="https://c2.staticflickr.com/8/7399/26799157635_e9fcf3afd9_m.jpg" width="240"  alt="Bug" style="float:left; margin:5px"></a>
Cuando hablemos de métodos formales en informática enseguida nos tacharán de teóricos, alejados de la realidad y poco prácticos.
Tal vez sea así para programas sencillos y poco comprometidos, pero a partir de cierto nivel de complejidad una herramienta más siempre ayudará. En [How Amazon Web Services Uses Formal Methods](http://cacm.acm.org/magazines/2015/4/184701-how-amazon-web-services-uses-formal-methods/fulltext) (no se si está accesible públicamente, tal vez este sí que sea fácil de leer [[PDF] Use of Formal Methods at Amazon Web Services](http://research.microsoft.com/en-us/um/people/lamport/tla/formal-methods-amazon.pdf)).

En concreto nos hablan de modelos formales y 'model checking' para ayudar a rseolver problemas difíciles de diseño en sistemas críticos. Las herramientas estándar de la industria se quedan cortas en algunos casos:

>  We have found the standard verification techniques in industry are necessary but not sufficient. We routinely use deep design reviews, code reviews, static code analysis, stress testing, and fault-injection testing but still find that subtle bugs can hide in complex concurrent fault-tolerant systems. 

Las limitaciones de las pruebas ('testing'):

> We have found that testing the code is inadequate as a method for finding subtle errors in design, as the number of reachable states of the code is astronomical. 

Tampoco es que lo utilicen de manera extensiva, claro. Lo usan para encontrar fallos sutiles y también para mejorar la comprensión y la confinanza en las mejoras que aplican en unos cuantos sistemas:

> At the time of this writing, Amazon engineers have used TLA+ on 10 large complex real-world systems. In each, TLA+ has added significant value, either finding subtle bugs we are sure we would not have found by other means, or giving us enough understanding and confidence to make aggressive performance optimizations without sacrificing correctness. 

En varios equipos y con apoyo al máximo nivel:

> Amazon now has seven teams using TLA+, with encouragement from senior management and technical leadership. 

Yo creía que esto sólo les pasaba a los principiantes, pero parece que es algo común: nos centramos en los casos normales, sin pensar en que puede haber fallos y errores.

> Engineers naturally focus on designing the "happy case" for a system, or the processing path in which no errors occur. 

La forma de enfrentarse al problema: cómo debería funcionar, en lugar de pensar en lo que podría ir mal:

> We find this rigorous "what needs to go right" approach to be significantly less error prone than the ad hoc "what might go wrong" approach.

Para evitar fallos es necesario que todo el mundo comparta la misma visión del sistema, que debe ser correcta, ajustada, precisa, completa ...:

> To avoid creating subtle bugs, we need all engineers to have the same mental model of the system and for that shared model to be accurate, precise, and complete. 

Los métodos formales también tienen sus inconvenientes, claro: es difícil evaluar (al menos para ellos en este momento) los fallos que provocan degradación del sistema y que se realimentan:

> ... surprising "sustained emergent performance degradation" of complex systems that inevitably contain feedback loops

También se habla de la forma de comenzar, los aspectos 'sociales' (el lenguaje utilizado):

>  Engineers think in terms of debugging rather than "verification," so we called the presentation "Debugging Designs.

...

>  We initially avoid the words "formal," "verification," and "proof" due to the widespread view that formal methods are impractical.

¿Qué proporcionan los métodos formales?
Según los usuarios ayudan a obtener buenos diseños ('Get design right'), comprender mejor el sistema ('Gain better understanding') y también a escribir código mejor ('Write better code').

Lectura muy interesante.

