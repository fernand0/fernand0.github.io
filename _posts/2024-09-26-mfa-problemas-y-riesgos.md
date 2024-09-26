---
layout: post
title: "Factor múltiple de autentificación y algunos problemas"
date: "2024-09-26 15:00:00 +0000"
category: seguridad
tags:
- MFA
- contraseñas
- claves
- passwords
imagefeature: "https://live.staticflickr.com/2370/2354106537_3b6f322352_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/2354106537/in/photolist-27Dwe-27DCn-27DSt-27E2R-4A2pRK" title="Aínsa. Doble muralla"><img src="https://live.staticflickr.com/2370/2354106537_3b6f322352_z.jpg" width="640" height="480" alt="Aínsa. Doble muralla"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

El consejo que damos normalmente en estos días cuando hablamos de la seguridad de las contraseñas es doble: utiliza un gestor de contraseñas y activa el doble factor de autentificación. Si sólo vas a aplicar una, mejor la segunda (aunque tiene sus propios inconvenientes, cuando los mensajes no llegan y alguna situación curiosa se puede dar...).
Como sabemos la autentificación con factor múltiple se basa en que el sistema en el que nos queremos identificar nos puede enviar algún tipo de reto (típicamente una segunda contraseña, un mensaje en alguna aplicación específica, o un mensaje en la misma aplicación pero en otro dispositivo...). Tiene la ventaja de que si adivinan nuestra contraseña podemos esperar que no tengan acceso al dispositivo donde recibiremos ese mensaje y, por lo tanto, la clave no les servirá de mucho.

En [How MFA is falling short](https://blog.1password.com/how-mfa-is-falling-short/) hablan de este sistema y de algunos de los problemas que pueden aparecer.

* Ingeniería Social.

Bastante frecuente, alguien intenta entrar en nuestra cuenta, se le solicita el factor y trata de engañarnos para que se lo demos.

> MFA risk #1: social engineering

> What’s the easiest way to steal a user’s authentication factors? Just ask them nicely.

* Robo de la sesión.

Este es un poco más técnico, pero es tan viejo, casi, como la web: robar las *cookies* que las plataformas envían para mantener nuestra información. Se hace, por ejemplo, a través de extensiones maliciosas del navegador.

> MFA risk #2: session hijacking

> Cookies have long been the way the internet has saved our browsing information and preferences; however, they also risk allowing threat actors to steal your credentials after login.

* Interposición.

Se trata de interponer entre el sistema real y el usuario algún otro que puede obtener la información que vamos transmitiendo.

> MFA risk #3: man-in-the-middle (MITM) attacks

> In MITM attacks, hackers create a fake network/server/webpage that intercepts user credentials when a user thinks they’re entering them into the legitimate destination.

* Robo de la SIM

En este caso engañamos al proveedor de comunicaciones de la persona atacada: conseguimos un duplicado de la SIM, después de conseguir tanta información como sea posible, para que sea más sencillo el engaño.

> MFA risk #4: SIM swapping

> They then contact the target’s phone carrier and impersonate them to receive a new SIM card. This allows the attacker to insert the SIM card into the mobile device of their choosing and effectively take over the target’s number.

* Hartazgo de notificaciones.

Si hacemos que al usuario le llegen tantas que está ya cansado y nervioso por el bombardeo es posible que baje la guardia y tengamos éxito.

> MFA risk #5: MFA fatigue/bombing/flooding

> The goal of an MFA bombing attack is to coerce the victim into confirming their identity via notification, which is almost always the second factor.

Después pasa a analizar algunas alternativas, y por donde podemos esperar que evolucionen las soluciones y recomienda, a día de hoy:

* Formación de los usuarios
* Utilización de un gestor de contraseñas
* Prestar atención a los dispositivos (para que no estén comprometidos).


