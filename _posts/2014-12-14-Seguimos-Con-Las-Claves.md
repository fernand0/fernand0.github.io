---
layout: post
title: "Las claves muy largas también pueden ser problemáticas"
date: "Wed Dec 14 19:55:01 +0100 2014"
category: seguridad
tags: seguridad contraseñas claves passwords usuarios administradores enlaces historia usabilidad 
---


Una pregunta frecuente cuando alguien empieza a preguntarse por los temas de seguridad es por qué no poner la contraseña, o lo que sea, más grande para estar un poco más seguros. Normalmente eso puede ser un problema porque mayor tamaño implica más necesidades de cálculo, de almacenamiento...

En [Too long passwords can DoS some servers](http://www.net-security.org/secworld.php?id=15591) se refieren a un fallo en Django, donde no hay una restricción para el tamaño máximo de las claves y que podría poner a algunos servidores en problemas.

Hay más detalles en [Security releases issued](https://www.djangoproject.com/weblog/2013/sep/15/security/).

>The default password hasher in Django is PBKDF2, which has the virtue of allowing the complexity of computing the hash to be effectively arbitrarily high, by repeated "rounds" of application before producing the final result. This increases the difficulty of attacks which use brute-force methods to compute the hashes of many possible plaintext values, in hopes of discovering which plaintext password corresponds to a given hashed value.
>
>Unfortunately, this complexity can also be used as an attack vector. Django does not impose any maximum on the length of the plaintext password, meaning that an attacker can simply submit arbitrarily large -- and guaranteed-to-fail -- passwords, forcing a server running Django to perform the resulting expensive hash computation in an attempt to check the password. A password one megabyte in size, for example, will require roughly one minute of computation to check when using the PBKDF2 hasher.

Interesante.

Por cierto que sobre el tema del 'hashing' de contraseñas había un resumen interesante en [About Secure Password Hashing](http://security.blogoverflow.com/2013/09/about-secure-password-hashing/). 
