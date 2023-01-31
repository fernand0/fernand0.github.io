---
layout: post
title: "GitHub y OWASP"
date: "2023-01-23 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- github
- OWASP
- herramientas
- top10
imagefeature: 'https://live.staticflickr.com/176/399144526_e289577520.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/399144526/" title="The pila seguridad "><img src="https://live.staticflickr.com/176/399144526_e289577520.jpg" alt="The pila seguridad " class="img-responsive img-centered"></a>
Desde que empecé a fijarme en los temas relacionados con el desarrolo seguro me ha llamado mucho la atención el proyecto <a href="https://owasp.org/">OWASP</a>: un grupo de voluntarios proporcionando información, documentación, consejos,... y siendo referenciados desde las más diversas fuentes como un proyecto que hay que tener en cuenta.

En esta ocasión se trata de GitHub, y [How to mitigate OWASP vulnerabilities while staying in the flow](https://github.blog/2022-11-04-how-to-mitigate-owasp-vulnerabilities-while-staying-in-the-flow/) donde tratan de reflejar las caracterísiticas y procesos de seguridad en los que GitHub puede ayudarnos, con referencia al proyecto OWASP.

Se habla, en particular, del [OWASP Top 10](https://owasp.org/www-project-top-ten/), con su lista de fallos frecuentes e importantes.

> Fortunately, the Open Web Application Security Project (OWASP) can help. OWASP provides a Top 10 list of vulnerabilities that gives developers and organizations the context they need to address security and compliance risks within their applications.

GitHub tiene un libro sobre el tema, [Secure code without disrupting innovation](https://resources.github.com/appsec/) que no conocía. 

Los fallos que comentan son:

* Fallos relacionados con la criptografía.

Fundamentalmente se concentran en los secretos que pueden ser difundidos a través del sistema de gestión del código.

> However, sometimes API keys, clear text passwords, security tokens, and other sensitive data may remain in code, leading to cryptographic vulnerabilities.

* Fallos de inyección.

Como todos saben, fallos de inyección pueden ocurrir en la web, pero también en los caminos (*paths*) de nuestras llamadas, en las órdenes SQL, ...

> Cross-site scripting, path injection, SQL injection, and NoSQL injection are several of the vulnerabilities that have plagued applications for years and continue to stay in the OWASP Top 10 list.

* Diseño inseguro.

Se centra, en este caso, en el modelado de amenazas.

> Threat modeling strategies can be implemented to encourage collaboration between developers, security professionals, and even risk management teams.

* Componentes vulnerables y desactualizadas.

De nada sirve diseñar nuestro código con seguridad si luego depende de componenetes que no tenemos adecuadamente actualizadas.

> One of the best strategies for managing the risk of vulnerable and outdated components is to alert developers as soon as a security threat is found and give them the ability to take action in their normal workflows and tooling.

