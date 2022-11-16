---
layout: post
title: "Las contraseñas. Más complicado de lo que solemos pensar."
date: "2021-12-06 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- contraseñas
- claves
- normas
- entrevistas
imagefeature: 'http://live.staticflickr.com/65535/51059825032_8b6308bfd7.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/51059825032/" title="Detalle parte superior puerta de la Lonja "><img src="http://live.staticflickr.com/65535/51059825032_8b6308bfd7.jpg" alt="Detalle parte superior puerta de la Lonja " width="240" style="float:left; margin:5px"></a>
Me encanta el tema de las contraseñas. Es un modelo sencillo, pero muy difícil de hacerlo todo bien. En mis clases dedico un buen rato al tema y cuando me invitan a dar una charla también me gusta prestarle atención.

En [Evolving beyond password complexity as an identity strategy](https://www.microsoft.com/security/blog/2021/04/22/evolving-beyond-password-complexity-as-an-identity-strategy/) una entrevista a Troy Hunt, que mantiene el sitio [HaveIBeePwned](https://haveibeenpwned.com/), entre otras cosas.
Este sitio se dedica a recopilar información sobre diversos conjuntos de datos obtenidos en ataques informáticos que terminan siendo publicados de una forma u otra. Esto le da mucha perspectiva acerca de las contraseñas que utiliza la gente y cómo la protegen los sitios.

Empieza hablando de una tendencia que se está observando en los últimos meses, relacionada con ataques de robo de información mediante la obtención de una copia de la SIM del propietario por diversos métodos.
Cuando se utiliza como un segundo factor de autentificación (*2FA*) tendremos unproblema si alguien puede conseguir una copia de la nuestra con cierta facilidad.
Tiene que ver con lo desagradable que es quedarse sin ella y no poder comunicarte, pero hay que balancear la facilidad de resolver los problemas con lo que puede pasar si eso ayuda a los malos.

> ... SIM card hijacking. It concerns me greatly that it seems to be so prevalent and that it’s so easy, almost by design, to port a SIM from one location to another. As an industry, we need to say, “Where is the level of identity assurance for a phone number?”

Y, claro, esto tiene que ver con la industria y cómo los profesionales manejan las necesidades de sus usuarios. A veces se toman decisiones sin tener en cuenta a las personas afectadas.

> I would really like IT professionals to better understand the way humans interact with systems. Everyone says, “Just force people to use two-factor authentication.” Do you still want customers? I think every IT professional should have to go through two-factor authentication enrollment with my parents. Everyone should have to learn what it’s like to take non-technical people and try and get some of these things working for them. We can’t just look at these things in a vacuum.

Y las contraseñas tradicionales son un método de interacción bien conocido.

> The thing that passwords do better than just about everything else is that everyone knows how to use them.

Un consejo que solemos dar es utilizar un gestor de contraseñas, que nos permiten almacenarlas adecuadamente protegidas. Pero, dice Hunt, no sólo las contraseñas, podemos utilizarlos para otro tipo de información, como puede ser nuestra tareta de crédito u otros datos secretos que podamos necesitar.

> Password managers are a way of storing one-time passcodes (OTPs), but it’s important to recognize that password managers are not just for passwords. I have my credit card details in there, and every time I go to pay at a store, I do the control backslash and automatically fill in the credit card details. 

Otros casos pueden ser las cuentas compartidas (aunque yo aquí diría que los proveedores de servicios deberían hacerlo mejor y permitirnos tener cuentas individuales en servicios compartidos; pero no estamos allí, en la mayoría de los casos, aún).

> Another use case is a family account. If my partner wants to log into our Netflix account, she has her own identity, but there’s one set of credentials. [...] But if you have a password manager where you have shared vaults, you can just drop it in the shared vault. 

Se dice de vez en cuando que las contraseñas llegan a su fin (de hecho, algunosservicios ya usan sistemas alternativos como el envío de un código cuando intentamos entrar). Pero es un sistema que ya tiene más de 60 años.

> Ultimately, this password is the key to your identity. We’ve had passwords on computer systems for about 60 years and the era in which they were born was so simple.

Luego habla de las normas de complejidad: en muchos sitios nos obligan a cumplir determinadas normas consiguiendo, paradójicamente, contraseñas peores. Si nos dicen que tenemos que poner alguna letra mayúscula, ponemos la primera en mayúscula; si nos piden que tenga un número o un símbolo, lo añaddimos al final:

> "[...] and a website says you have to have at least one uppercase character. What do you do? You capitalize the first letter." [...] "You have to have a number. What do you do? You put a one at the end." And there’s the same nervous laughter. 

Las contraseñas representan algo fácil de comprender pero que tiene más dificultades a la hora de hacer las cosas bien de las que solemos tener en cuenta.
