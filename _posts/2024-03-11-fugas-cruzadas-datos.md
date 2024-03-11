---
layout: post
title: "XS-Leaks. XSS para extraer información sobre los usuarios"
date: "2024-03-11 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- XSS
- leaks
- fugas
imagefeature: https://live.staticflickr.com/5300/5543123497_a07b6243c9_o.jpg
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/5543123497/in/photolist-rafGFd-rcsuk1-9rPXuM-9C1YtF" title="Centro de Exposiciones del Centro de Conocimiento sobre servicios públicos electrónicos. Almacenamiento."><img src="https://live.staticflickr.com/5300/5543123497_a07b6243c9_o.jpg" width="2048" height="1536" alt="Centro de Exposiciones del Centro de Conocimiento sobre servicios públicos electrónicos. Almacenamiento."/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En [Introduction to Cross-Site Leaks (XS-Leaks) – Attacks and Mitigations](https://cybercx.co.nz/blog/cross-site-leaks-attacks/) hay una introducción a este ataque, que sirve para recolectar información acerca de los usuarios, a través de fallos de programación cruzada (*Cross-site scripting (XSS)*) y la utilización estos fallos para acceder a información como atributos de los usuarios, permisos, papeles (*roles*). Y también al historia de palabras de búsqueda y otras informaciones que se almacenan en memorias temporales (*caches*).

> XS-Leaks then allow attackers to collect information about website visitors that is usually not available. This information can give the attacker clues about the user’s identity. This can include if the victim is logged into other web applications allowing access to user attributes, permissions, or roles. Additionally, a victim’s keyword search history can be queried as well as privately cached browser objects, such as images, based on how the website caches these resources.

Interesante.
