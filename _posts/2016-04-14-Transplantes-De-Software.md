---
layout: post
title: "Transplantes de código para arreglar fallos"
date: "Thu Apr 14 12:30:01 +0100 2016"
category: fallos
tags: [desarrollo, fallos, bugs, corrección, automática, codephage]
---





<a href="https://www.flickr.com/photos/fernand0/7258092704" title="Bicho"><img src="https://c1.staticflickr.com/9/8149/7258092704_d670649aff_m.jpg" width="240"  alt="Bicho" style="float:left; margin:5px"></a>
Me dan un poco de miedo las analogías 'médicas' porque siempre hay quien termina tomándoselas al pie de la letra (recuerdo hace un montón de años escuchar una conversación en el tren de alguien que le contaba a otro como los virus informáticos se inoculaban con una jeringuilla).

En este caso la idea es muy sugerente: [MIT tests 'software transplants' to fix buggy code](http://www.pcworld.com/article/2941992/mit-tests-software-transplants-to-fix-buggy-code.html), utilizar el código de programas que funcionan correctamente para 'reparar' programas con fallos:

La idea se basa en entradas de datos que hacen fallar el programa y otras que no lo hacen fallar.

> To fix a buggy program, CodePhage requires two sample inputs, one that causes the program to crash, and another that does not.

Se utilizan para verificar en un 'donante' que se obtienen los resultados correctos y a partir de allí ya se sabe que se puede utilizar ese nuevo código para corregir el programa defectuoso:

> It runs those inputs through a second program, known as the donor program, that has similar functionality. The Internet is awash with open source software that could provide parts for donor programs, though there’s no particular reason the donor code needs to be open source.

Si leemos algunos detalles más en [System fixes bugs by importing functionality from other programs—without access to source code](http://phys.org/news/2015-06-bugs-importing-functionality-programswithout-access.html) podemos ver que se trata de algo que deberíamos denominar, más bien, 'microtransplantes', porque se trataría de pequeños bloques de código.

En el artículo (seguramente no accesible para todos), [Automatic error elimination by horizontal code transfer across multiple applications](http://dx.doi.org/10.1145/2737924.2737988) se puede ver, por ejemplo un fallo en el programa gif2tiff, corregido mediante la 'donación' desde ImageMagick:


{% highlight c %}
#define MaximumLZWBits  12
if (data_size > MaximumLZWBits)
   ThrowBinaryException(CorruptImageError,
         "CorruptImage",image.filename);
{% endhighlight %}

Este código sería susceptible de un ataque de desbordamiento de memoria y el programa propondría corregirlo con:


{% highlight c %}
if (!(datasize <= 12)) {exit(-1);}
{% endhighlight %}

Me encanta.
