---
layout: post
title: "Despliegue de URLs, interacción en Slack y sus riesgos"
date: "2024-10-14 15:00:00 +0000"
category: seguridad
tags:
- slack
- url
- unfurling
- desplegado
imagefeature: "https://www.flickr.com/photos/fernand0/53992811357/in/dateposted/"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/53992811357/in/dateposted/" title="Rocas y agua"><img src="https://live.staticflickr.com/65535/53992811357_e9aa00527f_z.jpg" width="427" height="640" alt="Rocas y agua"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

El desplegado de URLs (*unfurling*) tiene que ver con esas aplicaciones que cuando tienen una URL la descargan para mostrarnos una previsualización de la página. Se puede ver, por ejemplo, en redes sociales, pero en este caso nos hablan de Slack.

En [The dangers of AI agents unfurling hyperlinks and what to do about it](https://embracethered.com/blog/posts/2024/the-dangers-of-unfurling-and-what-you-can-do-about-it/) nos hablan del problema que esto puede supone cuando, por ejemplo, cuando un chatbot puede recibir a través de este proceso datos y generar un ataque de inyeción de preguntas (*prompt injection attack*).

> This becomes a threat in LLM (large language model) powered Chatbots and Slack Apps when untrusted data enters a chat, for instance via a prompt injection attack.

Podría ocurrir, por ejemplo, que un atacante provocara el desplegado de enlaces que contengan parte de algun de las conversaciones de nuestro Slack. Al hacer la consulta este contenido terminaría en el registro de actividad (*log*) del servidor.

> Now, during a prompt injection attack an attacker can cause rendering hyperlinks that contain past chat information in the URL (or other data that might be accessible), and Slack would send the data off to the third party server automatically.

La verdad es que parece un poco truculento, pero  ya sabemos que el diablo está en los detalles.

