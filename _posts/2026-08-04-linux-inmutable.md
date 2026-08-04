---
layout: post
title: "Inmutabilidad: control, reproducibilidad... ¿pagando un precio?"
date: "2026-08-04 14:00:00 +0000"
category: seguridad
tags:
- seguridad
- inmutabilidad
- nube
- control
imagefeature: "https://live.staticflickr.com/65535/55034144037_a44a7e1cea_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/55034144037/" title="Decoración del Obeslico de Teodosio"><img src="https://live.staticflickr.com/65535/55034144037_a44a7e1cea_z.jpg" width="640" height="427" alt="Decoración del Obeslico de Teodosio"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En los últimos años venimos observando cada vez más preocupación sobre qué tenemos ejecutándose en las máquinas por ahí, sobre todo por las diversas nubes y el deseo de estar seguros de que allá sigue estando lo que nosotros habíamos puesto.

En [Personal Reflections On Immutable Linux](https://hackaday.com/2025/07/10/personal-reflections-on-immutable-linux/)

> Immutable means “not subject or susceptible to change” according to Merriam-Webster, which is not 100% accurate in this context, but it’s close enough and the name is there so we’re stuck with it. Immutable distributions are subject to change, it’s just that how you change them is quite a bit different than bog-standard Linux.

Tiene un poco que ver, creo, también con la reproducibilidad y tener la tranquilidad de que nuestro entorno de ejecución será parecido al de pruebas.

Nos habla de algunos ejemplos, como MicroOS, OSTree, Silverblue Aurora...

Pero esa inmutabilidad no significa que no podamos instalar nuevos programas y la solución habitual es mediante contenedores (Flatpak, por ejemplo). A partir de ahí muestra cómo MacOS es un Unix inmutable, a través de su aislamiento de las carpetas del sistema en modo de solo lectura. Las actualizaciones vienen como *snapshots* que sustituyen esa parte del sistema completa.

> And Cupertino has been moving towards this “immutable” thing for a long time, until Catalina finally sealed the system folders away completely on a read-only volume. Updates for MacOS also come as snapshots to replace that system volume– you could certainly call them “atomic”.

La pregunta que surge es si esto es aceptable para el escritorio y la respuesta es que, probablemente, para la mayoría sí. Lo demuestra macOS y sus usuarios satisfechos.

> macOS has shown that very few desktop users will ever notice if they can access the system folders or not; they are most interested in having a stable, reproducible environment to work in.

Naturalmente, estas aproximaciones vienen con sus propios inconvenientes: el uso de contenedores supone mayor uso de recursos (memoria y disco, fundamentalmente).

> There are downsides to this kind of system, of course, and it is important to recognize that. Some people really, really hate containerization because Flatpaks, and other similar options, use more memory, both on disk and in RAM.

También nos quita algunas cosas a las que estamos acostumbrados en los sistemas de tipo Linux como el control sobre lo que hay en nuestra máquina, o cambiando la perspectiva, la idea de 'no tocar', derivada de la inmutabilidad.

> From an aesthetic perspective, it’s not as elegant as a traditional Linux environment, at least to some eyes, mine included. Those of us who switched to Linux because we wanted absolute control over our computers might not feel too great about the “do not touch” label implicitly scrawled across the system folders

Finalmente, nos habla de una solución que no es exactamente inmutable, pero que nos permite abordar el problema del control sobre lo que hay en nuestro sistema, como es Nix, ofreciéndonos muchas de las ventajas de la inmutabilidad pero sin renunciar a configurar nuestro sistema.

> After seeing how well containerization can work on desktop, Nix looks extra appealing – it can do most of what this article talks about with the immutable distros, but without trusting configuration of any facet of the system to anyone else.
