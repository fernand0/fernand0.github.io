---
layout: post
title: "GitHub y algunas pistas sobre desarrollo seguro. Automatización."
date: "2023-02-09 15:00:00 +0000"
category: seguridad
tags:
- desarrollo
- github
- herramientas
imagefeature: 'https://live.staticflickr.com/65535/52579378881_fa7a7c5f8b.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52579378881/in/dateposted/" title="Torre "><img src="https://live.staticflickr.com/65535/52579378881_fa7a7c5f8b.jpg" alt="Torre " class="img-responsive img-centered"></a>
Seguimos con GitHub. En esta ocasión [5 tips for embedding security into your workflows](https://github.blog/2022-10-17-5-tips-for-embedding-security-into-your-workflows/). 
Como dice el título, cinco recomendaciones para integrar la seguridad en nuestro flujo de trabajo.

* Herramientas de seguridad cercanas al código.

Aquí tratan de 'vendernos' sus integraciones, claro.

* Reemplazar una aproximación reactiva por una proactiva.

Que los problemas no nos sorprendan porque ni siquiera habíamos pensado en ellos.

* Mantener una buena relación señal/ruido.

El problema de muchas herramientas de seguridad es que son muy ruidosas: se hace complicado discriminar el grano de la paja y terminan siendo una fuente de molestias en lugar de una ayuda.

> While security tools are needed, they often cause more headache than help. This is because the aforementioned third-party security apps most organizations use are slow, create noise, and may not be integrated into the native developer environment. 

* Permitir la realimentación sobre aspectos de seguridad cuando colaboramos con otros.

Cuando otros colaboran con nosotros (o nosotros con ellos) es bueno poder vigilar lo que va sucendiendo en el código.

* Automatizar los procesos de seguridad.

Cuando sea posible, hacer pruebas y comprobaciones de seguridad de manera automática.

Como decía arriba, se trata de publicitar su servicio [GitHub Advanced Security](https://docs.github.com/en/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security) pero los consejos son relevantes y podemos usar sus herramientas u otras.
