---
layout: post
title: "Acceso a APIs, credenciales y uso desde clientes"
date: "2023-05-23 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- teléfono
- acelerómetro
- espionaje
- ataques
imagefeature: 'https://live.staticflickr.com/65535/52867697309_4cc0386695.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52867697309/" title="Vías, valla y cartelería "><img src="https://live.staticflickr.com/65535/52867697309_4cc0386695.jpg" alt="Vías, valla y cartelería " class="img-responsive img-centered"></a>

Las APIs permiten el acceso a nuestros programas (y, al final, a los datos) de manera alternativa a la tradicional de las interfaces web o mediante programas. Últimamente veo bastantes lecturas relacionadas con la seguridad. En parte, probablemente, porque al tratarse de accesos más controlados (o aparentemente más controlados) no siempre están tan bien aseguradas como deberían.

En [Quick way to Secure API Keys for the Frontend](https://dev.to/korconnect/quickest-way-to-secure-api-keys-on-the-frontend-1jcp) nos hablan de un problema interesante, que tiene que ver con el acceso a estas APIs a través de diversos frontales (*frontends*) y la gestión de las contraseñas (que pueden estar incluso en el código).

> We all know that API keys and connections can not be secured on the client side of an application. Hard coding API keys on the frontend is a quick and surefire way to have your API connection shutdown, API keys stolen, and have your API provider’s bill skyrocket. 

Hay formas de evitar exponer secretos de esta forma y las tres que proponen son:

- Funciones *serverless* que interactúan con algún servicio que gestiona las contraseñas (por ejemplo AWS Lambda).
- Funciones de Netlify. En este caso es un servicio, que interactuaría con el verdadero almacén (nuevamente AWS Lambda).
- Otro servicio, [KOR Connect](https://korconnect.io/) que permite gestionar los accesos sin que las credenciales aparezcan el código de nuestro frontal.

Igual es demasiado técnico (y orientado a productos) pero creo que nos puede ayudar a pensar en las nuevas necesidades que provoca hacer las cosas de una forma determinada.
