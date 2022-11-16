--- 
layout: post
title: "OAuth 2.0 y OpenId. Autorización e identidad entre servicios."
date: "Fri Apr 17 15:02:01 +0100 2020"
category: seguridad
tags: [seguridad, autentificación, identidad, autorización, serfvicios]
imagefeature: http://live.staticflickr.com/1373/4724022474_0ca7b06bd2.jpg
---


<a href="https://www.flickr.com/photos/fernand0/4724022474/in/photolist-TLtZdm-8crRim" title="Recibido. Acceso electrónico de los ciudadanos a los servi… "><img src="http://live.staticflickr.com/1373/4724022474_0ca7b06bd2.jpg" alt="Recibido. Acceso electrónico de los ciudadanos a los servicios públicos " width="240" style="float:left; margin:5px"></a>
A pesar de que sigue usándose ampliamente el usuario ya la contraseña (y su 'glorificación', el certificado digital), lo cierto es que hay formas más intersantes de dar acceso a recursos.
En [An Illustrated Guide to OAuth and OpenID Connect](https://developer.okta.com/blog/2019/10/21/illustrated-guide-to-oauth-and-oidc) hablan de estos mecanismos que permiten dar acceso a recursos sin tener que difundir o utilizar todo el rato el usuario y la contraseña.
El usuario atento habrá visto cómo necesita, a veces, autorizar el uso de un recurso (en Google, Twitter, Facebook y otras redes sociales) que es justamente eso: OAuth nos permite identificarnos ante un servicio para dar permiso a otro (o a una aplicación que se conecta al mismo) con el objetivo de poder realizar determinadas acciones). Por eso nos avisan de cosas como que la aplicación podrá leer, modificar o lo que sea que va a hacer.
Además de liberarnos de tener que poner nuestra clave y contraseña en esos sitios y aplicaciones (las ponemos directamente en el servicio en cuestión), nos permite una gestión más eficaz:

* Si cambiamos la contraseña no será necesario (al menos no siempre) reintroducirla en todas las aplicaiones.
* Si queremos revisar/modificar o cancelar quién puede acceder a nuestra información lo podremos hacer en el sitio del servicio y no en el del que hace uso de ello.

En esa entrada se hace una muestra gráfica de cómo funciona el mecanismo y me pareció interesante para compartirla aquí.

OAuth está diseñado para la autorización, esto es, dar acceso a datos y características. En algunos casos puede ser necesario, además, proporcionar información sobre el usuario (identidad). En esto entra en juego OpenID, donde se puede compartir esta información. Y también hay una demostración gráfica de las capacidades y el funcionamiento.

Interesante.
