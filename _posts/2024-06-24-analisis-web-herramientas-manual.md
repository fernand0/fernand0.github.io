---
layout: post
title: "Las limitaciones de los analizadores de código para la seguridad"
date: "2024-06-24 15:00:00 +0000"
category: seguridad
tags:
- desarrollo
- analizadores
- seguridad
- código
imagefeature: "https://live.staticflickr.com/65535/53794868454_a5bf834526_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/53794868454/in/dateposted/" title="Piedras"><img src="https://live.staticflickr.com/65535/53794868454_a5bf834526_z.jpg" width="427" height="640" alt="Piedras"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

El análisis de una aplicación (web o no) para detectar problemas de seguridad es una tarea inexcusable que puede llevar una buena cantidad de tiempo. Hay herramientas pero, como siempre, llegan hasta donde llegan y eso puede ser un problema.

En [The Blind Spots of Automated Web App Assessments](https://baldur.dk/blog/automated-web-assessment.html) nos hablaban un poco de este asunto y de la importancia de la revisión manual.

> This post illustrates the importance of manual code review when doing application security. Relying heavily on automated tools can give you some grim blind spots that pose a significant risk to the application.

Para ello, seleccionan varios fallos habituales y ven cómo se comportan diversos analizadores. El problema fundamental que detecta es que los analalizadores no suelen ser capaces de determinar el contexto ni la lógica de negocio, con lo que algunos fallos pueden pasarse por alto.

> The scanners simply can't do this. All of these rules are application logic which is laws defined by the programmer. One application might have a friend invitation system where you actually are allowed to view other users profiles. Another is a private application where you are only supposed to see your own profile. How does the scanner distinguish between these rules that are man made on a project-to-project basis?

Sin embargo, esto no es una llamada a dejar de usar ese tipo de herramientas, sino a ser conscientes de sus limitaciones.

> We're not here to tell you to stop using automated tools. They're great for the job, but you should use them with an understanding of what might be missed if you don't couple them with manual assessments by a vetted application security professional.

Interesante.
