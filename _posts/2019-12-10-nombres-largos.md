--- 
layout: post
title: "En informática los nombres largos son una mala idea"
date: "Thu Dec 12 15:05:01 +0100 2019"
category: desarrollo
tags: [nombres, desarrollo, variables, identificadores, consejosG]
imagefeature: https://live.staticflickr.com/207/523829842_de2311f514_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/523829842" title="Sobre nombres"><img src="https://live.staticflickr.com/207/523829842_de2311f514_m.jpg" width="240"  alt="Sobre nombres" style="float:left; margin:5px"></a>
Un asunto importante en la informática es el nombre de las cosas. En [Long Names Are Long](http://journal.stuffwithstuff.com/2016/06/16/long-names-are-long/) me gustó leer los consejos que dan y por eso lo traigo aquí.

Habla del sistema de revisión de código en Google y también de la importancia que le dan a la legibilidad, para centrarse en la longitud de los nombres (identificadores):

> What I want to talk about is something I see in a lot of code that drives me up the wall: identifiers that are too damn long.

Las metas para elegir un buen nombre deberían se la claridad (saber a qué se refiere el nombre) y la precisión (saber a qué no se refiere). Y los consejos:

Omitir nombres obvios para una variable o tipo de parámetro (por ejemplo, incluir el tipo de la variable en el nombre sería desaconsejable).

> 1. Omit words that are obvious given a variable’s or parameter’s type

Evitar palabras que no ayudan a eliminar ambigüedades (por ejempo, calificativos redundantes).

> 2. Omit words that don’t disambiguate the name

Evitar palabras que se conocen del contexto (por ejemplo, en un método que calcula un valor anualizado, ¿tiene sentido hacer referencia a la anualización en la variable correspondiente?).

> 3. Omit words that are known from the surrounding context

Evitar palabras que no significan mucho (o nada). Ejemplos: datos, estado, valor, ...

> 4. Omit words that don’t mean much of anything

Interesante.

Como bola extra, un viejo artículo sobre el nombrado y como (según Joel Spolski) se pervirtió la idea de la notación húngara (que se nombra en el otro artículo) hasta convertirla en algo absurdo [Making Wrong Code Look Wrong](https://www.joelonsoftware.com/2005/05/11/making-wrong-code-look-wrong/).

