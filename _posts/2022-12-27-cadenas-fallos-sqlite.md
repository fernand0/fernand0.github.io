---
layout: post
title: "Un fallo en SQLite relacionado con la representación de valores"
date: "2022-12-27 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- programas
- antiguos
- SQLite
- vulnerabilidades
- análisis
imagefeature: 'https://live.staticflickr.com/5484/11481913066_1b4229f71e.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/11481913066/" title="Teatro "><img src="https://live.staticflickr.com/5484/11481913066_1b4229f71e.jpg" alt="Teatro " class="img-responsive img-centered"></a>


Cualquier observador atento (o cualquiera que se pase por aquí de vez en cuando) sabe que no hay programas seguros. No sólo eso, programas con una larga trayectoria y con una buena comunidad de usuarios detrás se encuentran con problemas (que suelen llevar tiempo allí) de vez en cuando.

Hoy traemos [Stranger Strings: An exploitable flaw in SQLite](https://blog.trailofbits.com/2022/10/25/sqlite-vulnerability-july-2022-library-api/) que es un fallo en el API de la biblioteca SQLite. Tiene mucho interés porque este gestor de bases de datos está implantado en los sistemas más diversos que podamos imaginar. No sólo eso, también tiene un buen historial de seguridad.

> SQLite is used in nearly everything, from naval warships to smartphones to other programming languages. The open-source database engine has a long history of being very secure...

El fallo tiene que ver con la longitud de una cadena de caracteres representada en 64 bits que se transformaba en un entero con signo de 32 bits cuando se pasaba como argumento en una función (dentro de un programa escrito en PHP).

> The blog’s bug manifested when a 64-bit unsigned integer string length was implicitly converted into a 32-bit signed integer when passed as an argument to a function.

Explorando el problema los autores descubrieron que en una función que se utilizaba para proteger (*escape*) comillas (*quote characters*) en uno de los módulos podía haber problemas.

> a function used for properly escaping quote characters in the PHP PDO SQLite module.

No vamos a entrar en ese nivel de detalle, pero esta es la línea en la que se pasa un entero largo sin signo `(2*ZSTR_LEN(unquoted) + 3)` a una función `sqlite3_snprintf`, que espera recibir un entero con signo:

     sqlite3_snprintf(2*ZSTR_LEN(unquoted) + 3, quoted, "'%q'", ZSTR_VAL(unquoted));


Sí que vale la pena destacar que SQLite tiene sus propias implementaciones de funciones alternativas a las peligrosas de la familia *printf*, que permiten sanear las cadenas que contienen instrucciones SQL.

Las personas interesadas deberían leerse la entrada completa (que está muy bien explicada y escrita) pero nos encontramos lo de siempre: la entrada/salida en C (SQLite está escrito en C) es delicada. Incluso cuando tratas de hacer las cosas bien, e incluso mejorarlas, puedes tener problemas.

Por si nos consuela, en las conclusiones nos dicen que las entradas necesarias para conseguir el ataque son muy grandes (y por eso los programas típicos de *fuzzing* no habrían detectado el problema).

> For one, the inputs required to reach the bug condition are very large, which makes it difficult for traditional fuzzers to reach, and so techniques like static and manual analysis were required to find it. 

Además, es un error que en el momento de escribirlo seguramente no se habría considerado como tal, porque entonces las arquitecturas eran primordialmente de 32 bits.

> For another, it’s a bug that may not have seemed like an error at the time that it was written (dating back to 2000 in the SQLite source code) when systems were primarily 32-bit architectures

Finalmente, el ataque era más sencillo gracias a las representaciones divergentes (*divergent representations*) de la misma variable (algunas optimizaciones del compilador ocasionan que se puedan leer valores diferentes en función de si se ven de una forma o de otra).

> its exploitation was made easier by the discovered “divergent representations” of the same source variable, which we explore further in a separate blog post.

Sobre esto han escrito otra entrada, que no he leído aún: Look out! [Divergent representations are everywhere!](https://blog.trailofbits.com/2022/11/10/divergent-representations-variable-overflows-c-compiler/).

