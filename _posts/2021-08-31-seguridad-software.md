---
layout: post
title: "Desarrollo seguro: algunas piezas sobre las que construir"
date: "2021-08-31 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- desarrollo
- procesos
imagefeature: 'http://live.staticflickr.com/2044/1557977187_7383ad79f1.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/1557977187/" title="Teruel. Torre mudéjar. "><img src="http://live.staticflickr.com/2044/1557977187_7383ad79f1.jpg" alt="Teruel. Torre mudéjar. " width="240" style="float:left; margin:5px"></a>
En [Applying Software Security to Security Software](https://aaronbedra.com/post/securing_security_software/) utiliza la excusa de la seguridad del software de seguridad (mucha seguridad, pero ya hemos dicho varias veces como sorprende muchas veces que los programas informáticos de las empresas de seguridad fallan muchas veces, igual que los otros, en estos aspectos). Todo a raíz del descubrimiento de un fallo en `sudo`.

> When it comes to software security, the devil is in the details. When it comes to security software, those details are even more important. Just recently a significant bug was found in sudo, demonstrating that even the most highly scrutinized software can still contain mistakes. 

En este paso parece que es evidente que no habría que justificar mucho un mayor coste, en aras de tener una mejor seguridad.

> Arguably, security software is one of the easier places to justify spending more time on software security. 

Y luego pasa a enumerar una lista de recomendaciones, que empieza con las dependencias: tenemos que estar seguros de que nuestros programas no dependen de otros que tienen vulnerabilidades.

>  Getting Familiar With Dependencies

> The first thing to do is check up on our dependencies to make sure there aren’t any issues.

Y el camino a seguir es actualizar siempre que sea posible. La razón es que si no estamos actualizados podríamos tener problemas de compatibilidad cuando aparezca alguna actualización de seguridad.

> Keeping up with dependencies should be a first class concept in your SDLC. In reality, you should update your dependencies as often as possible. If you only wait for security issues to update dependencies, you could be left with expensive upgrade paths that touch code that has long since fallen out of context with your team. 

Igualmente, deberíamos utilizar una versión actualizada del lenguaje.

>  An Updated Language Version 

También deberíamos tener pruebas (`tests`), no se si vale la pena explicarlo mucho.

>  Adding Tests 

Baste decir que asegurar el funcionamiento correcto de nuestro programa forma parte de la seguridad.

> It turns out functioning correctly is also a part of Software Security.

Finalmente, habla de medir los resultados y procedimentar lo que hacemos.

> I  do think it’s worth mentioning that part of Software Security is grounding your work and making sure you’re applying methods that map to measurable outcomes.

Sin olvidar que hay que pensar bien lo que se hace, para poder refactorizar y obtener productos robustos y sólidos.

> Part of applying software security is arriving at a model that allows the full expression of the domain, including invariants, and nothing more. This is much more difficult than it sounds. It takes thought, several rounds of refactoring, and good old fashioned discipline. Before we crack into our code it is important to expose a better model that we can refactor into. 

