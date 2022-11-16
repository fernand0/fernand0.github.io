---
layout: post
title: "Contraseñas y dispositivos móviles"
date: "Wed Jun 3 19:50:01 +0100 2015"
category: seguridad
tags: seguridad hispasec boletín listas correo
---




<a href="https://www.flickr.com/photos/fernand0/3549004527/" title="Teléfono"><img src="https://farm4.staticflickr.com/3128/3549004527_0962121bc6_m.jpg" width="200"  alt="Escribiendo" style="float:left; margin:5px"></a>

En [Why passwords should not be stored on a mobile device](http://mobilesecurityares.blogspot.com.es/2014/12/why-passwords-should-not-be-stored-on.html) unas cuantas razones para evitar esa práctica de almacenar contraseñas que se utilizan para conectarse a diversos servicios en nuestro dispositivo móvil.

>This often raises the question how to store the username and the password on the device securely. The easy answer to this is: unfortunately not possible.

La solución pasaría por utilizar protocolos de autentificación modernos en los que el dispositivo no almacena una contraseña, sino un token que le identifica y que la concede permisos para  determinadas actividades:

>The question for an app developer now is: How can you make sure that the customers can use the app with all features without storing the password on the device? The solution: a token-based approach like OAuth 2.0 [4]. 

La clave está en la limitación para realizar sólo determinadas actividades (para otras se le pediría la contraseña en el momento) de forma que no está almacenada, no tiene que teclearla en cada ocasión que necesita hacer algo y el acceso a las partes más valiosas (pero menos frecuentemente utilizadas) sigue protegido con la contraseña.

Podemos recordar aquí que ya hemos hablado algunas veces de OAuth. En [OAUTH y seguridad](http://fernand0.github.io/Seguridad-OAuth/) y allí enlazábamos a algunos programitas que lo utilizan.
