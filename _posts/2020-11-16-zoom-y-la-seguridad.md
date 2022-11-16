--- 
layout: post
title: "Análisis de amenazas de un sistema de cifrado entre extremos para videoconferencia"
date: "Mon Nov 16 15:02:01 +0100 2020"
category: videoconferencia
tags: [videoconferencia, cifrado, extremos, zoom, análisis, amenazas]
imagefeature: https://i.imgur.com/j9EHwJG.jpg
---

<a href="https://avecesunafoto.wordpress.com/2020/07/27/camara-2/" title="Cámara"><img src="https://i.imgur.com/j9EHwJG.jpg" alt="Cámara" width="240" style="float:left; margin:5px"></a>
Zoom ha sido uno de los vencedores de la pandemia. Es una plataforma de videoconferencias sencilla de usar, que funciona bastante bien (casi todas hoy en día, esa es la verdad) y que para mucha gente ha sido un verdadero hallazgo.

En  [Trusting Zoom?](https://www.cs.columbia.edu/~smb/blog/2020-04/2020-04-06.html) que no me importan tanto por la plataforma en sí, sino por el análisis que hace de algunas prevenciones que se comentaron durante el inicio de la pandemia. Ya digo que algunas cosas habrán cambiado (y sigue habiendo polémicas sobre la plataforma, al máximo nivel [Zoom lied to users about end-to-end encryption for years, FTC says](https://arstechnica.com/tech-policy/2020/11/zoom-lied-to-users-about-end-to-end-encryption-for-years-ftc-says/)).

Lo primero que dice es que, a pesar de los puntos débiles, la plataforma proporciona un servicio con unos beneficios tan importantes en aquel momento que superarían los inconvenientes, salvo que perjudicasen notablemente a alguien:

> In other words, the benefit of using Zoom is considerable, and I have an ethical obligation to do it unless the risks to me, to my students, or to the university are greater. 

Prefiere la aplicación porque no se fía de los navegadores:

> My reasoning for not using the browser option is a bit different: I don’t trust browsers enough to want one to have the ability to get at my camera or microphone.

Sobre todo porque cualquier fallo le pondría en un compromiso sólo cuando utilizara la aplicación y no el navegador, que lo usa mucho más:

> But apart from my serious privacy reservations, flaws in the Zoom app put me at risk while using Zoom, while flaws in a browser put me at risk more or less continuously. 

Sus clases, al final son públicas (para su audiencia, e incluso cuelga materiales de manera pública)

> But apart from my serious privacy reservations, flaws in the Zoom app put me at risk while using Zoom, while flaws in a browser put me at risk more or less continuously. 

Y luego se pregunta si las debilidades de Zoom son suficientemente importantes para evitar su uso:

>  Are Zoom’s weaknesses sufficiently serious that my university—and I—should avoid it?

Sobre los métodos criptográficos utilizados, sin ser los mejores, parecen suficientes para lo que se está haciendo:

> That’s already a substantial part of the answer: I’m not worried about the Andromedan cryptanalysts trying to learn about my students’ personal tragedies. Yes, I suppose in theory I could have as a student someone who is a person of interest to some foreign intelligence agency and this person has a problem that they would tell to me and that agency would be interested enough in blackmailing this student that they’d go to the trouble of cryptanalyzing just the right Zoom conversation—but I don’t believe it’s at all likely and I doubt that you do. 

Por otra parte, ese atacante tendría que tener acceso de alguna forma al tráfico de la red:

> There’s another part of the puzzle for a would-be attacker who wants to exploit this flaw: they need access to the target’s traffic. [...] Routing attacks don’t require a government-grade attacker, but they’re also well up there on the scale of abilities. 

Por lo que atacar y sacar partido del cifrado entre extremos sería algo complejo:

> What it boils down to is this: exploiting the lack of true end-to-end encryption in Zoom is quite difficult ...

Finalmente, destaco que el autor trata de hacer todo su contenido académico público, así que tampoco teme los robos. Puede haber excepciones:

> Nothing that I personally do would seem to meet that first criterion—I try to make all of my academic work public as soon as I can—but there are some plausible university activities, e.g., development of advanced biotechnology, where there could be such governmental interest. 

Como decía, me pareció una lectura interesante.
