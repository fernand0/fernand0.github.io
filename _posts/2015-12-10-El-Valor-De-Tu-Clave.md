---
layout: post
title: "El valor de tu clave"
date: "Thu Dec 10 09:55:01 +0100 2015"
category: seguridad
tags: [seguridad, clave, contraseña, robo, credenciales, autentificación, protocolos, research, papers, procesos]
---




<a href="https://drive.google.com/file/d/0B8bmkIYKwyb8T28zcWpPTktENGM/view" title="Phishing contra Google docs"><img src="https://lh3.googleusercontent.com/44yTOyUHtFkLSLH8d0JKS_URZoR_l86UTZ9-Frvj-zmmmUAGT_tp-e0wGGE6bisKmEu0AA" width="240"  alt="Robo de credenciales" style="float:left; margin:5px"></a>
Un error frecuente de muchos usuarios es pensar que no son objetivo de ningún atante (¿a quién podría interesar mi cuenta?). Lo cierto es que es posible que no seamos nada interesantes pero aún así nuestras cuentas puedan ser utilizadas como vía de acceso a otros recursos o personas y por eso hay que mentalizarse y concienciar a los usuarios.

El dato viene de [21% of users think their passwords are of no value to criminals](http://www.kaspersky.com/about/news/product/2015/21-per-cent-of-users-think-their-passwords-are-of-no-value-to-criminals) y nos recuerda que las contraseñas son el paso necesario para obtener nuestros datos, información privada e incluso nuestro dinero. Muchas veces toda esta información está disponible gracias a las alertas y avisos que llegan a nuestra cuenta de correo.
Incluso aunque no seamos famosos, un atacante puede estar interesado en alguna de nuestras propiedades (virtuales o físicas). También puede utilizarnos como puente para acceder a otros.

En este sentido puede ser una buena lectura el artículo que puede descargarse en [Handcrafted Fraud and Extortion: Manual Account Hijacking in the Wild](http://research.google.com/pubs/pub43469.html) donde nos cuentan el proceso de un atacante cuando consigue las credenciales de una cuenta: formas de ataque, explotación, ...

El trabajo se hizo con datos de Google:

> We observe an average of 9 incidents per million Google users per day.

y habla de cómo se roban credenciales, cómo se monetiza ese robo y también (aunque para este caso es menos interesante) lo que hacen en la empresa para devolver el control al usuario.

Las técnicas de robo son las que podemos imaginar:

> This can occur in a multitude of ways: phishing a user’s credentials; installing malware on the victim’s machine to steal credentials; or guessing a victim’s password. Overall we find corroborating evidence throughout our measurements that phishing is likely to be the main way hijackers compromise user accounts. 

Una vez obtenidas estas credenciales se pasa al prefilado del usuario: ver qué hay interesante en la cuenta.

> The account profiling part where the hijacker decides on a concrete exploitation plan and the exploitation itself.  
> The existence of this profiling phase is one of the most surprising insights we gained by fighting manual hijackers. Instead of blindly exploiting every account, hijackers take on average 3 minutes to assess the value of the account before deciding to proceed. 

El resultado puede ser que nuestra cuenta termine siendo considerada poco valiosa (y abandonada), que encuentren algún objetivo de interés, o que intenten exteorsionarnos (pidiéndonos un rescate).

El phishing normalmente llegaría a través de mensajes de correo electrónico.

Finalmente habla de una cierta profesionalización de estos ataques: los atacantes parecen tener sus horarios, protocolos de actuación e incluso utilizan herramientas comunes. 
