---
layout: post
title: "Vibe coding y programación asistida por LLMs"
date: "2026-01-14 14:00:00 +0000"
category: desarrollo
tags:
- desarrollo
- IA
- vibe coding
- LLM
imagefeature: "https://live.staticflickr.com/2276/2120779847_1d4961e0be_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/2120779847/" title="Agua y luz"><img src="https://live.staticflickr.com/2276/2120779847_1d4961e0be_z.jpg" width="480" height="640" alt="Agua y luz"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Estoy haciendo algunos experimentos con el denominado *vibe coding* y me parece bastante interesante: por un lado, se pierde la pereza a realizar determinados cambios que supondrían esfuerzo de mover código, renombrar cosas, ... porque la IA lo hace bastante bien; por otro, algunas veces se 'enganchan' en determinadas decisiones y si no tenemos cuidado podemos tener un pequeño monstruo en nuestras manos.
Además, desde siempre he reivindicado el verbo 'jugar' para aprender: en el sentido de probar cosas, hacer experimentos, ver qué sucede cuando cambiamos cosas...

Voy recopilando ideas en este hilo de X:

<blockquote class="twitter-tweet"><p lang="es" dir="ltr">De eso que te encuentras un código viejo y le das un remate. aunque no me convence la visualización. <a href="https://t.co/1BoLAuShy2">pic.twitter.com/1BoLAuShy2</a></p>&mdash; fernand0 (@fernand0) <a href="https://twitter.com/fernand0/status/1740405680295584155?ref_src=twsrc%5Etfw">December 28, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Pero hoy quería traer aquí al *experto oficial* del tema, Simon Willison, que no solo lo utiliza, hace recomendaciones y seguimiento de las novedades, sino que también aporta reflexiones y terminología. En [Not all AI-assisted programming is vibe coding (but vibe coding rocks)](https://simonwillison.net/2025/Mar/19/vibe-coding/) hablaba de *vibe coding*, un término acuñado por Andrej Karpathy,

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">There&#39;s a new kind of coding I call &quot;vibe coding&quot;, where you fully give in to the vibes, embrace exponentials, and forget that the code even exists. It&#39;s possible because the LLMs (e.g. Cursor Composer w Sonnet) are getting too good. Also I just talk to Composer with SuperWhisper…</p>&mdash; Andrej Karpathy (@karpathy) <a href="https://twitter.com/karpathy/status/1886192184808149383?ref_src=twsrc%5Etfw">February 2, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

La definición incluye la idea de que se trata de fluir con la IA y nuestras ideas, llegando a olvidar la existencia del propio código.

En este sentido, lo que decía arriba no sería *vibe coding* porque mis viejas costumbres me fuerzan en muchos casos a revisar, recolocar cosas, sugerir detalles a la IA... en definitiva, lo que hace un viejo programador (si es que puedo lamarme así) para asegurarse de que lo que le entrega la IA funcionará, podrá mantenerse y seguir desarrollándose en el futuro, tendrá las prestaciones adecuadas, accesibilidad, seguridad, coste razonable (aunque aquí, moviéndonos en el tiempo 'libre' a veces lo podemos descuidar).

> We need to create code that demonstrably works, and can be understood by other humans (and machines), and that will support continued development in the future.

...

> We need to consider performance, accessibility, security, maintainability, cost efficiency.

...

> We also need to read the code.

Pero, nos dice, no se trata de transformar el *vive coding* en un término peyorativo o un uso poco responsable de la tecnología, porque puede haber valor en ello.

> I don’t want “vibe coding” to become a negative term that’s synonymous with irresponsible AI-assisted programming either. This weird new shape of programming has so much to offer the world!

Todo el mundo, nos dice, debería poder automatizar tareas aburridas, y no debería ser necesario un informático para eso.

> I believe everyone deserves the ability to automate tedious tasks in their lives with computers. You shouldn’t need a computer science degree or programming bootcamp in order to get computers to do extremely specific tasks for you.

Y es posible que esta aproximación sea útil para mucha gente, que de otra forma no tendría acceso a estas comodidades.

> If vibe coding grants millions of new people the ability to build their own custom tools, I could not be happier about it.

Naturalmente, mucha de esa gente se llevará sustos y disgustos y no conseguirá lo que quería, pero también habrá gente que empezará a mirar lo que ha generado, aprenderá sobre ello y, tal vez, terminen siendo buenos desarrolladores.

> Some of those people will get bitten by the programming bug and go on to become proficient software developers.

La curva de aprendizaje es muy empinada al principio, pero las IAs son muy adeucadas para explicarnos lo que hace el código que han generado, y no se cansan nunca.

Por lo tanto, ¿qué deberíamos tener en cuenta?

- Proyectos de bajo riesgo: cuando algún fallo no vaya a producir problemas catastróficos o problemas de cualquier tipo.

> Projects should be low stakes. Think about how much harm the code you are writing could cause if it has bugs or security vulnerabilities.

- Atentos a la seguridad, cuidado con los secretos (contraseñas, identificadores, ..) y también a la privacidad.

- Ser un buen ciudadano de la red. Que nuestras pruebas no vayan a provocar algún problema en los servidores de alguien

> Be a good network citizen. Anything that makes requests out to other platforms could increase the load (and hence the cost) on those services.

- Cuidado con el coste. No será la primera vez que alguien se pone a programar ocn una herramienta de estas, se lía y termina teniendo una factura importante que pagar correspondiente al uso de la herramienta.

>  I’ve seen horror stories about people who vibe coded a feature against some API without a billing limit and racked up thousands of dollars in charges.

Finalmente nos hace algunas recomendaciones.

Fundamentalmente, hacer las pruebas con cuidado, no nos vayamos a cargar nuestros datos, nuestro sistema o cualquier otra cosa a la que tengamos acceso.
Habla de algunas herramientas, pero todavía no hay demasiado.

> Safe vibe coding for complete beginners starts with a sandbox.

¡A jugar!
