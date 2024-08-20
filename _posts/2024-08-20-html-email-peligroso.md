---
layout: post
title: "Los peligros del correo con HTML y CSS"
date: "2024-08-20 15:00:00 +0000"
category: seguridad
tags:
- correo
- HTML
- clientes
- riesgos
imagefeature: "https://live.staticflickr.com/2120/2442636467_4f8c7a19d8_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/2442636467/in/photolist-4HR9HR" title="Rimas populares"><img src="https://live.staticflickr.com/2120/2442636467_4f8c7a19d8_z.jpg" width="480" height="640" alt="Rimas populares"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Esta es una batalla perdida: yo mismo utilizo clientes de correo que lo interpretan y envío mensajes en HTML. Sin embargo, es bueno recordarlo, y de vez en cuando alguien lo hace. En [Kobold letters. Why HTML emails are a risk to your organization](https://lutrasecurity.com/en/articles/kobold-letters/) nos recordaban algunos aspectos relevantes.

Es un problema desde el punto de vista técnico, tanto de interpretación del mensaje, como desde el punto de vista de la seguridad, nos dice:

> Anyone who has had to deal with HTML emails on a technical level has probably reached the point where they wanted to quit their job or just set fire to all the mail clients due to their inconsistent implementations. But HTML emails are not just a source of frustration, they can also be a serious security risk.

En esta caso hablan de las llamadas **Kobold letters** que, esencialmente, tienen diferente aspecto cuando se reciben por primera vez; y cambian cuando son reenvíadas (*forward*).

> The email your manager received and forwarded to you was something completely innocent, such as a potential customer asking a few questions. All that email was supposed to achieve was being forwarded to you. However, the moment the email appeared in your inbox, it changed.

Esto se debe a la posibilidad de utilizar las hojas de estilo en cascada (*CSS*) y los cambios que se producen al reenviar un mensaje, que permiten activar reglas diferentes, que muestran alguna parte del mensaje que el receptor original no podía ver.

> This attack is possible because most email clients allow CSS to be used to style HTML emails. When an email is forwarded, the position of the original email in the DOM usually changes, allowing for CSS rules to be selectively applied only when an email has been forwarded.

Desde el punto de vista del usuario no hay mucho que podamos hacer (algunos clientes permiten ver HTML básico, sin estilo, o podemos desactivarlo completamente, pero entonces habrá correos que no podremos leer completamente).
Según nos cuentan en la historia, los diversos clientes toman medidas contra esto, dentro de sus posibilidades.
