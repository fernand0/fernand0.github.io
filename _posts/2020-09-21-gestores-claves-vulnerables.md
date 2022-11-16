--- 
layout: post
title: "Gestores de contraseñas y seguridad"
date: "Mon Sep 21 15:02:01 +0100 2020"
category: seguridad
tags: [seguridad, gestores, contraseñas, claves, passwords, vulnerabilidades]
imagefeature: http://live.staticflickr.com/65535/50193368636_b9c97e8d6d.jpg
---

<a href="https://www.flickr.com/photos/fernand0/50193368636/in/dateposted/" title="Entrada "><img src="http://live.staticflickr.com/65535/50193368636_b9c97e8d6d.jpg" alt="Entrada " width="240" style="float:left; margin:5px"></a>
Uno de mis temas favoritos en cuanto a problemas de seguridad son los programas desarrollados para protegerla que resultan ser vulnerables. En esta ocasión podemos leer [Some commercial password managers vulnerable to attack by fake apps](https://www.helpnetsecurity.com/2020/03/18/password-managers-vulnerable/) que habla de gestores de contraseñas y algunas vulnerabilidades.
Reconozcámoslo, la seguridad no es fácil: hay muchas cosas que se pueden hacer mal y es complicado hacerlo todo bien.

Algunos de estos programas utilizaban métodos débiles para identificar una aplicación y qué credenciales había que usar con ella (hacer las cosas más fáciles puede hacerlas demasiado fáciles).

> ... some of the password managers used weak criteria for identifying an app and which username and password to suggest for autofill. This weakness allowed the researchers to impersonate a legitimate app simply by creating a rogue app with an identical name.

Esto significa que si engañamos al usuario para que instale una aplicación falsa 'adecuada' podríamos conseguirlas.

> “Our study shows that a phishing attack from a malicious app is highly feasible – if a victim is tricked into installing a malicious app it will be able to present itself as a legitimate option on the autofill prompt and have a high chance of success.”

La recomendación frente a esto es utilizar doble factor de autentificación: pueden robarnos las credenciales pero será difícil que tengan, además, el dispositivo para el segundo factor.

> “The risk presented with autofill on compromised websites pertains only to the site’s credentials, not the user’s entire vault. It is always in the user’s best interest to enable MFA for all online accounts ...

Había otros problemas, por ejemplo, no había limitaciones sobre el número de veces que se podía comprobar un PIN.

>The researchers also discovered some password managers did not have a limit on the number of times a master PIN or password could be entered. This means that if hackers had access to an individual’s device they could launch a “brute force” attack, guessing a four digit PIN in around 2.5 hours.

Claro que, en este caso, el doble factor probablemente tampoco ayudaría.

Otro de mis favoritos en seguridad es lo que sucede muchas veces: problemas de seguridad detectados y anunciados anteriormente siguen allí.

> The researchers also drew up a list of vulnerabilities identified in a previous study and tested whether they had been resolved. They found that while the most serious of these issues had been fixed, many had not been addressed.

Interesante.
