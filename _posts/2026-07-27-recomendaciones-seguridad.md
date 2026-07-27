---
layout: post
title: "Las inteligencias artificiales y sus recomendaciones"
date: "2026-07-27 14:00:00 +0000"
category: seguridad
tags:
- seguridad
- IA
- LLM
- consejos
- API
imagefeature: "https://live.staticflickr.com/2424/3699265044_962fae8d8d_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/3699265044/" title="Torre de Hércules y laberinto"><img src="https://live.staticflickr.com/2424/3699265044_962fae8d8d_z.jpg" width="640" height="427" alt="Torre de Hércules y laberinto"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Cualquiera que haya jugado un rato con una IA sabe que pueden convertirse en algo adictivo: nos aligera las tareas repetitivas, nos ayuda a resolver algunos problemas técnicos sin necesidad de leerse unos cuantos foros para ver cuál es la buena.... casi siempre.

En [Large Language Models (LLMs) Are Falling for Phishing Scams: What Happens When AI Gives You the Wrong URL?](https://www.netcraft.com/blog/large-language-models-are-falling-for-phishing-scams) nos recordaban que las recomendaciones no siempre son correctas y para comprobarlo hicieron un experimento.

Preguntaban dónde conectarse a algunas plataformas conocidas y las respuestas eran erróneas; no solo eso, ni siquiera estaban conectadas con el sitio al que pretendíamos ir en un 34% de las ocaciones.

> When Netcraft researchers asked a large language model where to log into various well-known platforms, the results were surprisingly dangerous. Of 131 hostnames provided in response to natural language queries for 50 brands, 34% of them were not controlled by the brands at all.

Esto era un problema relativo, porque en la mayoría de los casos (29%) eran dominios aparcados, no registrados o sin actividad y en un 5% de los casos eran negocios legítimos, pero incorrectos.

> 64 domains (66%) belonged to the correct brand.
> 28 domains (29%) were unregistered, parked, or had no active content.
> 5 domains (5%) belonged to unrelated but legitimate businesses.

Pero cualquiera que tenga interés por las cosas de las que solemos hablar aquí sabe cuál es el siguiente paso: alguien descubre estas direcciones, las registra, y solo le queda esperar a recolectar los frutos.

> Worse, many of the unregistered domains could easily be claimed and weaponized by attackers. This opens the door to large-scale phishing campaigns that are indirectly endorsed by user-trusted AI tools.

¿A quién afecta esto?
Fundamentalmente, los damnificados podrían ser los negocios y empresas más pequeñas (que, además, últimamente son los que tienen la web completamente abandonada echándose en los brazos de las redes sociales).

Sitios más pequeños tienen una menos probabilidad de estar incluidos en los conjuntos de datos de entrenamiento y, por lo tanto, son los que invitan a los LLMs a alucinar, inventándose algo que decir cuando no lo tienen en su información.

> These smaller players are less likely to appear in LLM training data, meaning hallucinations are more likely.

Podría suceder lo mismo con asistentes de programación, si alguien consigue contaminar sus datos con APIs falsas, que el asistente incluirá en nuestro código sin demasiados problemas.

> In another campaign, Netcraft uncovered a sophisticated effort to poison AI coding assistants. The threat actor created a fake API, SolanaApis, designed to impersonate a legitimate Solana blockchain interface. Developers who unknowingly included this API in their projects were, in reality, routing transactions directly to the attacker’s wallet. The malicious API was hosted on two hostnames: api.solanaapis[.]com and api.primeapis[.]com

Interesante.
