---
layout: post
title: "ChatGPT y el phishing: no está mal"
date: "2023-07-24 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- chatGPT
- plugins
- exfiltración
- LLM
imagefeature: 'https://live.staticflickr.com/65535/52674933470_fa683fdeac.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/52674933470/" title="Muro y decoración "><img src="https://live.staticflickr.com/65535/52674933470_fa683fdeac.jpg" alt="Muro y decoración " class="img-responsive img-centered"></a>

En [ChatGPT Plugins: Data Exfiltration via Images & Cross Plugin Request Forgery](https://embracethered.com/blog/posts/2023/chatgpt-webpilot-data-exfil-via-markdown-injection/) una mezcla de viejos y nuevos mecanismos de ataque.

Es una entrada curiosa, sobre los sitios que nos facilitan el acceso a la herramienta chatGPT, ofreciendo servicios añadidos.

Por un lado, los añadidos (*plugins*) pueden generar, por ejemplo, salida en un cierto formato (usan Markdown como ejemplo). Pero claro, una vez que el plugin tiene acceso a la información del usuario en la plataforma, puede aprovechar para extraer información adicional:

> The LLM’s response can contain markdown (or instruct the AI to build it on the fly), summarize the past conversation, URL encode that summary and append that as query parameter. And off it goes to the attacker.




