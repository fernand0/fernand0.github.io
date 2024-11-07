---
layout: post
title: "La seguridad de esos servicios que utiliza y conoce poca gente"
date: "2024-11-07 15:00:00 +0000"
category: seguridad
tags:
- vulnerabilidades
- SQL
- seguridad
- fallos
imagefeature: "https://live.staticflickr.com/3026/3331367660_e282ee7ff8_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/3331367660/in/photolist-3ue5t-3ue5u-3zHAk-65o8xs" title="T2(.0)"><img src="https://live.staticflickr.com/3026/3331367660_e282ee7ff8_z.jpg" width="640" height="480" alt="T2(.0)"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

A veces la seguridad se basa en que el servicio es oscuro y utilizado por poca gente, y a la pregunta de '¿quién podría intentar atacar esto?' la respuesta es, efectivamente, 'nadie'. Pero en algunas ocasiones esta respuesta se transforma en 'casi nadie' y eso puede ser un problema.

De un caso de estos nos hablaban en <a href="https://ian.sh/tsa">Bypassing airport security via SQL injection</a> donde Ian Carroll y Sam Curry descubren que los sistemas que permiten aligerar el control para algunos de los usuarios más habituales de los aeropuertos (tripulaciones, fundamentalmente) utilizar mecanismos para ahorrarse las verificaciones que sufrimos el resto de los mortales.

El caso es que esto depende de un sistema que la TSA (Transportation Security Agency) subcontrata a otra empresa que no le pone el cariño suficiente a estas cosas y los investigadores descubren que tiene un API que no se preocupa de cosas tan básicas como las comillas en una petición de datos. Tirando del hilo, encuentran la forma de manipular los datos y algunas otros problemas más.

> We ended up finding several more serious issues but began the disclosure process immediately after finding the first issue.
