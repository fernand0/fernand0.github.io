--- 
layout: post
title: "Dropbox, Python y la comprobación de tipos"
date: "Mon Nov 23 15:02:01 +0100 2020"
category: desarrollo
tags: [desarrollo, python, programción, tipos, comprobación, dropbox]
imagefeature: http://live.staticflickr.com/8298/8014989646_27d2c04db0.jpg
---

<a href="https://www.flickr.com/photos/fernand0/8014989646/" title="Otros tipos "><img src="http://live.staticflickr.com/8298/8014989646_27d2c04db0.jpg" alt="Museo Pedagógico de Aragón. tipos " width="240" style="float:left; margin:5px"></a>
En programación existen varias discusiones eternas. Una de ellas es la comprobación de tipos. Hay lenguajes más exigentes y (nos dicen) por ello mucho más seguros y robustos y otros mucho menos y (nos dicen) por ello mucho más productivos y eficaces.

En [Our journey to type checking 4 million lines of Python](https://dropbox.tech/application/our-journey-to-type-checking-4-million-lines-of-python) nos hablan de Dropbox, y su esfuerzo para mejorar la verificación de tipos en sus programas escritos en Python.

> Dropbox is a big user of Python. It’s our most widely used language both for backend services and the desktop client app (we are also heavy users of Go, TypeScript, and Rust). At our scale—millions of lines of Python—the dynamic typing in Python made code needlessly hard to understand and started to seriously impact productivity. 

Python es un lenguaje con tipado dinámico (esto es, una variable puede tener un tipo en un momento dado y más adelante tener otro). Eso es cómodo, porque nos quita preocupaciones cuando programamos pero puede ser un inconveniente cuando el código crece y empezamos a no entender lo que sucede.

> Once your project is tens of thousands of lines of code, and several engineers work on it, our experience tells us that understanding code becomes the key to maintaining developer productivity. Without type annotations, basic reasoning such as figuring out the valid arguments to a function, or the possible return value types, becomes a hard problem. 

¿Qué puede devolver esta función? ¿Cómo debería ser este argumento? ¿Qué puede significar este nombre?

Puede que haya documentación, pero que sea ambigua o poco precisa.

>  Even if there is a docstring, it’s often ambiguous or imprecise, leaving a lot of room for misunderstandings. 

Si definimos los tipos y podemos verificarlos, tenemos algunas ventajas: no poner datos en lugares donde no serán bien recibidos, por ejemplo. Pero también, por ejemplo, poder cambiar el código (refactorizar) más fácilmente:

> Refactoring is much easier, as the type checker will often tell exactly what code needs to be changed.

El trabajo se ha desarrollado sobre casi 5 millones de líneas de código y ha permitido mejorar la situación:

> It has been a long journey from the early prototypes to type checking 4 million lines in production. Along the way we’ve standardized type hinting in Python,...

La organización ha asumido este trabajo como propio y ya se da por supuesto, pero aún queda camino por recorrer:

> Even though type checking is already taken for granted at Dropbox, I believe that we are still in early days of Python type checking in the community, and things will continue to grow and get better

Intersante.
