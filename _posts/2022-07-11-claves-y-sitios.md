---
layout: post
title: "Políticas de contraseñas: lo estamos haciendo mal"
date: "2022-07-11 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- contraseñas
- claves
- passwords
- políticas
imagefeature: 'https://live.staticflickr.com/65535/52123473773_c7f42c15b9.jpg'
---
<a href="https://flickr.com/photos/fernand0/52123473773/" title="Cúpula "><img src="https://live.staticflickr.com/65535/52123473773_c7f42c15b9.jpg" alt="Cúpula " class="img-responsive img-centered"></a>
Aunque van apareciendo intentos de sustituirlas y evitarlas, lo cierto es que las contraseñas siguen siendo una forma bien conocida de identificarse y autentificarse en internet.

Da la casualidad de que hace unos días avisaba a un administrador de que su sistema de gestión de cambio de contraseñas tenía algunos problemas. Me considero un friki del tema, y me fijo en detalles que parece que muchos desarrolladores desconocen. No sólo eso, sino que trato de contarlos a todo el mundo que me deja (principalmente nuestros estudiantes, que no les queda otra).

No sólo eso, muchas veces se aplican políticas solo porque las hemos visto por ahí, o nos parece que añaden seguridad (pista: en algunos casos la reducen) en lugar de aprender lo que ya se sabe sobre el tema.
Sin embargo observamos permanentemente como, a pesar de ser un método tan utilizado, las empresas lo usan bastante mal.

De eso trata [Password policies of most top websites fail to follow best practices](https://passwordpolicies.cs.princeton.edu/) que es el trabajo de Kevin Lee, Sten Sjöberg, y  Arvind Narayanan, y que nos muestra el lamentable estado de la cosa.

Definen la seguridad definen los situientes criterios:

Permitir menos de 5 de las 40 claves más usadas y fáciles de adivinar.

> Allowed 5 or fewer of the 40 most common leaked passwords and easiest-to-guess passwords (e.g., "12345678", "rockyou") we tried.

Las claves no podrán ser más cortas de 8 caracteres o utilizar un medidor de calidad que mida correctamente la resistencia a poder ser adivinado en un ataque de un atacante.

> Required passwords be no shorter than 8 characters OR employed a password strength meter that accurately measured a password's resistance to being guessed by an adversary.

Sobre usabilidad, evitar requisitos sobre el tipo de caracteres utilizados.

> Usability: Did not impose any character-class requirements (e.g. "at least one digit and one special character").

¿Resultado? Sólo 15 sitios de los 120 examinados seguían estas prácticas.

En resumen,  más de la mitad de sitios (71/120) no comprueban la calidad de las contraseñas y 19 de los que las comprueban no bloquean menos de la mitad de las malas.

> More than half (71 / 120) of websites do not check passwords at all, allowing all 40 of the most common passwords we tested (e.g., "12345678", "rockyou").

> 19 more websites block less than half of the most common passwords we tested.

Sólo 23 utilizan medidores de calidad.
>
> Only 23 / 120 websites used password strength meters.

De los 23, 10 de ellos utilizan los medidores simplemente como indicadores hacia la selección de determinados caracteres y no miden si las contraseñas son fáciles de adivinar.

> Of those 23, 10 websites misuse meters as nudges toward specific types of characters and do not incorporate any notion of guessability.

54 de los sitios analizados incluyen requisitos sobre los tipos de caracteres.

> 54 / 120 sites still require specific character classes such as digits or special characters.

Han publicado una tabla resumen en [Datos](https://passwordpolicies.cs.princeton.edu/dataset) un resumen.

Se puede leer el artículo académico en [[PDF] Password policies of most top websites fail to follow best practices](https://passwordpolicies.cs.princeton.edu/assets/password_policies_draft-latest.pdf).

¿Leerán esta información las personas responsables de estos sistemas? 
Parece que no suelen hacerlo.

