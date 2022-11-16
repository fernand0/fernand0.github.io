--- 
layout: post
title: "Mejorar la seguridad eligiendo mejores lenguajes"
date: "Tue Oct 29 16:05:01 +0100 2019"
category: seguridad
tags: [seguridad, claves, contraseñas, passwords, gestor]
imagefeature: https://live.staticflickr.com/8404/28957143283_52a231f7ba_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/28957143283" title="Ardilla"><img src="https://live.staticflickr.com/8404/28957143283_52a231f7ba_m.jpg" width="240"  alt="Ardilla" style="float:left; margin:5px"></a>
Microsoft lleva años mejorando las herramientas y procedimientos para desarrollar código más seguro. En esa línea podemos leer [A proactive approach to more secure code](https://msrc-blog.microsoft.com/2019/07/16/a-proactive-approach-to-more-secure-code/) donde se habla del problema que suponen los fallos de corrupción de memoria y cómo tratar de evitarlos eligiendo (cuando sea posible) mejores lenguajes desde este punto de vista:

> as Matt Miller discussed in his 2019 presentation at BlueHat IL, the majority of vulnerabilities fixed and with a CVE assigned are caused by developers inadvertently inserting memory corruption bugs into their C and C++ code. As Microsoft increases its code base and uses more Open Source Software in its code, this problem isn’t getting better, it’s getting worse.

Tenemos herramientas, pero los desarrolladores no tienen tiempo para usarlas y también existen cada vez más lenguajes que son seguros desde el punto de vista de gestión de la memoria 

>  If only the developers could have all the memory security guarantees of languages like .NET C# combined with all the efficiencies of C++. Maybe we can: One of the most promising newer systems programming languages that satisfy those requirements is the Rust programming language originally invented by Mozilla. 

Y también tenemos modelos, como la industria del automóvil y todo lo que ha mejorado la seguridad de los viajeros en la evolución de sus procesos.

> We can learn from the way the automotive industry continually evolves their technology to protect drivers and road users. The software security industry has a prerogative to protect the developer in a similar manner.  Perhaps it’s time to scrap unsafe legacy languages and move on to a modern safer system programming language?

Habrá que conocer mejor  [Rust](https://www.rust-lang.org/).
