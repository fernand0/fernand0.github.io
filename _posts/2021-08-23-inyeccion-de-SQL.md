---
layout: post
title: "Más de 20 años de la inyección SQL y todavía sigue allí"
date: "2021-08-23 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- inyección
- SQL
- desarrolladores
- formación
- herramientas
imagefeature: 'http://live.staticflickr.com/65535/50338211772_dbb92fc9f3.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/50338211772/" title="Brazo ortopédico "><img src="http://live.staticflickr.com/65535/50338211772_dbb92fc9f3.jpg" alt="Brazo ortopédico " width="240" style="float:left; margin:5px"></a>
Una de las facetas más curiosas de la seguridad informática es que se siguen cometiendo los mismos errores desde hace un montón de años. En [SQL injection: The bug that seemingly can’t be squashed](https://www.helpnetsecurity.com/2021/01/11/sql-injection-bug/) nos recuerdan que los fallos de inyección de SQL acaban de cumplir 22 años pero siguen siendo un problema frecuente de seguridad.

> December 2020 marked SQL injection’s 22nd birthday (of sorts). Despite this vulnerability being old enough to drink, we’re still letting it get the better of us instead of squashing it for good. In August this year, Freepik Company disclosed that they had fallen victim to an SQL injection blunder that compromised the accounts of 8.3 million users. 

La inyección de SQL se produce cuando alguien que utiliza un programa es capaz de hacer que se lancen **sus** preguntas directamente a la base de datos. De allí puede salir cualquier problema: divulgación de información, modificación o incluso eliminación. El problema tiene que ver casi siempre con desarrolladores que no han tomado las precauciones necesarias para que esto no pueda suceder (esencialmente validar que los datos proporcionados por el usuario corresponden a lo que deben y que no incluyen 'sorpresas').

Es un problema especialmente grave porque no tiene que ver con los usuarios: son los desarrolladores los que pueden evitarlo con unas prevenciones mínimas y, aún así, no se remedia.

> We keep saying that SQL injection is simple to fix and that code should be written so as to not introduce it at all. Like most things, it’s only easy when you’ve been taught how to do it right. 

Aunque siempre pensamos que los ataques son muy sofisticados, lo cierto es que no parece que esto sea siempre así.

En la nota dicen, y debe de ser verdad, que muchas personas que estudian informática nunca han llegado a recibir formación sobre estos temas:

> This shouldn’t come as a surprise: most engineers complete their degree without having learned much about secure coding (if anything at all). Most on-the-job training is inadequate, especially in an environment where security is not seen as a business priority in their role. 

Algunos lenguajes nuevos, más robustos, ayudan con algunos fallos que sigue habiendo. Pero sigue habiendo sistemas legados, código viejo y bibliotecas que no manejan bien estas cosas (y también, esto lo digo yo, desarrolladores que siguen haciendo las cosas 'a mano' sin tener en cuenta las amenazas que existen).

> Newer, more security-robust languages like Rust are helping to eradicate some of the bugs we’ve dealt with for a long time by utilizing safer functions, but there is an enormous number of legacy software, older systems, and libraries that will continue to stay in use and be potentially vulnerable. 

Como siempre decimos, los desarrolladores deben embarcarse en este viaje desde el principio y recibir el apoyo adecuado para desarrollar mejor.

> Developers must be brought on the journey from the beginning, and supported to take responsibility for their part in creating safer, better code. 
