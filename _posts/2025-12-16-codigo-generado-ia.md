---
layout: post
title: "Alucinanciones de las Inteligencias Artificiales y sus consecuencias en el desarrollo de código"
date: "2025-12-16 14:00:00 +0000"
category: seguridad
tags:
- desarrollo
- IA
- alucinaciones
- paquetes
- cadena de suministro
imagefeature: "https://live.staticflickr.com/2348/2137644411_23bae9346f_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/2137644411/" title="¡Oh! ¡Qué bonito!"><img src="https://live.staticflickr.com/2348/2137644411_23bae9346f_z.jpg" width="640" height="480" alt="¡Oh! ¡Qué bonito!"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Tengo sentimientos enfrentados con el código generado por inteligencias artificiales. Por un lado, ando haciendo pruebas y me permite avanzar en cosas aburridas y que no haría por mi propia cuenta o me costaría esfuerzo abordarlas. Por otro lado, de vez en cuando me la lía y pierdo tiempo que podría estar dedicando a otras cosas.

<blockquote class="twitter-tweet"><p lang="es" dir="ltr">De eso que te encuentras un código viejo y le das un remate. aunque no me convence la visualización. <a href="https://t.co/1BoLAuShy2">pic.twitter.com/1BoLAuShy2</a></p>&mdash; fernand0 (@fernand0) <a href="https://twitter.com/fernand0/status/1740405680295584155?ref_src=twsrc%5Etfw">December 28, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

En [AI-generated code could be a disaster for the software supply chain. Here’s why.](https://arstechnica.com/security/2025/04/ai-generated-code-could-be-a-disaster-for-the-software-supply-chain-heres-why/) dan una visión pesimista, por losproblemas que pueden aparecer.

Nos habla de un estudio donde se observa como las IAs alucinan, y generan dependencias que no existen, por ejemplo. Eso no sería un problema salvo que alguien se de cuenta y las cree para nosotros: entonces nuestro código dependerá de algo que se ha creado a propósito para perjudicarnos.

> These non-existent dependencies represent a threat to the software supply chain by exacerbating so-called dependency confusion attacks. These attacks work by causing a software package to access the wrong component dependency, for instance by publishing a malicious package and giving it the same name as the legitimate one but with a later version stamp. Software that depends on the package will, in some cases, choose the malicious version rather than the legitimate one because the former appears to be more recent.

Estas alucinaciones, como sabemos, se corresponden con propuestas incorrectas generadas como respuesta a determinadas peticiones por la propia naturaleza de los LLMS.

> In AI, hallucinations occur when an LLM produces outputs that are factually incorrect, nonsensical, or completely unrelated to the task it was assigned.

Lo peor del caso es que en algunos casos esas alucinaciones se concentran en situaciones muy concretas, dando lugar a que sea relativamente sencillo concentrarse en estos casos y que todo sea más problemático.

> In other words, many package hallucinations aren’t random one-off errors. Rather, specific names of non-existent packages are repeated over and over. Attackers could seize on the pattern by identifying nonexistent packages that are repeatedly hallucinated. The attackers would then publish malware using those names and wait for them to be accessed by large numbers of developers.

**Actualización (2025-12-23)** En [LLMs can't stop making up software dependencies and sabotaging everything](https://www.theregister.com/2025/04/12/ai_code_suggestions_sabotage_supply_chain/) otro enlace donde hablan del tema.

