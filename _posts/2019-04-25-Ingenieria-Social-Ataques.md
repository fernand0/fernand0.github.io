--- 
layout: post
title: "Interacciones inseguras entre sistemas de ayuda y otros"
date: "Thu Apr 24 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, interacción, sistemas, ayuda, issues, slack, gitlab, yammer]
imagefeature: https://live.staticflickr.com/7330/27389497496_73a8179e81_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/27389497496" title="Muro roto"><img src="https://live.staticflickr.com/7330/27389497496_73a8179e81_m.jpg" width="240"  alt="Muro roto" style="float:left; margin:5px"></a>
A veces confiamos en sistemas externos para las comunicaciones de nuestra empresa, y no siempre comprendemos bien las consecuencias de algunas de sus funcionalidades.
Casi siempre nos olvidamos de que los ataques más sencilos se pueden realizar sin (casi) tecnología: basta con engañar a alguien con el acceso adecuado a la información o sacar partido de su buena voluntad de ayudar para conseguir muchas cosas.
En este caso, ni siquiera hay engaño a personas, sino a los sistemas que sirven para que las personas resuelvan sus problemas o pidan ayuda.
De eso nos hablaba Inti De Ceukelaire en [How I hacked hundreds of companies through their helpdesk](https://medium.com/intigriti/how-i-hacked-hundreds-of-companies-through-their-helpdesk-b7680ddc2d4c) y cualquier responsable de información (y explícitamente evito la palabra sistemas o informática) debería leer.

En este caso, el atacante sacaba partido de las características de sistemas comoTwitter, Slack y otros...
Esencialmente, sistemas que aceptan o mandan un mensaje sin hacer demasiadas verificaciones. El problema sucede cuando alguien puede acceder al mensaje de alguna forma alternativa (por ejemplo, porque se publica su contenido en alguna parte).

> Months ago I discovered a flaw hackers can use to access a company’s internal communications. The flaw only takes a couple of clicks to potentially access intranets, social media accounts such as Twitter, and most commonly Yammer and Slack teams.

GitLab, por ejemplo, tiene una dirección @gitlab.com de correo electrónico para crear peticiones (*issues*):

> At the same time, GitLab offers a feature to create issues by e-mail by sending them… to a unique @gitlab.com e-mail address. See *where this is headed?*

Esta se publicará directamente en el sitio adecuado y esto lo utilizó para unirse al Slack de los desarolladores: pone como dirección de la cuenta la de gitlab del proyecto y Slack manda el mensaje típico de verificación como respuesta (de forma que se publican como una petición). 'Tachán! ... Acceso conseguido.

¿Es algo exclusivo de GitLab? No, lo cierto es que muchos portales permiten enviar por correo consultas similares. 

Pero se pueden hacer otras cosas, por ejemplo abusar de los sistemas de identificación con *single sign-on*. En este caso un usuario autenticado tiene acceso directo al portal de apoyo y, en muchos casos, no se utiliza corero de verificación por lo que podríamos utilizar practicamente cualquier dirección y, en particular, una relacionada -nuevamente- con slack. 
Cuando Slack nos responde (después de buscar el espacio de trabajo que nos interesa) llega la notificación al sistema de ayuda al que nosotros ya teníamos acceso.

> Behind the scenes, feedback@slack.com now sends an e-mail to support@[censored*].com containing the verification link.

> When support@[censored*].com receives the e-mail, it will be classified as a support ticket created by feedback@slack.com… which is the exact e-mail I signed up with.

Aunque los ejemplos se realizaron con el acceso a Slack, no es la única posibilidad (nombra Yammer).

Muy curioso. Al final se trata de un ejemplo más de interacciones inseguras entre sistemas que son seguros (o que no son inseguros).

En [This hacker gained access to hundreds of companies through their helpdesk](https://thenextweb.com/security/2017/09/21/ticket-trick-see-hackers-gain-unauthorized-access-slack-teams-exploiting-issue-trackers/) está la presentación (menos ténica) del caso.
