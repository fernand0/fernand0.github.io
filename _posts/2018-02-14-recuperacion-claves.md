---
layout: post
title: "Sistemas de recuperación de contraseñas"
date: "Wed Feb 14 15:10:01 +0100 2018"
category: seguridad
tags: [contraseñas, claves, recuperación, web, aplicaciones, seguridad]
imagefeature: https://avecesunafoto.files.wordpress.com/2017/07/img_20170623_172153.jpg
---


<a href="https://avecesunafoto.wordpress.com/2017/07/22/luces-de-colores-lo-pasare-bien-no/" title="Servidores"><img src="https://avecesunafoto.files.wordpress.com/2017/07/img_20170623_172153.jpg" width="240"  alt="Servidores" style="float:left; margin:5px"></a>
El mundo de las contraseñas es muy interesante. Pero suponiendo que todo va bien (o no), pero que ya tenemos montada una infraestructura alrededor de ellas la gente tenemos la manía de olvidarlas.

En [Untangling the Forget-Me Knot: Secure Account Recovery Made Simple](https://paragonie.com/blog/2016/09/untangling-forget-me-knot-secure-account-recovery-made-simple) un recordatorio de las cuestiones básicas alrededor del tema de recuperación de las contraseñas.

Empieza con un recordatorio: cuando permites cambiar la contraseña, empiezan los problemas:

> This bears emphasis: When you give your users the capability to reset their password, you are creating a backdoor into their account.

Naturalmente, en cualquier instalación de tamaño mediano será difícil manejar el problema 'a mano' así que habrá que tener algún mecanismo de recuperación (que típicamente será un sistema para poner una nueva), porque no deberíamos enviar a los usuarios la que tenían (no deberíamos ser capaces):

> If you're taking security seriously and properly utilizing a password hashing function, you shouldn't even be able to do this. 

Tampoco es buena idea enviarles una nueva: se transmitirá por canales inseguros, puede que no llegue, puede que no lo hagas bien, hay que esperar a que llegue (experiencia desagradable de la que, de cualquier modo, puede que no nos libremos) y, si no lo cambian, probablemente permanezca en el canal de comunicación para siempre.

Tampoco aconseja utilizar preguntas de seguridad, se trata de una clave secundaria que normalmente es fácil de adivinar.

> The answers to most security questions are like a second password, except they're often disclosed publicly on social media

Entonces, ¿qué hacer?

Primero, hacerlo opcional: si el usuario es suficientemente competente, gestionará bien sus contraseñas y no necesitará cambiarlas por estos mecanismos:

> So, first and foremost, empower your users to choose convenience or security. Ask them, "Do you want to be able to regain access to your account if you ever forget your password?" If your application is designed for high risk users, consider defaulting to "No".

Lo que no significa que no pueda cambiarse, sólo que hará falta que lo haga alguien por nosotros.

Segundo, utilizar un mecanismo de recuperación basado en un token dividido (una parte sirve para identificar, la otra para validar. La que identifica se almacena en la base de datos sin más, la de validar se almacena transformada como un hash: al usuario se le envían ambas; si alguien consiguiera entrar en la aplicación el 'token' no le serviría para nada. Igual es exagerado porque si consiguen robar la base de datos de identificación seguro que tenemos más problemas; pero no es mucho trabajo y añade seguridad.

El artículo también sugiere cifrar los mensajes, que puede ser algo aplicable en contextos muy concretos (no creo que para usuarios en general).

Finalmente, los 'tokens' deberían caducar, para que no sirvan para siempre almacenados (igual que si fueran contraseñas) en el sistema de mensajería.

Interesante.
