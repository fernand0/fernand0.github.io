--- 
layout: post
title: "Cuidado con los consejos sobre contraseñas"
date: "Tue Mar 09 15:05:01 +0100 2020"
category: seguridad
tags: [seguridad, contraseñas, claves, consejos]
imagefeature: http://live.staticflickr.com/1255/1301539362_daa1107f13.jpg
---

<a href="https://www.flickr.com/photos/fernand0/1301539362/" title="Los dados del r5 "><img src="http://live.staticflickr.com/1255/1301539362_daa1107f13.jpg" alt="Los dados del r5 " width="240" style="float:left; margin:5px"></a>
Últimamente se ha empezado a dar relevancia a las contraseñas y a los consejos sobre cómo construirlas. Se utilizan con cierta frecuencia consejos que ya no deberían darse y en [Your xkcd passwords are pwned](https://www.unix-ninja.com/p/your_xkcd_passwords_are_pwned) habla de uno de ellos en particular, que no es muy recomendable.

En primer lugar, recordar que las contraseñas es algo que todo el mundo cree que comprende, pero es algo mucho más difícil de lo que pensamos, fundamentalmente porque no tienen en cuenta a los atacantes de verdad:

> Passwords are incredibly hard to "get right." In fact, there's a pretty solid argument to be made that they can never be right (at least when used as a sole authN factor.) Yet we are inundated with "experts" telling us fantastic stories about how secure the right password policy can be. The biggest problem here is these policies aren't modeling real world attackers

Los consejos habituales son: más de 8 caracteres (más mejor), tener una mayúscula, una minúscula y un número.

Pero la fortaleza de una contraseña, ¿de dónde viene?
En realidad una contraseña es mejor si es más complicado obtenerla para un atacante, que no es algo fácil de medir:

> Ideally, the strength of a password should be the approximate measure of how difficult it would be for an attacker to recover said password. Except it gets a little more complicated than that. How do we determine something is even difficult?

Las últimas recomendaciones, además, contradicen cosas que se han dicho siempre: ya no se debe forzar la complejidad, no se deben caducar y algunas reglas más de las que ya hemos hablado a veces:

> We now have some recommendations like: * no complexity requirements * no password expiration period * no password hints * no truncation of secrets * tagging SMS OTPs as "RESTRICTED" * and some other good things...

El consejo del conocido cómic tiene una cosa buena: aleatoriedad real (con dados).

Tiene cosas malas, relacionadas con la dificultad de elegir buenas combinaciones de palabras, pero también la medición de entropía (que es compleja); otro error es asumir que los 'malos' utilizan sólo la fuerza bruta y, finalmente, cuatro palabras seguramente son pocas en este momento.

También cosas feas: al final la gente elige las palabras según su criterio, y eso reduce mucho las posibilidades, llegando a adivinar las contraseñas en unos días:

> If you haven't already guessed, I got a password in less than that. After 6 days, I cracked the password for a senior systems administrator who held highly sensitive privileges to the entire infrastructure. (This was definitely an epic moment for me.)

Termina dando los siguientes consejos: si queremos utilizar el método, deberíamos utilizar 6 palabras como mínimo, con una buena cantidad de palabras para elegir, de forma aleatoria y añadiendo espacios entre ellas.

> Also, if you're going to use diceware, make sure you do it right:
> Use a minimum of 6 base words.
> Use a decently sized pool of candidates for selection (Diceware's recommendation of 6^5 seems like a good bar.)
> Make sure your selections are chosen at random. (Do not pick them yourself.)
> Go ahead an use spaces in your passwords. Use all the spaces! It really does make a difference

Igual lo he resumido excesivamente, vale la pena leerlo.
