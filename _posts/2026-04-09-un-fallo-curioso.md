---
layout: post
title: "Mensajes que misteriosamente no llegan"
date: "2026-04-09 14:00:00 +0000"
category: mensajes
tags:
- código
- protección
- seguridad
- fallos
- bugs
imagefeature: "https://live.staticflickr.com/2120/2442636467_4f8c7a19d8_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/27389497496/" title="Muros"><img src="https://live.staticflickr.com/7330/27389497496_73a8179e81_z.jpg" width="640" height="427" alt="Muros"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

A veces traemos fallos bastante sofisticados y hasta difíciles de seguir. En este caso...

En [Cracking The Dave & Buster’s Anomaly](https://rambo.codes/posts/2025-05-12-cracking-the-dave-and-busters-anomaly) nos hablan de uno verdaderamente curioso: si se envía un mensaje de audio en la aplicación *Messages*, el receptor también utiliza esa misma aplicación e incluye el nombre "Dave and Buster's", el mensaje nunca se recibirá.

> The bug is that, if you try to send an audio message using the Messages app to someone who’s also using the Messages app, and that message happens to include the name “Dave and Buster’s”, the message will never be received.

Nos cuenta cómo busca si es un error conocido y no encontrando explicaciones satisfactorias se puso a investigar por su cuenta.

El problema parece tener que ver con que el mensaje se transcribe:

> Something else you may have noticed is that when you send an audio message using the Messages app, the message includes a transcription of the audio.

Y el traductor lo convierte en una cadena con el carácter &:

> the transcription engine on iOS will recognize¹ the brand name and correctly write it as “Dave & Buster’s” (with an ampersand).

Pero este carácter tiene significado en HTML (y XHTML). El problema era que el traductor no tenía en cuenta este significado y no aplicaba los métodos de marcado adecuado para que no se interprete como parte de una etiqueta:

> The audio-transcription attribute includes the full transcription from the audio, and it clearly has the unescaped ampersand symbol.

En algún punto se detecta que ese código no está bien construido, falla y deja de procesar el mensaje.

> Since BlastDoor was designed to thwart hacking attempts, which frequently rely on faulty data parsing, it immediately stops what it's doing and just fails.

Como dice el autor, ¿es un fallo de seguridad?
Es posible que lo sea, pero en principio parece más bien lo contrario: una protección contra los problemas de seguridad que va más allá de lo necesario.

> On the surface, this does sound like it could be used to “hack” someone’s iPhone via a bad audio message transcription, but in reality what this bug demonstrates is that Apple’s BlastDoor mechanism is working as designed.

Interesante.
