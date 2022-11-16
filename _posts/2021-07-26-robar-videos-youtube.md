---
layout: post
title: "Un ejemplo de interacción insegura entre sistemas seguros: YouTube"
date: "2021-07-19 15:00:00 +0000"
category: seguridad
tags:
- vulnerabilidad
- seguridad
- sistemas
- interacción
- youtube
imagefeature: 'http://live.staticflickr.com/2598/3755479278_18457cc702.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/3755479278/" title="Espectación audiovisual "><img src="http://live.staticflickr.com/2598/3755479278_18457cc702.jpg" alt="Espectación audiovisual " width="240" style="float:left; margin:5px"></a>
Hacer un sistema invulnerable es muy difícil. Hay personas muy ingeniosas que encontrarán formas de ir consiguiendo lo que quieren. En [Stealing Your Private YouTube Videos, One Frame at a Time](https://bugs.xdavidhu.me/google/2021/01/11/stealing-your-private-videos-one-frame-at-a-time/) David Schütz nos cuenta sus experimentos para tratar de ver vídeos privados del sitio. Estos vídeos son los que sólo puede ver el propietario o personas a las que se les de permiso de manera explícita.

> ... and Private, where only you can watch the video, or other accounts you’ve explicitly given permission to do so.

Después de intentarlo directamente, pensó que podría tratar de probar con otros servicios de Google, de forma que a través de ellos pudiera saltarse las protecciones (el típico caso en el que una herramienta confía en otra, más de lo que debería).

> A great thing to do in a situation like this, is to try to look for other products/services which are not your main target, but are somehow interacting with its resources internally. If they have access to its resources, it might be possible that they don’t have every level of protection that the main product has.

Y entre ellos encontró el servicio de anuncios (*Ads*) que, efectivamente, accede a los vídeos para poder seleccionar en qué momento es mejor mostrar la publicidad.

> It had an embedded player, some statistics, and an interesting feature called Moments. It allowed advertisers to “mark” specific moments of the video, to see when different things happen (such as the timestamp of when the company logo appears).

Siguiendo con la investigación descubrió una llamada para ver el pantallazo de un momento determinado.

> Looking at the proxy logs, every time I “marked a moment”, a POST request was made to a /GetThumbnails endpoint, with a body which included a video ID:

La prueba, entonces, era evidente: poner allí el identificador de un vídeo 'privado' y ver qué sucedía (pista: devolvía el pantallazo).

> I did what I did a bunch of times already, and replaced the ID to my second account’s Private video in the request, and to my surprise, it returned a base64 response!

Esto sólo es un pantallazo, claro, pero con esa información ver el vídeo completo es relativemente sencillo. Sólo hay que descargar una imagen cada 33 milisegundos del vídeo en cuestión.

> So I just have to download every image starting from 0 milliseconds, incrementing by 33 milliseconds every time, and then construct some kind of video using all of the images I have acquired.

Interesante, aunque seguro que todos están pensando que hace falta el identificador del vídeo (el mundo es imperfecto). Además, nos dice, no podremos escuchar el sonido y la resolución no será muy buena.

> In the real world you would have to know the ID of the target video. Mass-leaking those would be considered a bug on its own.

> Since these are just images, you can’t access audio.

> The resolution is very low. (but it’s high enough to see what is happening)

En todo caso, desde el punto de vista de la seguridad, logro conseguido. Y recordatorio de una vieja lección: sistemas seguros pueden interactuar entre sí de forma no tan segura. Y darle algún beneficio al atacante.

> The takeaway from this bug is that situations where two different products interact with each other under the hood are always a good area to focus on, since both product teams probably only know their own systems best, and might miss important details when working with a different product’s resources.

Una historia interesante.
