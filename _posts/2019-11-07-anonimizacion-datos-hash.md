--- 
layout: post
title: "Anonimización de datos personales y ataques"
date: "Thu Nov 07 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, anonimato, datos, hash, descubrimiento]
imagefeature: https://live.staticflickr.com/4338/37251899012_eeea0637df_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/37251899012" title="Oculto"><img src="https://live.staticflickr.com/4338/37251899012_eeea0637df_m.jpg" width="240"  alt="Oculto" style="float:left; margin:5px"></a>
Recientemente se ha hablado en España del tema de anonimización de datos de ciudadanos (lo contaba en [Demoscopía tecnológica: Un gobierno que tome decisiones basadas en datos](http://fernand0.blogalia.com/historias/78040)) porque creo que es un buen camino para conocer mejor a los ciudadanos y proporcionarles un buen servicio.

No obstante, soy consciente de que cuando se habla de anonimización, hay que manejar los términos con cuidado. Y por eso me gustó leer [Hashing names does not protect privacy](https://www.johndcook.com/blog/2019/07/20/hashing-pii-does-not-protect-privacy/); esto es, utilizar un hash de los nombres (o de los identificadores) no tiene por qué supone una anonimización efectiva, sobre todo si el atacante sabe que la entrada proviene de un conjunto de datos restringido (¿números de teléfono? ¿matrículas?).

> But you know the input comes from a restricted set, a set small enough to search by brute force, then hash functions are reversible. If I know that you’ve either hashed “yes” or “no,” then I can apply the hash function to both and see which one it was.

Sobre datos personales, siempre estaremos trabajando con un conjunto de datos pequeños donde un ataque de fuerza bruta tiene sentido (sobre todo si se buscan los datos de alguien en particular).

> Suppose someone has attempted to anonymize a data set by hashing personally identifying information (PII) such as name, phone number, etc. These inputs come from a small enough space that a brute force search is easy.

Los números son más costosos

> Hashing numbers is simpler but more computationally intense. I had to do a little research to find a list of names, but I know that social security numbers are simply 9-digit numbers. There are only a billion possible nine-digit numbers, so it’s feasible to hash them all to make a look-up table.

Para mejorar la situación la propuesta tampoco es muy complicada: en lugar de utilizar el dato, generar una clave que podemos combinar con los valores reales antse de hacer el hash.

> One way to improve the situation would be to use a key, a random string of bits that you combine with values before hashing. An attacker not knowing your secret key value could not do something as simple as what was described above.

En temas de seguridad y privacidad siempre hay que ir un poco más allá.
