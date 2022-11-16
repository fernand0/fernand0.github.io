---
layout: post
title: "¿Se desarrollan los antivirus de manera segura?"
date: "Wed Jun 21 15:45:01 +0100 2017"
category: seguridad
tags: [seguridad, software, seguro, desarrollo, metodos]
imagefeature: https://c2.staticflickr.com/6/5024/5610633717_5a523d780d_m.jpg
---




Los antivirus siguen siendo necesarios: es cierto que no paran lo que no conocen (o lo intentan, pero no siempre lo consiguen) pero colocan una barrera frente a muchos problemas conocidos y reconocidos.

<a href="https://www.flickr.com/photos/fernand0/5610633717/" title="Bicho"><img src="https://c2.staticflickr.com/6/5024/5610633717_5a523d780d_m.jpg" width="240"  alt="Bicho" style="float:left; margin:5px"></a>


En [Why Antivirus Standards of Certification Need to
Change](https://www.tripwire.com/state-of-security/security-data-protection/cyber-security/why-antivirus-standards-of-certification-need-to-change/)
hablan de antivirus y de un viejo tema por este sitio: el software de
seguridad no siempre es seguro.  Tavis Ormandy, del proyecto Zero de Google
visita una empresa de desarrollo de antivirus y no podréis creer lo que
pasó (frase escandalosa para que pudiera aparecer esto bien posicionado
en determinados entornos). 
Él mismo lo contaba en [Security Software Certification](http://blog.cmpxchg8b.com/2016/03/security-software-certification.html).  


> Ormandy came across one such problem recently.

> During his work with Comodo, in whose antivirus solution he discovered “hundreds of critical memory corruption flaws,” the researcher noticed that the security firm was working on receiving its certification from Verizon 

Ni que decir tiene, que consiguieron una buena calificación, lo que nos lleva a dos problemas: 1) el antivirus no está desarrollado de forma segura y 2) los que certifican el antivirus no están preocupados por esas cuestiones.

Podrían empezar utilizando alguna metodología ya conocida:

> Specifically, the researcher recommends that Verizon integrate parts of Microsoft’s Security Development Lifecycle, including dynamic analysis, fuzz testing, and attack surface review, to test each certification candidate against the reality of today’s threats.

Pero el problema no era exclusivo para esta empresa:

> Indeed, in its 2015 State of Infections report, Damballa found that a majority of high-profile antivirus solutions overlooked 70 percent of malware within the first hour.

Y, claro, la consecuencia es todavía peor: instalas el antivirus creyéndote
seguro y no lo estás.

¡Atención!
