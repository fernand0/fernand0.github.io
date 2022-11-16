---
layout: post
title: "La cadena de suministro y a qué principios debemos prestar atención"
date: "2022-04-11 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- cadena
- suministro
- proveedores
imagefeature: 'https://live.staticflickr.com/421/31152325993_9321c190d2.jpg'
---
<a href="https://flickr.com/photos/fernand0/31152325993/" title="Defensa "><img src="https://live.staticflickr.com/421/31152325993_9321c190d2.jpg" alt="Defensa " width="240" style="float:left; margin:5px"></a>
Seguimos con la cadena de suministro. Recordatorio: se trata de atacar alguno de los elementos de los que depende nuestro proyecto, pero que están gestionados por otras personas (servicios, bibliotecas, ...).

En [How Hackers Compromise the Software Supply Chain](https://www.esecurityplanet.com/applications/how-hackers-compromise-the-software-supply-chain/) hablan del tema.

> If you consider all the components you need for your software, you have a
pretty long chain, and those components have dependencies too. Any weak link
can compromise the entire software supply chain, putting your business at
risk.

¿Ocupación de nombres?
Ya habíamos hablado de los paquetes que se llaman parecido a otros legítimos y que la gente termina instalando sin darse cuenta. Imaginemos ahora que un atacante descubre algún nombre de un proyecto que se aloja en un repositorio privado. ¿Podría registrar ese nombre en uno público y engañarnos?

> If hackers find the name of one of the private repositories, they can register
public repositories with the same name and upload their version of what is
supposed to be an internal library.

En cualquier caso, es muy difícil evitar cualquier problema de este tipo que pueda aparecer. Los consejos: seguir una política muy estricta de proveedores, registrar repositorios públicos con los nombres de los privados, actualizar los programas (con sus propios riesgos), asegurar todos los ficheros de configuración, tener especial cuidado con las cuentas privilegiadas (si les engañan a ellos será peor), tener niveles de defensa y monitorización (vigilancia) y compartimentalizar. 
Nada muy nuevo, pero a veces lo olvidamos.

> Have a stricter vendor policy. Don't source from multiple private registries when you can use only one.

> When you register a private repository, register a public repository with the same name to prevent typosquatting.

> Keep all software up to date, even if the update process is now a risk too.

> Secure all configuration files and never deploy them on production, or, at least restrict their access.

> Be extremely careful with IT management interfaces. Privileged accounts with a super high level of access should be few.

> Have several layers of defense and use monitoring tools such as SIEM or SOAR to detect suspicious behaviors early.

> Segment your networks. Don't let any breach at a low level expose the whole system.

