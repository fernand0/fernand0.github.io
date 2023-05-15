---
layout: post
title: "Ataque contra el reciclado de credenciales en PayPal"
date: "2023-05-15 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- credenciales
- ataque
- PayPal
- usuarios
- contraseñas
- passwords
imagefeature: 'https://live.staticflickr.com/65535/52867697874_1e2ed49044.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52867697874/" title="Tornillos "><img src="https://live.staticflickr.com/65535/52867697874_1e2ed49044.jpg" alt="Tornillos " class="img-responsive img-centered"></a>

Si hay un invariante en ciberseguridad es que da igual que seas grande o pequeño puedes tener incidentes de seguridad.  En [PayPal accounts breached in large-scale credential stuffing attack](https://www.bleepingcomputer.com/news/security/paypal-accounts-breached-in-large-scale-credential-stuffing-attack/) nos hablan de un ataque para conseguir credenciales de usuarios de PayPal. 
El método utilizado es viejo, pero eficaz, si uno tiene tiempo y ganas: ir probando usuarios y contraseñas obtenidos de diversos ataques anteriores, donde ya se han divulgado los datos.

> Credential stuffing are attacks where hackers attempt to access an account by trying out username and password pairs sourced from data leaks on various websites.

La cuestión es que cuando tienes un número de usuarios importante es bastante seguro que habrá algunos de ellos que reciclen sus credenciales (esto es, que usen las mismas en varios sitios).

El ataque se produjo en diciembre del 2022 y se vieron afectados casi 35000 usuarios.

> According to the data breach reporting from PayPal, 34,942 of its users have been impacted by the incident. During the two days, hackers had access to account holders' full names, dates of birth, postal addresses, social security numbers, and individual tax identification numbers.

Parece raro que PayPal no se diera cuenta antes del ataque, pero a veces las cosas son así.

Como medida de prevención, en este caso, está clara: utilizar doble factor de autentificación. Ya sabemos que aún así habría gente afectada, pero seguramente muchos menos.

> Moreover, PayPal advises users to activate two-factor authentication (2FA) protection from the 'Account Settings' menu, which can prevent an unauthorized party from accessing an account, even if they have a valid username and password.

Y, por supuesto, no usar la misma contraseña en varios sitios.
