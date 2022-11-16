--- 
layout: post
title: "Almacenamiento de información sobre nuestra navegación: cookies y LocalStorage"
date: "Tue Jan 13 15:05:01 +0100 2020"
category: web
tags: [web, navegación, cookies, localstorage, desarrollo]
imagefeature: https://live.staticflickr.com/6235/6323493704_c2d4c0cc81_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/6323493704" title="Galletas"><img src="https://live.staticflickr.com/6235/6323493704_c2d4c0cc81_m.jpg" width="240"  alt="Galletas" style="float:left; margin:5px"></a>
Un artículo técnico pero no demasiado sobre cómo almacenan información los navegadores: [Cookies vs. LocalStorage: What’s the difference?](https://medium.com/swlh/cookies-vs-localstorage-whats-the-difference-d99f0eb09b44).

Todos hemos oido hablar de las 'cookies' (de manera irremediable por la absurda regulación sobre los avisos y esas cosas que tanto dolor causan en nuestra navegación diaria). No es tan habitual haber escuchado hablar de 'LocalStorage', otro sistema de almacenamiento de información (siempre local, otra cosa es lo que se haga con esa información después, claro).

Sobre las cookies, lo de siempre: un poco de información que se utiliza principalmente para hacer seguimiento de nuestra navegación mediante algún tipo de identificador que se nos asigna.

> So, what are cookies? According to whatarecookies.com, they are small text files that are placed on a user’s computer by a website. 

Que las hay persistentes y de sesión, las primeras tienen fecha de caducidad y las segundas expiran en cuanto cerramos la ventana del navegador (o la pestaña, o lo que sea). Las persistentes quedan almacenadas en nuestro sistema y son las que permiten que no tengamos que identificarnos una y otra vez en los sitios que usamos habitualmente.

Sobre LocalStorage, se trata de un mecanismo introducido con HTML5, que tiene la ventaja de que no es necesario que viaje de un sitio para otro en nuestra navegación en cada enlace que pinchamos (está orientado a almacenar información localmente).

> This is because data is stored on the user’s local disk and is not destroyed or cleared by the loss of an internet connection.

Para repasar.
