---
layout: post
title: "Las amenazas en los tiempos de la IA"
date: "2024-08-12 15:00:00 +0000"
category: web
tags:
- protocolos
- web
- HTTP
imagefeature: "https://live.staticflickr.com/2204/1853829397_2fe702c8ba_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/1853829397/in/photolist-3PPmTP-Qkhzvb" title="eFindex: Enredados"><img src="https://live.staticflickr.com/2204/1853829397_2fe702c8ba_z.jpg" width="480" height="640" alt="eFindex: Enredados"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

El protocolo HTTP (*Hypertext Transfer Protocol*) es el que proporciona las bases fundamentales para la web. A mi me parece bastante interesante saber cómo funciona (aunque sea a nivel generalista) para comprender un poco mejor la web y por eso me gustó leer [HTTP/2 and HTTP/3 explained](https://alexandrehtrb.github.io/posts/2024/03/http2-and-http3-explained/).

Conviene recordar que la web, tal y como la conocemos se basa en un lenguaje para escribir documentos (HTML), un protocolo de transmisión (HTTP) y en una arquitectura cliente (el navegador) servidor (el que nos proporciona la información cuando nos conectamos).

El protocolo ha pasado por varias versiones, desde la HTTP/0.9, que fue el primer borrador hasta el más moderno, la versión 3 del protocolo (que apareció en 2012) que todavía no es de uso mayoritario (ver, por ejemplo, el dato de [Examining HTTP/3 usage one year on](https://blog.cloudflare.com/http3-usage-one-year-on), que tiene datos del año pasado).

Hacia el final nos recuerdan que HTTP/3 nació para dar mejor servicio a las conexiones menos estables, como los teléfonos móviles.

> HTTP/3 was designed for unstable connections, such as cellphone and satellite networks. To counter network instabilities, QUIC has a great degree of independence between the data streams and good resilience if packets are lost.

Así como las mejores prestaciones de la versión 2 del protocolo cuando las conexiones son estables.

> On reliable and stable connections, HTTP/2 many times offers better performance than HTTP/3.

