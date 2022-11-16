---
layout: post
title: "OAuth como herramienta para ataques de envío de spam"
date: "2022-10-28 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- ataques
- OAuth
- aplicaciones
- microsoft
imagefeature: 'https://live.staticflickr.com/2120/2442636467_4f8c7a19d8.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/2442636467" title="Rimas populares "><img src="https://live.staticflickr.com/2120/2442636467_4f8c7a19d8.jpg" alt="Rimas populares " class="img-responsive img-centered"></a>
OAuth es un estándar para delegar el acceso a aplicaciones que es muy útil cuando no queremos compartir una contraseña con un sitio (al menos no todas las veces) pero necesitamos identificarnos y poder realizar acciones. Se utiliza con bastante frecuencia en APIs, pero también en aplicaciones móviles (a través de APIs también, la verdad) para gestionar mejor la autenficación (y la autorización) en diversos servicios.
En este caso, este tipo de autorización se ha utilizado simplemente como herramienta de ataque.

En [Malicious OAuth applications abuse cloud email services to spread spam](https://www.microsoft.com/en-us/security/blog/2022/09/22/malicious-oauth-applications-used-to-compromise-email-servers-and-spread-spam/) nos hablaban de un caso donde aplicaciones maliciosas usaban el estándar para acceder a recursos en la nube y enviar spam.

> Microsoft researchers recently investigated an attack where malicious OAuth applications were deployed on compromised cloud tenants and then used to control Exchange Online settings and spread spam. 

Este tipo de problemas son relativamente sencillos de evitar con sistemas de autentificación multifactor pero en este caso se atacaba precisamente a los que no lo tenían activdado.

> The investigation revealed that the threat actor launched credential stuffing attacks against high-risk accounts that didn’t have multi-factor authentication (MFA) enabled and leveraged the unsecured administrator accounts to gain initial access. 

El atacante primero compromete las cuentas de usuarios con suficientes privilegios, lo que le permite crear aplicaciones en el entorno.

> For the attack to succeed, the threat actor needed to compromise cloud tenant users with sufficient permissions that would allow the actor to create an application in the cloud environment and give it admin consent

Luego modifica la configuración del servidor de correo y lo utiliza para enviar los mensajes.

Como medios de mitigación se indican:

Reducir el riesgo de ataques de intento de adivinar las credenciales, activando la autentificación multi factor.

> The most common initial access vector observed in this attack was account compromise through credential stuffing, and all the compromised administrator accounts did not have MFA enabled. Implementing security practices that strengthen account credentials such as enabling MFA raises the cost of an attack.   

Activar las políticas de acceso condicional, basadas en dispositivos, dirección IP, ....

> Conditional access policies are evaluated and enforced every time the user attempts to sign in. Organizations can protect themselves from attacks that leverage stolen credentials by enabling policies such as device compliance or trusted IP address requirements.

Activar la evaluación contínua de acceso, que permite revocar automáticamente el acceso cuando se observan determinadas acciones de riesgo.

> Continuous access evaluation (CAE) revokes access in real time when changes in user conditions trigger risks, such as when a user is terminated or moves to an untrusted location.

Activar las opciones de seguridad por defecto, que son gratuitas y suficientes para mitigar los riesgos.

>  sufficient to better protect the organizational identity platform, as they provide preconfigured security settings such as MFA, protection for privileged activities, and others.

Y también habla de las técnicas de detección que hay disponibles.


