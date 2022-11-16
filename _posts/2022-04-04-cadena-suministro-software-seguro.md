---
layout: post
title: "La cadena de suministro y la seguridad"
date: "2022-04-04 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- cadena
- suministro
- proveedores
imagefeature: 'https://live.staticflickr.com/78/158926102_7a22d1a293.jpg'
---
<a href="https://flickr.com/photos/fernand0/158926102/" title="Huesca.Semana Santa. Cadenas. "><img src="https://live.staticflickr.com/78/158926102_7a22d1a293.jpg" alt="Huesca.Semana Santa. Cadenas. " width="240" style="float:left; margin:5px"></a>
El (pen)último fallo de moda ha sido, desde este verano, el ataque a la cadena de suministro. 

De ello nos hablan en [Secure software supply chain: why every link matters](https://sysdig.com/blog/software-supply-chain-security/) y nos dicen que se refiere a bibliotecas, código, hardware y otras herramientas que nos proporcionan (o directamente tomamos) otros y que nos sirven para nuestros propios proyectos.

>  In software, the raw materials are common libraries, code, hardware, and tools that transform code into a final deliverable. This deliverable can be deployed as either a user-facing application, a service (starting over with the same supply chain loop), or another package artifact that is included as a dependency, part of a different product. 

Si alguien ataca a alguno de estos proveedors, ¿qué sucederá con nuestro proyecto?

>  Software supply chain attack happens when some malicious element is introduced in this chain.

> A successful attack in any link of the supply can propagate the compromised code or component downstream, completely unnoticed, and cause mayhem across different stages. 

Álvaro Iradier cuenta varios ejemplos, y algunas recomendaciones. La principal: establecer conexiones fuertes con proveedores confiables y verificados.

> So the approach for securing every single piece and link is very different and cannot be covered as a whole. But, whether you are a supplier or a consumer (or both), you need to put the focus on securing your processes and establishing strong connections with trusted and verified providers.
