---
layout: post
title: Complejidad y diseño de sistemas seguros
date: 2021-05-17 15:00:00 +0000
category: seguridad
tags:
- desarrollo
- seguridad
- complejidad 
- historia
- libros
imagefeature: 'http://live.staticflickr.com/421/31152325993_9321c190d2.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/31152325993/" title="Defensa "><img src="http://live.staticflickr.com/421/31152325993_9321c190d2.jpg" alt="Defensa " width="240" style="float:left; margin:5px"></a>
He estado leyendo un libro que me ha parecido interesante: [This Is How They Tell Me the World Ends: The Cyberweapons Arms Race](https://fotografiasenmovimiento.wordpress.com/2021/03/19/libro-recibido-this-is-how-they-tell-me-the-world-ends-the-cyberweapons-arms-race/).
No voy a hacer una reseña, pero sí que recomiendo su lectura porque es una aproximación interesante y fácil de leer de la historia reciente que nunca se cuenta (al menos en nuestro entorno, donde el periodismo tecnológico está orientado a las novedades comerciales y al miedo a la tecnología en sus diversas vertientes) en los aspectos relacionados con el mercado de los fallos de día cero *zero days* y cómo los diversos agentes han estado interactuando con los expertos para conseguirlos y utilizarlos con obejtivos diversos.
Es un libro escrito por Nicole Perlroth y que ha trabajado con un montón de fuentes para traernos esta información.
Se puede leer una (bastante critica, casi me desanimó de comprar el libro) en [ Book Review: "This Is How They Tell Me the World Ends" ](https://addxorrol.blogspot.com/2021/02/book-review-this-is-how-they-tell-me.html) pero estaba muy bien 'puntuado' en diversos sitios, así que me decidí.

En uno de los capítulos se habla del tema de la seguridad en los programas informáticos y se aporta información interesante sobre la complejidad de los programas y cómo influye en su seguridad (y en nuestra capacidad de estar seguros de que no hacen algo malo, si los examinamos). 
Tradicionalmente se ha dicho (es fácil encontrar referencias) que la complejidad hace más difícil asegurar los programas.
En este caso se habla de una complejidad muy sencilla (el tamaño) y aún así, se ve que la cosa no pintaba bien.

En particular se habla de [Penetrate, Exploit, Disrupt, Destroy: The Rise of Computer Network Operations as a Major Military Innovation](http://mars.gmu.edu/handle/1920/10613) que se puede descargar en PDF. 

Allí se describen los experimentos CHAPERON 1 y CHAPERON 2, como ejercicios para determinar si era posible diseñar aplicaciones seguras. También si era posible que alguien insertase código malicioso en una aplicación sin que los defensores pudieran detectarlo. 
Nos cuentan como se diseñaron dos equipos (atacantes y defensores). Estos últimos, sabiendo que algo peligroso había, debían encontrarlo. En el primer experimento, uno de los atacantes implantó dos trozos de código malicioso, que nadie encontró.

> In time, based on the knowledge he acquired examining software/hardware interfaces and the residual vulnerabilities the use of microelectronics and microcontrollers engender, Gosler convinced Sandia management to perform proof of principle technical studies that came to be known as the CHAPERON 1 and CHAPERON 2 exercises. The premises of the CHAPERON exercises were simple: Can a person design a secure application? Can a person insert malicious constructs that are not detected even through detailed evaluation? Two groups were created as part of the study: Group 1 was designated as Subverters and Group 2, which consisted of two subteams of evaluators, was responsible for uncovering the subversion. As a practical matter, the design of the exercise purposefully provided all advantages to the Evaluator: The subverter would inform evaluators that one or two vulnerabilities were placed in a system, within certain parameters and constraints, and provide them comprehensive system documentation. Gosler was designated as a subverter and immediately set out to undermine a specific security-critical application. As part of the study, he created a "Guideline for Subversive Software Development" to outline principles for subversion design and implementation, which included prohibitions against the use of extraneous code: Any code utilized must have a justifiable reason for being a part of the system, and the subversive design could not compromise the encryption algorithm. Through a painstaking trial-and-error process, Gosler developed and implanted two subversions in the system which none of the evaluators were able to find: (1) the insertion of Zork text which revealed secret system variables, and (2) another subversion. 

Tanto es así, que mostrar los fallos y explicarlos llevó un buen número de horas.
La segunda parte del experimento se diseñó con más limitaciones (692 líneas de lenguaje máquina) y sólo uno de ellos pudo encontrar el nuevo problema.

> The Sandia evaluation team spent several months examining the doctored system, to no avail. In fact, it took three 8-hour-long days of briefing the evaluators on how the subversive design worked. Gosler initially planned to train future Sandia evaluators to uncover the more complicated subversion using the CHAPERON 1 exercise as a teaching tool, but the subversion he created was so complicated that no one could solve it and led the evaluators to become extremely frustrated. This required the creation and development of the CHAPERON 2 exercise, which was designed to be less complex. 423 Sandia employee Tom Barger created the follow-on exercise as the subverter, which was severely limited to 692 machine-level instructions. Close to 100 people were given an opportunity to be evaluators of the subversion, but only Gosler successfully identified the exploit (although a couple other evaluators came very close to discovering the exploit), which was a spoofed code execution sequence embedded in a particular machine instruction.

Así las cosas, y ya teorizando, se preguntaban cuántas líneas de código podria tener un programa para estar razonablemente seguros de que hacía lo que se suponía que tenía que hacer. Los que no conocían el experimento hablaban de 10000.

> The CHAPERON 2 exercise came to the attention of Rick Proto, and Robert Morris Sr., Chief of Research and Chief Scientist at NSA National Computer Security Center respectively (among others in the IC), who thought these exercises were insightful and could be helpful. Upon meeting, Gosler asked Morris, “How complex can software be for you to have total knowledge of what it would do?” Morris replied, "100% confident at 10,000 machine level instructions or less. We would have no confidence at more than 100,000 machine level instructions."  Immediately after this interaction, Gosler shared the subversion he created for the CHAPERON 1 exercise with Morris and Proto. Clearly, the implications of what Gosler achieved in the CHAPERON exercises was not lost on NSA technical leadership, and their assumptions about their abilities to detect subversions in computer hardware and software interfaces would need to be adjusted accordingly.

Después de esto, la NSA pudo ver que con sus recursos no tenía capacidad para cumplir con su cometido y empezó a contratar más personal, pero esto ya es otra historia.
