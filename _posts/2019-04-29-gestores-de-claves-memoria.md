--- 
layout: post
title: "La seguridad y los gestores de contraseñas"
date: "Thu Apr 29 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, contraseñas, claves, fallos, secretos, memoria]
imagefeature: https://live.staticflickr.com/4338/37251899012_eeea0637df_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/37251899012" title="Escondido"><img src="https://live.staticflickr.com/4338/37251899012_eeea0637df_m.jpg" width="240"  alt="Escondido" style="float:left; margin:5px"></a>
Me gustó leer [Password managers may leave your online crown jewels 'exposed in RAM' to malware – but hey, they're still better than the alternative](https://www.theregister.co.uk/2019/02/20/password_managers_security_bugs/) porque trata dos temas sobre los que pasamos de largo habitualmente: los usuarios no utlizan los gestores de contraseñas y, en general, no se preocupan demasiado de la calidad de sus claves; por otro lado, los desarrolladores no suelen prestar atención a los secretos almacenados en memoria. Esto es, cuando desciframos un dato con un programa ese dato reside en alguna parte (o algunas) de nuestro computador. Y lo de algunas tiene que ver con las *cachés*, mecanismos de paginación y otros artefactos que aparecen en nuestra vida diaria.

Sobre este segundo tema, dice:

> The problem here is mainly secure memory management. To some degree, every one of the four password managers left passwords – either the master password or individual credentials – accessible in memory. This would potentially allow malware on a system, particular malware with admin rights, to obtain those passwords.

Y no se trata de una afirmación puramente teórica, sino que hicieron las pruebas:

> "Each password manager also attempted to scrub secrets from memory. But residual buffers remained that contained secrets, most likely due to memory leaks, lost memory references, or complex GUI frameworks which do not expose internal memory management mechanisms to sanitize secrets."

porque este trabajo proviene de una investigación sobre la seguridad de 1Password, KeePass, LastPass y Dashline, algunos de los gestores más conocidos. Se pueden ver más detalles en [Password Managers: Under the Hood of Secrets Management](https://www.securityevaluators.com/casestudies/password-manager-hacking/).

De todas formas, y volviendo a los usuarios normales, ¿debemos dejar de usar los gestores porque tienen fallos? 
La respuesta es claramente negativa porque con esos problemas y con todo lo que podamos pensar, siguen siendo una manera más eficaz de resolver el problema para la mayoría de la gente:

> The report doesn't by any means suggest you should not be using a password manager. Even with the mild flaws ISE found, a password manager remains by far the best way to keep your login credentials secure, and experts routinely recommend them as a way to manage multiple unique and strong passphrases for your online accounts.

Por lo tanto, ya saben ustedes: si son desarrolladores, que los secretos descifrados estén el menor tiempo posible así y sólo en memoria. Si son usuarios, utilicen un gestor de contraseñas. Serán mejores y ustedes estarán más seguros.
