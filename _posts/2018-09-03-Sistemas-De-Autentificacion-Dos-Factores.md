---
layout: post
title: "Algunos aspectos prácticos de la autentificación de dos factores"
date: "Mon Sep 03 16:02:01 +0100 2018"
category: seguridad
tags: [seguridad, autentificación, autenticación, 2FA, dos, factores]
imagefeature: https://c1.staticflickr.com/3/2899/33253324191_7174667d5b_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/33253324191" title=""><img src="https://c1.staticflickr.com/3/2899/33253324191_7174667d5b_m.jpg" width="240"  alt="Puerta" style="float:left; margin:5px"></a>
Llevamos una temporada escuchando que la autentificación con dos factores es la solución para los problemas de las malas contraseñas que eligen los usuarios y otros problemas de la autentificación mediante contraseña. 
La autentificación de dos factores se vió puesta en entredicho este verano por la inseguridad de los SMS [Reddit hack highlights vulnerability of two-factor authentication](https://www.computing.co.uk/ctg/news/3036969/reddit-hack-highlights-vulnerability-of-two-factor-authentication).
No obstante, podemos ver en [Inside Two-Factor Authentication Apps](https://hackaday.com/2017/10/16/inside-two-factor-authentication-apps/) proporcionan algunas pistas interesantes y una introducción al tema que podemos leer, con ejemplos de código en Python. 

> So I’m going to step quickly through how 2FA apps work, and then show you how you can implement it yourself if you want in a few lines of Python.

Para hacer una autentificación de dos factores, en la práctica, muchcas aplicaciones utilizan para generar el segundo factor el algoritmo de clave de un solo uso basado en tiempo:

> In practice, because of cost and convenience, most 2FA implementations use an app that authenticates using the time-based one-time password (TOTP) algorithm. That is, it’s just another password. 

Se basan en una contraseña secreta, un secreto compartido (el momento de la petición) y una función de hash:

> The beauty of these algorithms is that the one-time secret password is hashed with some other number that’s common knowledge to me and the server — sometimes it’s a simple counter. This generates a different “password” for every value of the counter.

Para no tener problemas con las diferencias de tiempo entre el cliente y el servidor hace falta un pequeño ajuste, que consiste en habilitar tramos de alrededor de 30 segundos y, además, dar por bueno el anterior y el posterior:

> In most TOTP implementations, the counter is the number of 30 second intervals that have elapsed since Jan 1, 1970 — the Unix epoch. This gives you a different, strong, password every 30 seconds. Practically, servers will accept either the previous, current, or next values to allow for clocks to go a little out of sync, but after a minute or so, that old hashed value is useless to an attacker. That’s pretty cool

Interesante.

