---
layout: post
title: "Cuando el desarrollador quiere llamar la atención sobre la cadena de suministro"
date: "2022-06-27 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- desarrollo
- desarrolladores
- protesta
- suministro
imagefeature: 'https://live.staticflickr.com/4810/45975957012_312a552253.jpg'
---
<a href="https://flickr.com/photos/fernand0/45975957012/" title="Accionadores de cambio de agujas "><img src="https://live.staticflickr.com/4810/45975957012_312a552253.jpg" alt="Accionadores de cambio de agujas " class="img-responsive img-centered"></a>
Estamos viendo ataques que no habíamos visto nunca. En este caso, el desarrollador de un proyecto lo boicotea para llamar la atención o mostrar su enfado por el estado de las cosas: [Dev corrupts NPM libs 'colors' and 'faker' breaking thousands of apps](https://www.bleepingcomputer.com/news/security/dev-corrupts-npm-libs-colors-and-faker-breaking-thousands-of-apps/)

Los usuarios de bibliotecas populares, como 'colors' y 'faker' descubrieron de manera desagradable que alguien las había cambiado y sus programas empezaban a mostrar cosas diferentes de lo esperado:

>  Users of popular open-source libraries 'colors' and 'faker' were left stunned after they saw their applications, using these libraries, printing gibberish data and breaking.

Algo simple, como introducir un bucle infinito:

>  The developer of these libraries intentionally introduced an infinite loop that bricked **thousands of projects** that depend on 'colors' and 'faker.'

Mostraban basura, y diversos mensajes.

> ... were left stunned on seeing their applications print gibberish messages on their console.

Había una componente revindicativa y de protesta, frente a todas esas empresas que utilizan los programas de software libre sin contribuir.

> The reason behind this mischief on the developer's part appears to be retaliation-against mega-corporations and commercial consumers of open-source projects who extensively rely on cost-free and community-powered software but do not, according to the developer, give back to the community.

La cuestión, claro, es que el software libre funciona así: se publica y lo usa quien quiere (y para lo que quiere) así que igual este desarrollador se equivocó en la forma de distribuir su trabajo.

> "If you have problems with business using your free code for free, don't publish free code. By sabotaging your own widely used stuff, you hurt not only big business but anyone using it. This trains people not to update, 'coz stuff might break."

Hay una componente que siempre veremos cuando utilizamos servicios de tercero y es que GitHub le suspendió la cuenta:

> GitHub has reportedly suspended the developer's account. 

Lo que provoca la paradoja de dejar al desarrollador sin acceso a su propio proyecto. Y a preguntarnos si estamos siguiendo el camino correcto.

> "Removing your own code from [GitHub] is a violation of their Terms of Service? WTF? This is a kidnapping. We need to start decentralizing the hosting of free software source code,...

Todo esto tiene algo de relación con el problema de **log4j** y los problemas que causó en un montón de proyectos que, por supuesto, sólo se quejaban cuando la cosa iba mal.

> But, shortly after mass-exploitation of the Log4shell vulnerability, the maintainers of the open-source library worked without compensation over the holidays to patch the project, ...

Un debate que probablemente haya hecho pensar a mucha gente sobre estos temas.
