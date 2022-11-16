---
layout: post
title: "Más ataques a la privacidad: los 'faviconos'"
date: "2021-08-16 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- privacidad
- navegador
- favicon
- identificación
imagefeature: 'http://live.staticflickr.com/4338/37251899012_eeea0637df.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/37251899012/" title="Juan oculto "><img src="http://live.staticflickr.com/4338/37251899012_eeea0637df.jpg" alt="Juan oculto " width="240" style="float:left; margin:5px"></a>
Internet no se diseñó pensando en la privacidad. Esto hace que casi cualquier iniciativa en la red pueda ser usada para 'conocernos mejor'. En este caso, unos investigadores de la Universidad de Illinois (Chicago) nos hablaban de los 'faviconos': [Favicons may be used to track users](https://www.ghacks.net/2021/01/22/favicons-may-be-used-to-track-users/). Los 'faviconos' son esos dibujitos asociados a los sitios web que aparecen en la barra del navegador y también en los favoritos, en la barra del navegador....
Como siempre, y por motivos de eficiencia, se almacenan. El problema parece ser que no se almacenan con el resto de objetos temporales del navegador (*caches*).

> Favicons are used by site to display a small site icon, e.g. in the address bar of browsers that support it but also elsewhere, e.g. in the bookmarks or tabs. Favicons are cached by the browser, but are stored independently from other cached items such as HTML files or site images.

Los investigadores prepararon un sistemas para generar el almacenamiento de diferentes 'faviconos' según la navegación del usuario y, por lo tanto, mejorar las poosibilidades de identificar a un usuarios conforme se tienen más datos almacenados en su navegador.

> A single favicon is not enough to identify users based on it, but the researchers discovered a way to plant multiple favicons in the favicon cache. The site does a series of redirects through several subdomains to save multiple different favicons in the cache. Each saved favicon creates its own entry in the cache, and all of them together can be used to identify users provided that enough favicons are saved using the methodology.

Curioso.
