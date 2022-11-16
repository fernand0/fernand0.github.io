---
layout: post
title: "Una introducción a la autentificación basada en riesgos"
date: "Thu Jan 07 11:50:01 +0100 2015"
category: seguridad
tags: seguridad riesgos autentificación
---


<a href="https://plus.google.com/112862240851570159916/posts/gMRHtV9CA9e" title="Asegurando la autentificación"><img src="https://lh3.googleusercontent.com/-NH80s7ohDbQ/VK0NV5aGzRI/AAAAAAAAJ6A/zz-WP4cgD1Q/w426-h254/15%2B-%2B1" width="240"  alt="Acciones posibles en Facebook" style="float:left; margin:5px"></a>

La autentificación parece ser el gran problema de los últimos tiempos: elegimos malas contraseñas, picamos con facilidad en muchos sitios que nos engañan para que las divulguemos ....

Las soluciones tecnológicas existen, y se pueden utilizar: pero en muchas ocasiones estaremos consiguiendo molestar a nuestros usuarios, que reutilicen contraseñas o que hagan todo lo posible para no seguir nuestras directrices (o peor: irse con la competencia). 

Por eso me gustó [Risk-based Authentication: A Primer](http://deloitte.wsj.com/cio/2013/10/30/risk-based-authentication-a-primer/) donde se introduce la idea de mezclar la autentificación con una estimación del riesgo (que es, por otra parte, lo que creo que están haciendo últimamente muchos sistemas de uso masivo): se asocia a la sesión una 'puntuación' que determina si nuestros parámtros son 'normales'. 

Esto es, mira la localización geográfica, datos de conexión, pautas de comportamiento... Se trata, en definitiva, de ver si todo parece razonable o hay algo que no se ajusta a lo habitual y en caso de que haya motivos para desconfiar se toman medidas adicionales: 

>If the risk score for a user’s access attempt exceeds the system’s risk threshold, authentication controls are automatically elevated, and the user may be required to provide a higher level of authentication, such as a PIN or token. If the risk score is too high, it may be rejected outright.
