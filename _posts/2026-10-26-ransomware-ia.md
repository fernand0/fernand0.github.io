---
layout: post
title: "Una IA para generar un secuestro de información completo"
date: "2026-10-26 14:44:36 +0200"
category: seguridad
tags:
- seguridad
- IA
- ransomware
imagefeature: "https://live.staticflickr.com/65535/54174894032_036e515aa3_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/54174894032/" title="Robot guitarrista"><img src="https://live.staticflickr.com/65535/54174894032_036e515aa3_z.jpg" width="427" height="640" alt="Robot guitarrista"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Hasta ahora hemos oído hablar de cómo se usa la IA para mejorar las oportunidades de los ataques tipo *phishing* con mejores traducciones, mensajes más convincentes y todo eso.
En [Experimental PromptLock ransomware uses AI to encrypt, steal data](https://www.bleepingcomputer.com/news/security/experimental-promptlock-ransomware-uses-ai-to-encrypt-steal-data/) nos contaban un caso que va un poco más allá, porque PromptLock sería una demostración de la posibilidad de usar una IA para generar los programas de ataque:

> The malware uses OpenAI’s gpt-oss:20b model through the Ollama API to dynamically generate the malicious Lua scripts from hard-coded prompts.

Por lo que nos dicen se trata simplemente de una 'demo' o una prueba de concepto.

> The cybersecurity company believes that PromptLock is a proof-of-concept or work in progress, and not an active ransomware in the wild.

El proyecto parece tener varios 'padres'.

> After ESET published details about PromptLock, a security researcher claimed that that the malware was their project and somehow it got leaked.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">#ESETResearch has discovered the first known AI-powered ransomware, which we named #PromptLock. The PromptLock malware uses the gpt-oss:20b model from OpenAI locally via the Ollama API to generate malicious Lua scripts on the fly, which it then executes 1/6 https://t.co/wUZS7Fviwi</p>&mdash; ESET Research (@ESETresearch) <a href="https://x.com/ESETresearch/status/1960365364300087724?ref_src=twsrc%5Etfw">August 26, 2025</a></blockquote>
<script async src="https://platform.x.com/widgets.js" charset="utf-8"></script>

Y también, uno académico, sobre el que se puede leer en [Large language models can execute complete ransomware attacks autonomously, NYU Tandon research shows](https://engineering.nyu.edu/news/large-language-models-can-execute-complete-ransomware-attacks-autonomously-nyu-tandon-research).

> Researchers from the NYU Tandon School of Engineering have reached out to point out that PromptLock seems to have been directly derived from their project, called "Ransomware 3.0." They also published a blog post explaining the connection here.


