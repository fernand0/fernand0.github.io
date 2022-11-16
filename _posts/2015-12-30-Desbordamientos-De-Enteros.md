---
layout: post
title: "Desbordamientos de enteros recientes"
date: "Wed Dec 30 19:45:01 +0100 2015"
category: seguridad
tags: [seguridad, fallos, strncat, putty, desbordamiento, enteros, overflow]
---




<a href="https://www.flickr.com/photos/fernand0/7234835502" title="Agua desbordando"><img src="https://c2.staticflickr.com/8/7231/7234835502_8d10ba38fd_m.jpg" width="240"  alt="Agua desbordando" style="float:left; margin:5px"></a>
Me repito. Pero cuando salen fallos de seguridad relacionados con los temas típcos no podemos dejarlos pasar sin comentarlos. 
En este caso se trata de desbordamientos de enteros (lectura clásica recomendada: [Basic Integer Overflog](http://phrack.org/issues/60/10.html)).

El primero se trata de un desbordamiento de enteros en `strncat' [Integer overflow in strncat](https://sourceware.org/bugzilla/show_bug.cgi?id=19390).

> I didn't look into the details but it looks like strncat(s1, s2, n) misbehave when n is near SIZE_MAX, strlen(s2) >= 34 and s2 has specific offset.

Hay algunos comentarios interesantes en [Integer overflow in glibc strncat](https://news.ycombinator.com/item?id=10778812) donde no queda claro del todo si es fallo o característica, pero vale la pena leerlos, sobre todo si nos gusta o no sinteresa el lenguaje C.

Por otro lado, leíamos el otro día en [Desbordamiento de entero en PuTTY](http://unaaldia.hispasec.com/2015/12/desbordamiento-de-entero-en-putty.html) y en [PuTTY vulnerability vuln-ech-overflow](http://www.chiark.greenend.org.uk/~sgtatham/putty/wishlist/vuln-ech-overflow.html) sobre un desbordamiento de enteros en PuTTY. En este caso el atacante debería ser capaz de insertar una secuencia de escape sofisticada que afectaría a una variable que almacena el número de caracteres que hay que borrar en determinadas condiciones.

> The vulnerability arises because PuTTY uses signed integer variables to hold the number of characters to be erased and doesn't adequately check for overflow. This means that by passing a very large parameter to ECH, an attacker could cause check_boundary to inspect memory outside the terminal buffer. 
