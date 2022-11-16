---
layout: post
title: "Mejorando la gestión de la memoria en C++ para mejorar la seguridad"
date: "2022-08-29 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- programación
- c++
- google
- chrome
imagefeature: 'https://live.staticflickr.com/65535/52085214640_e28759659a.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52085214640/" title="Punteros "><img src="https://live.staticflickr.com/65535/52085214640_e28759659a.jpg" alt="Punteros " class="img-responsive img-centered"></a>
C y su pariente cercano, C++, sufren problemas de seguridad derivados de la gestión manual de memoria. No sólo ellos, claro, sino muchos otros por el simple hecho de que sus compiladores/intérpretes/herramientas están programados en estos lenguajes.

En [Retrofitting Temporal Memory Safety on C++](Retrofitting Temporal Memory Safety on C++) nos cuentan los esfuerzos de Google para aliviar estos problemas.

Nos hablan de la 'cuarentena' de la memoria, que consiste en marcar la memoria liberada en algún momento y no permitir su utilización (no está disponible) hasta que se cumplen algunas condiciones que garantizan la seguridad.

> Over the last decade, another approach has seen some success: memory quarantine. The basic idea is to put explicitly freed memory into quarantine and only make it available when a certain safety condition is reached. nos cuentan los esfuerzos de Google para aliviar estos problemas.

Nos hablan de la 'cuarentena' de la memoria, que consiste en marcar la memoria liberada en algún momento y no permitir su utilización (no está disponible) hasta que se cumplen algunas condiciones que garantizan la seguridad.

> Over the last decade, another approach has seen some success: memory quarantine. The basic idea is to put explicitly freed memory into quarantine and only make it available when a certain safety condition is reached. nos cuentan los esfuerzos de Google para aliviar estos problemas.

Nos hablan de la 'cuarentena' de la memoria, que consiste en marcar la memoria liberada en algún momento y no permitir su utilización (no está disponible) hasta que se cumplen algunas condiciones que garantizan la seguridad.

> Over the last decade, another approach has seen some success: memory quarantine. The basic idea is to put explicitly freed memory into quarantine and only make it available when a certain safety condition is reached. nos cuentan los esfuerzos de Google para aliviar estos problemas.

Nos hablan de la 'cuarentena' de la memoria, que consiste en marcar la memoria liberada en algún momento y no permitir su utilización (no está disponible) hasta que se cumplen algunas condiciones que garantizan la seguridad. Se utiliza en su navegador, Chrome, pero también hay alguna aproximación similar en el kernel de Linux.

> Over the last decade, another approach has seen some success: memory quarantine. The basic idea is to put explicitly freed memory into quarantine and only make it available when a certain safety condition is reached.

La condición de seguridad se basa en verificar que no hay punteros que hagan referencia a esta memoria, mediante la intercepción de las llamadas de petición de memoria.

> The main idea behind assuring temporal safety with quarantining and heap scanning is to avoid reusing memory until it has been proven that there are no more (dangling) pointers referring to it. To avoid changing C++ user code or its semantics, the memory allocator providing new and delete is intercepted.

En el artículo se habla de las formas de hacerlo, los compromisos alcanzados, e incluso de algunos apoyos de la arquitectura *hardware* (ARM v8.5A).

Interesante.
