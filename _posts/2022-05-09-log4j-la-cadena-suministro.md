---
layout: post
title: "Lo que podemos aprender sobre el fallo de Log4j y la cadena de suministro"
date: "2022-05-09 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- bibliotecas
- cadena
- suministro
- desarrollo
imagefeature: 'https://live.staticflickr.com/65535/49477091236_aac1401425.jpg'
---
<a href="https://flickr.com/photos/fernand0/49477091236/" title="Campanas "><img src="https://live.staticflickr.com/65535/49477091236_aac1401425.jpg" alt="Campanas " class="img-responsive img-centered"></a>
A finales del año pasado se estuvo hablando de la [Vulnerabilidad crítica en Apache Log4j](https://www.incibe.es/protege-tu-empresa/avisos-seguridad/vulnerabilidad-critica-apache-log4j).
Rápidamente se le puso remedio, se empezó a discutir sobre el asunto (¿dependemos de programas que desarrolla gente en su tiempo libre o con pocos recursos? y otros temas relacionados), se actualizó quién pudo y allí seguimos.

en [Log4j postmortem: Developers are taking a hard look at software supply-chain security gaps](https://www.techrepublic.com/article/log4j-postmortem-developers-are-taking-a-hard-look-at-software-supply-chain-security-gaps/) se hablaba del asunto con más calma y por eso lo traemos aquí. 

El primer problema (y ya lo anunciábamos diciendo lo de *quién pudo*) es que no siempre es tan fácil actualizar los sistemas y eliminar las versiones vulnerables.

> One of the most troublesome aspects of Log4j was not the vulnerability itself, but how deeply embedded the technology is in legacy code. After all, Java is one of the world's most popular platforms, and Log4j is an incredibly popular Java logging system whose initial release dates all the way back to 2001. So Log4J touches not only a ton of production systems, but also a lot of legacy code.

Y no es que no haya voluntad; el problema es que, a veces, intentando arreglar algo estropeas otra cosa. Y ni siquiera puedes estar muy seguro de si lo hiciste bien.

>  "You don't just need to fix a security vulnerability, you need to know that you fixed the vulnerability without breaking your system. When you have a vulnerability with a super popular logging library like Log4j, you are talking about dependencies on legacy code that typically lacks any testing, and where sometimes the developers who wrote the code and understand how it works don't even work at the company anymore."

Sin olvidar que cualquier reparación tiene que tener un análisis del coste/beneficio. En particular, cómo y a cuántos usuarios pueden afectar nuestras soluciones.

>  "There is a cost-benefit analysis that needs to take place on any
security remediation. You have to determine the right interval to deploy the
fix, which requires a complete understanding of the risk in terms of how many
users it could affect, and the acceptable level of unreliability you can
accept."

Al final las aplicaciones modernas están construidas a partir de muchas piezas, que a lo mejor ni siquiera tenemos inventariadas.

> "Modern applications are built from many components, many of which are not developed in-house but are rather assembled using 'off the shelf' solutions," according to John France, CISO at (ISC)2. "A large part of qualifying and identifying issues is knowing what components and libraries are used by your software and keeping a software bill of materials (SBOM)." 

Hasta ahora hemos sido muy laxos a la hora de tener en cuenta los riesgos que se asumen por utilizar este código de terceros.

> "Developers in general have been very lax about tracking what they use in their software. When an event like this requires us to identify whether some library or component is used by our code, that lack of traceability becomes a major pain point. It turns a simple exercise of checking inventories and SBOMs into a complex scanning process, with many opportunities for false positives and false negatives. If we ever needed a wake-up call, we got a big one with Log4j."

Tal vez este incidente sea la llamada que hacía falta para empezar a prestar atención.
