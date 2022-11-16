---
layout: post
title: "SSL para todos en CloudFare y la escala"
date: "Mon Jan 04 13:15:01 +0100 2016"
category: seguridad
tags: [seguridad, SSL, TLS, HTTPS, cifrado, cloudfare, velocidad, mejoras, trucos, prestaciones]
---




<a href="https://plus.google.com/u/1/photos/photo/112862240851570159916/6235906524022236338" title="Candados"><img src="https://lh3.googleusercontent.com/LU1L9qOFGyFd67iUD-Cv9Jqy66KG3MUJR92NBFC922Ok_8b_2GG5B5ITBla34M07EPBv=w1680-h1050-no" width="240"  alt="Candados" style="float:left; margin:5px"></a>
Uno de los problemas e utilizar SSL (TLS hoy en día) es el coste computaional: con muchas visitas las conexiones cifradas pueden ser un sobrecoste que no estemos dipuestos a asumir. 

En [Universal SSL: How It Scales](https://blog.cloudflare.com/universal-ssl-how-it-scales/) Nick Sullivan de CloudFlare nos habla de su proyecto (ya tiene más de un año) de proporcionar HTTPS para todos los sitios albergados por ellos (que es una decisión a la que parece que se está dirigiendo mucha más gente cada vez) y hablan de este sobrecoste:

> People have asked us, both in comments and in person, how our servers handle this extra load. The answer, in a nutshell, is this: we found that with the right hardware, software, and configuration, the cost of SSL on web servers can be reduced to almost nothing.

Alguno de los trucos está basado en cuestiones como retomar sesiones:

> For returning visitors of a site we have a shortcut that eliminates the need for our servers to perform these expensive operations. The shortcut is called session resumption and it's built into the TLS specification.

Otras medidas utilizadas son el *Lazy Loading*:

> Lazy loading of certificates helps relieve that bottleneck. Using custom modifications to nginx by CloudFlare engineer Piotr Sikora, we are able to dynamically load certificates into memory only when they’re needed. Now, if one site changes their certificate, the server does not have to reload every certificate. This change allows our servers to scale up to handle millions of HTTPS sites.

Todo ello combinado con algoritmos modernos (Criptografía de curvas elípticas, ECDSA) y hardware actualizado:

> All Intel CPUs based on the Westmere CPU microarchitecture (introduced in 2010) and later have specialized cryptographic instructions.
