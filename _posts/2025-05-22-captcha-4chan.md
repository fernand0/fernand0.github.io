---
layout: post
title: "Desentrañando los CAPTCHA de 4chan con una IA"
date: "2025-05-22 15:00:00 +0000"
category: seguridad
tags:
- CAPTCHA
- IA
- inteligencia artificial
imagefeature: "https://live.staticflickr.com/65535/54360107938_257f900cb2_z.jpg"
---
<a href="https://avecesunafoto.wordpress.com/2025/05/19/con-bicho/"><img src="https://i.imgur.com/hXUOysm.jpeg" title="Enmarañado" widht="640" alt="Imagen de un bicho entre una maraña de pelos de una planta"/></a>

Como hacía mucho que no escribíamos por aquí traigo una lectura de hace bastante tiempo, pero que tiene una (pequeña) dosis de actualidad por el reciente incidente que tuvo el sitio.

Comentaremos sobre [Breaking the 4Chan CAPTCHA](https://www.nullpt.rs/breaking-the-4chan-captcha) y la actualidad tendría que ver con su reciente caída ([How the Internet Left 4chan Behind](https://www.newyorker.com/culture/infinite-scroll/how-the-internet-left-4chan-behind)).

No vamos a hablar de la segunda parte, que es algo que no toca mucho aquí (salvo que nos cuenten los detalles técnicos, claro, que es algo que creo que no ha pasado todavía) sino de los CAPTCHAS y el caso de 4Chan. Como saben, se trata de un tablón donde la gente cuelga textos, fotografías, ... muchas veces de muy dudoso gusto y con un sesgo bastante descerebrado.

Ya hemos hablado (creo) de cómo las inteligencias artificiales pueden romper con cierta facilidad los CAPTCHAS, estos códigos ofuscados, que pretenden ayudar a las máquinas a discernir entre humanos y otras máquinas (por ejemplo, de pasada en [Las amenazas en los tiempos de la IA](https://fernand0.github.io/amenazas-tiempos-IA/), aunque una referencia más extensa podría ser [An Empirical Study & Evaluation of Modern CAPTCHAs](https://arxiv.org/abs/2307.12108)).

El caso es que el autor se propuso entrenar una IA (sí, hay gente que hace esas cosas, en lugar de utilizar las herramientas que nos 'dan' otros).
Los datos los obtuvo directamente de los retos que envía el sitio.

> I scraped several hundred CAPTCHAs in this manner - not enough to train the model, but it's at least a start. This still leaves us with a problem, though. We have all these CAPTCHAs, but we don't have the solutions. I could fill them out manually, but instead, let's try something else.

El problema ahora era resolverlos, para alimentar a su IA, aunque el problema, como ya anticipaban en el artículo de arriba es que los humanos no somos demasiado buenos con esos retos.

> Or, Humans are bad at solving the 4Chan CAPTCHA.

Se le podría pedir a un humano de confianza ayuda, pero se le ocurrió una idea mejor: ¿qué tal simular CAPTCHAS al estilo de los que tenía, pero con un contenido que él ya conocía?

> What if we could generate our own 4Chan CAPTCHAs? 4Chan, and the CAPTCHA it uses, are not open source, so I couldn't literally run the same code locally. But I could definitely approximate it.

Después, crear el modelo ya es una tarea más sencilla y el resultado no parece malo del todo.
Además, claro, el aprendizaje.

> I enjoyed this project a lot. It had a few challenges to overcome, and I learned a ton about machine learning and computer vision in the process. There are surely improvements that can be made, but for now, I'm pleased with the results, because I achieved what I set out to do from the start.

Interesante.
