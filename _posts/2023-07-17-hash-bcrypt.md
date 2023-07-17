---
layout: post
title: "25 años de bcrypt y un poco de historia sobre la seguridad de las contraseñas"
date: "2023-07-17 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- contraseñas
- passwords
- claves
- seguridad
- historia
imagefeature: 'https://live.staticflickr.com/4771/39855842155_056cf6ec83.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/39855842155/" title="Enigma "><img src="https://live.staticflickr.com/4771/39855842155_056cf6ec83.jpg" alt="Enigma " class="img-responsive img-centered"></a>

Ahora que es raro (aunque posible, todavía) ver sitios o programas que conserven las contraseñas en lugar de las versiones modificadas (*hash*) me gustó leer [Bcrypt at 25: A Retrospective on Password Security
](https://www.usenix.org/publications/loginonline/bcrypt-25-retrospective-password-security).

Lo firma Niels Provos, uno de los autores de bcrypt (en el año 1997) y la primera sorpresa después de 25 años es que seguimos utilizando contraseñas.

> As one of the creators of bcrypt back in 1997, I find it somewhat surprising that, 25 years later, we still rely heavily on passwords.

Habla después de los sistemas compartidos, donde la seguridad de la contraseña no se consideraba crítica (eran entornos de colaboración)

> This came over the strenuous objections of Richard Stallman who famously tried to resist the introduction of passwords at MIT in the 1970s (Levy, 1984). 

Y la introducción del primer sistema de *hashing* un poco robusto en los sistemas Unix, de la mano de sus primeros autores:

> Unix, developed in the 1970s by Ken Thompson and Dennis Ritchie, introduced a more robust password hashing function called crypt. 

Pero todavía hacía falta tener en cuenta la capacidad de cálculo que iban teniendo los sistemas y la importancia de dificultar la prueba por fuerza bruta para conseguir adivinar las contraseñas.

> The concept of adaptive hashing, which made brute force and dictionary attacks more and more computationally demanding, was the brainchild of David Mazières.

El problema que se trataba de solucinar era el robo de bases de datos de contraseñas de sistemas comprometidos: una vez que se comenzaron a almacenar transformados, lo que tenían que hacer los atacantes es probar con listas de contraseñas frecuentes, o probar todas las combinaciones (fuerza bruta) y  pescar lo que se pudiera. 

> Consequently, various tools emerged to guess common passwords and compare them with the hashed passwords in the user database. These tools typically employ a combination of dictionary attacks, brute force and other techniques to guess potential passwords and check them against stored hashes (Bonneau, 2012). John the Ripper, L0phtCrack, Hashcat, and Hydra are some popular examples of password cracking tools.

Cuando un atacante consigue algunas de estas contraseñas, puede probarlas en diferentes servicios, consiguiendo con frecuencia acceder a información interesante.

> When attackers successfully recover passwords from a database dump, they can then try them on different servers and sites, often gaining access to email accounts or other sensitive user data.

La introducción de `bcrypt` supuso un avance interesante por el factor de coste ajustable (esencialmente, se puede 'tunear' con parámetros de configuración para que sea más costoso de calcular conforme aumenta la velocidad de los procesadores).

> This critical feature allowed bcrypt to keep pace with computing power advancements, maintaining its robustness against evolving threats.

Como es natural, la existencia de buenos algoritmos no significaba que se estuvieran utilizando, como muestran algunos ejemplos. LinkedIn (SHA-1), Yahoo! (MD5, SHA-1, bcrypt), Adobe (SHA-1), MySpace (SHA-1)...

> Sadly, industry adoption hasn't been as swift as I had hoped. Even after introducing bcrypt and other more secure password hashing algorithms, numerous high-profile data breaches have occurred involving passwords hashed with weaker algorithms.

Y, como decíamos arriba, el factor de la potencia de cálculo: en 34 años se ha pasado de poder calcular 45 claves por segundo a 6.3 miles de millones, pulverizando (en este tema) las predicciones de la ley de Moore.

> Over the course of 34 years, we've witnessed an extraordinary leap in the password guessing speed for DES-crypt; it's accelerated from a mere 45 passwords per second to an astounding 6.3 billion passwords per second. This advance doesn't just surpass Moore's law — it pulverizes it, tripling the password cracking speed every two years.

Termina recordándonos que las contraseñas ya no son un gran problema y ni siquiera la seguridad es ya un problema técnico:

> In my experience, most security professionals consider password security a solved problem from a technical perspective. I would even go further and claim that security is no longer a problem that I consider to be primarily technical.

Sin embargo, sí que es importante tomar las decisiones técnicas adecuadas, que no es algo que venga disponible 'en una caja' para todo el mundo.

> Let’s talk about adopting security technologies first. Currently, there are no off the shelf solutions that lead to good security outcomes. 

La mayoría de las empresas siguen buscando el compromiso (cuando lo buscan) entre la seguridad y gasto.

> Most other companies usually seek to choose an appropriate trade off between investing in business growth and security. 

Porque los incentivos siguen siendo hacer crecer el negocio y gestionar los problemas de seguridad cuando aparezcan.

> The incentives are such that it is the rational argument to invest in business growth and treat a data breach as an eventuality that will be dealt with when it happens. 

Sin embargo, para las empresas con un nivel adecuado de madurez la preocupación es más bien por los aspectos humanos, fundamentalmente el riesgo que pueden provocar nuestros propios empleados.

> For the few companies that achieve a mature security posture, human factors often dominate their security concerns, and insider risk becomes the primary focus. 

Buena lectura.

