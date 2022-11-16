---
layout: post
title: "Se lo que escribiste en tu última videoconferencia"
date: "2021-10-04 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- videoconferencia
- teclado
- observación
- cámara
- imagen
imagefeature: 'https://live.staticflickr.com/2378/1553218800_7e1412bf8c.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/1553218800/" title="Teclado flexible "><img src="https://live.staticflickr.com/2378/1553218800_7e1412bf8c.jpg" alt="Teclado flexible " width="240" style="float:left; margin:5px"></a>
Cuando estamos en una videoconferencia mucha gente dedica su tiempo a realizar otras actividades, además de participar más o menos activamente en la reunión. Se hace con cierta ligereza, porque estamos bastante seguros de que nadie sabrá lo que ocurría. A veces, hay accidentes, como que tenemos el sonido abierto y se escucha el teclado, nuestros comentarios, ...

En [Experts Find a Way to Learn What You're Typing During Video Calls](https://thehackernews.com/2021/02/experts-find-way-to-learn-what-youre.html) nos cuentan cómo se puede extraer cierta información de los movimientos corporales mientras tecleamos.

> A new attack framework aims to infer keystrokes typed by a target user at the
opposite end of a video conference call by simply leveraging the video feed to
correlate observable body movements to the text being typed.

Nada impide que esto se haga con vídeo en directo, sino que alguien podría procesar vídeos disponibles por ahí y tratar de averiguar lo que sucedía.

> ... who say the attack can be extended beyond live video feeds to those
streamed on YouTube and Twitch as long as a webcam's field-of-view captures
the target user's visible upper body movements.

Casi nada que hacemos está aislado completamente, así que se puede tratar de decucir palabras teniendo en cuenta lo que ha sucedido anteriormente y posteriormente.

> Word prediction, where the keystroke frame segments are used to detect motion features before and after each detected keystroke, using them to infer specific words by utilizing a dictionary-based prediction algorithm

Si escribimos mirando al teclado y buscando las teclas, y además llevamos ropa sin mangas, será más fácil ver lo que estamos haciendo, nos dicen.

> The findings showed that hunt-and-peck typers and those wearing sleeveless
clothes were more susceptible to word inference attacks

Si tenemos información adicional sobre la actividad del usuario, todavía es más fácil tener éxito. Por ejemplo, nombres de usuarios, correos electrónicos...

> The tests were repeated again with 10 more participants (3 females and 7
males), this time in an experimental home setup, successfully inferring 91.1%
of the usernames, 95.6% of the email addresses, and 66.7% of the websites
typed by participants, but only 18.9% of the passwords and 21.1% of the
English words typed by them.

Curioso.
