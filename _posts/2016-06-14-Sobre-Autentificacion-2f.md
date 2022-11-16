---
layout: post
title: "Sobre la autentificación de dos factores"
date: "Tue Jun 14 15:00:01 +0100 2016"
category: seguridad
imagefeature: https://c1.staticflickr.com/3/2767/4210288217_50a0012283_m.jpg
tags: [seguridad, autentificación, 2fa, dos, factores, contraseñas, passwords, claves]
---





<a href="https://www.flickr.com/photos/fernand0/4210288217" title="Enséñame la patita. Vale, no tenía otra foto con patitas."><img src="https://c1.staticflickr.com/3/2767/4210288217_50a0012283_m.jpg" width="240"  alt="Enséñame la patita. Vale, no tenía otra foto con patitas." style="float:left; margin:5px"></a>
Llevamos una temporada en la que uno de los mantras de los de seguridad en temas de autentificación es: 'utiliza autentificación de dos factores'. Ya saben: normalmente una contraseña que nos sabemos y algo más (típicamente un mensaje que recibimos de alguna forma o algún dato generado de alguna forma). 
Aunque los beneficios están claros, me resisto a recomendarla abiertamente porque cuando funciona lo hace muy bien, pero cuando falla estamos fuera (ese SMS/correo que no llega, justo cuando más lo estamos necesitando o ese canal alternativo que en ese momento no está disponible). Sin ponernos en el caso de que alguien sea capaz de interceptar los mensajes de ese canal secundario, como nos recordaban recientemente en [SMShing para robar tu 2nd Factor Authentication en tus cuentas Google o Apple #SMShing #Google #Apple](http://www.elladodelmal.com/2016/06/smshing-para-robar-tu-2nd-factor.html). Y sin olvidar que ese canal alternativo (típicamente el teléfono móvil) se ha convertido en canal unitario.

A lo que vamos, en [Why You Don't Need 2 Factor Authentication](http://sakurity.com/blog/2015/07/18/2fa.html) nos lanzaban una serie de argumentos contra el sistema, que me gusta traer aquí:

* Mito 1: lo que sabes, lo que tienes, bla, bla, bla

El autor dice que no todo es tan sencillo y que hay más categorías y más que centrarnos en esa clasificación deberíamos preocuparnos de los factorse utilizados y sus características.

* Mito 2: la autentificación de dos factores hace mi cuenta más segura, sin consecuencias negativas

En realidad, perdemos tiempo en esa parte del proceso, la aplicación es más compleja, y no evita otros inconvenientes.

Al final, la autentificación de dos factores es un gestor de contraseñas para 'perezosos' (porque lo gestiona el proveedor del servicio). 
Me parece un punto de vista interesante, aunque conociendo la tendencia a la pereza de los usuarios igual es la única solución viable.
