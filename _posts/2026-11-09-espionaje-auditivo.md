---
layout: post
title: "Canales laterales: el ratón como sustituto del micrófono para espiar"
date: "2026-11-09 14:44:36 +0200"
category: seguridad
tags:
- seguridad
- canal lateral
- espionaje
imagefeature: "https://live.staticflickr.com/3045/2841206310_deaa788e5e_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/2841206310/" title="Expo. Ratón"><img src="https://live.staticflickr.com/3045/2841206310_deaa788e5e_z.jpg" width="640" height="427" alt="Expo. Ratón"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Cuando vemos algún estudio interesante traemos aquí información acerca de esos métodos de extraer información que se basan en el comportamiento (físico, normalmente) de nuestros aparatos. Lo que se denomina canales laterales. En este caso, en [Invisible Ears at Your Fingertips: Acoustic Eavesdropping via Mouse Sensors](https://arxiv.org/abs/2509.13581), presentan un artículo donde detallan la idea de usar los sensores ópticos de un ratón, por su precisión y velocidad de respuesta, para detectar las vibraciones sonoras de la superficie donde se apoyan y usarlos para espiar al usuario.

> Modern optical mouse sensors, with their advanced precision and high responsiveness, possess an often overlooked vulnerability: they can be exploited for side-channel attacks.
> ...
> We demonstrate that audio signals can induce subtle surface vibrations detectable by a mouse's optical sensor.

Al final, se trata de hacer que el ratón se comporte como un micrófono: estos traducen las ondas sonoras en señales eléctricas por efecto del movimiento que provocan los cambios de presión sonora en la membrana.

> Microphones convert sound waves into electrical signals through diaphragm vibrations caused by air pressure changes.

En el caso de los ratones, sus sensores ópticos pueden detectar vibraciones en la superficie de manera similar a como lo hacen las membranas de los micrófonos.

> ... their sensors can detect surface vibrations similar to how a microphone’s diaphragm captures sound waves

Adicionalmente, hace falta que el equipo ejecute algún tipo de programa que capture la información para procesarla posteriormente y extraer el sonido.
La conclusión es que el ataque es factible y que, en algunos casos, se puede conseguir extraer sonido de calidad razonable.

Se pueden consultar más detalles y ver una demostración en [Mic-E-Mouse. Covert Eavesdropping through Computer Mice](https://sites.google.com/view/mic-e-mouse).
