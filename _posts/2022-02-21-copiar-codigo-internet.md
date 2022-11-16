---
layout: post
title: "Lo encontré en un foro y resuelve mi problema"
date: "2022-02-21 15:00:00 +0000"
category: seguridad
tags:
- código
- programas
- ejemplos
- errores
imagefeature: 'https://live.staticflickr.com/17/20051836_39df5b842a.jpg'
---
<a href="https://flickr.com/photos/fernand0/20051836/" title="No funciona! "><img src="https://live.staticflickr.com/17/20051836_39df5b842a.jpg" alt="No funciona! " width="240" style="float:left; margin:5px"></a>
Hay una broma recurrente por ahí que habla de que los programadores ya no tienen que saber casi nada. Todas las soluciones están, nos dicen, en StackOverFlow y otros foros similares.

Sin embargo, y no es la primera vez que hablamos de ello, lo cierto es que muchsas veces es mala idea copiar código incluso de los libros, sobre todo si nos preocupa la seguridad.

En [If you copied any of these popular StackOverflow encryption code snippets, then you coded it wrong](https://littlemaninmyhead.wordpress.com/2021/09/15/if-you-copied-any-of-these-popular-stackoverflow-encryption-code-snippets-then-you-did-it-wrong/) hablan del tema.

El autor revisa código y encuentra fragmentos de código que están mal y que ha encontrado en ese foro:

> Security code reviews is a task that I do on a daily basis, and have been doing for the last thirteen and a half years. In this time, I have reviewed several hundred code bases, and have come across cryptographic code many times. **More often than not, there have been security issues in cryptography code that I have reviewed. Very often I have traced these bogus code snippets to StackOverflow answers that got highly upvoted**. 

La entrada se dedica a mostrar varios ejemplos, con contraseñas en el código al utilizar criptografía, por ejemplo.  También semillas y otros fallos de más alto nivel. A veces, incluso como soluciones con mayor número de votos positivos.
Que contienen errores.

> The current highest voted issue has 187 upvotes at the time of writing. This answer gives a nice overall education about how to do encryption properly, and it is definitely worth a read. The only niggle I have is the SecureRandom( ) confusion ...

Muy interesante. Y un recordatorio de que no hay que fiarse de soluciones más o menos cómodas que encontremos por ahí.
