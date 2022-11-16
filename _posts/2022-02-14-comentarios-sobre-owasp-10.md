---
layout: post
title: "Comentarios sobre el OWASP Top 10"
date: "2022-02-14 15:00:00 +0000"
category: seguridad
tags:
- OWASP
- listas
- fallos
- vulnerabilidades
imagefeature: 'https://live.staticflickr.com/7278/26706208032_569a0011d0.jp'
---
<a href="https://flickr.com/photos/fernand0/26706208032/" title="Araña "><img src="https://live.staticflickr.com/7278/26706208032_569a0011d0.jpg" alt="Araña " width="240" style="float:left; margin:5px"></a>
Vivimos (llevamos viviendo ya bastante así) tiempos confusos.
Por un lado, parece que la seguridad informática tenga que ver sólo con saber encontrar vulnerabilidades y nos recordaba Bernardo Quintero esta mañana que no:

<blockquote class="twitter-tweet"><p lang="es" dir="ltr">Recordatorio ahora que estamos en plena burbuja formativa: ciberseguridad no es saber usar metasploit, ni la mayoría de vacantes en la industria van a estar relacionadas con habilidades ofensivas. Ya, ya se que mola eso de hacer de &quot;hacker&quot;, pero los buenos hackers construyen.</p>&mdash; Bernardo Quintero (@bquintero) <a href="https://twitter.com/bquintero/status/1493211831304925184?ref_src=twsrc%5Etfw">February 14, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

No hay que olvidar que nuestro trabajo será más bien el de proteger nuestros propios sistemas y programas que el de andar descubriendo fallos por ahí.

Por otro lado, hay una gran confusión entre lo que son errores, fallos, vulnerabilidades (y luego si lo son de codificación, de la arquitectura, ...). Todo puede causar problemas, pero de muy diferente nivel.
Yo antes quería pensar que era porque todavía no había madurado suficientemente el conocimiento para hacerlo mejor, pero el tiempo pasa y no cambia casi nada.

El proyecto [OWASP Top 10](https://owasp.org/www-project-top-ten/) es un documento de la OWASP que incluye una lista de problemas de seguridad según lo que se está viendo en cada momento como mayores problemas de seguridad. En este sentido se lanza un proceso de recogida de información de empresas, expertos, ... para recopilar los problemas más frecuentemente observados.
En este sentido, es un indicador valioso porque nos puede ayudar a mirar en aspectos que, a lo mejor, estábamos pasando por alto. O reforzar nuestro criterio con respecto a problemas que otras personas no consideran.

De algunas de estas cosas nos hablaba Daniel Miessler en [Thoughts on the OWASP Top 10 2021](https://danielmiessler.com/blog/thoughts-on-the-owasp-top-10-2021/).

¿Qué es la lista del OWASP Top 10? ¿Una lista de vulnerabilidades? ¿Una lista de categorías? ¿A quién va dirigida?

> Is it a list of vulnerabilities? Is it a list of vulnerability categories? Is this for developers? Is this for security companies? Is this for security tool output labeling? Is it a tool for helping security metrics functions within companies?

Algunos de los problemas son completamente intangibles, como 'Diseño inseguro'.

> The addition of Insecure Design is one of the problems. While I think everyone can agree it's important, it's not a thing in itself. It's instead a set of behaviors that we use to _prevent issues_.

La mezcla de categorías y vulnerabilidades es un problema, nos dice.

> The mixing of categories and vulnerablities has always been a huge problem for me, both as a user and as an OWASP Project Leader.

Y, claro, en algunos casos los problemas pueden caer en varios apartados.

>  Then you have the situations where things can fall into multiple categories. Not turning off FTP on your home router can be Security Misconfiguration and also Insecure Defaults.

Y algo parecido sucede con el registro de seguridad y vigilancia: ¿qué es exactamente lo que se espera de nosotros?

> Security Logging and Monitoring suffers from something similar to Insecure Design. Namely, it sits in this weird realm between tangible and being part of a security review process.

Sin embargo, aparece un problema específico (SSRF, *Server Side Request Forgery*), como vulnerabilidad en esta variada lista.

> And then we have the lonely SSRF at number 10. The only specific issue on the list. I mean it's a good vuln, but it stands out like a vulnerability on a category list, which it is.


La lista tiene valor. Y una buena cantidad de trabajo detrás. Pero igual habría que empezar a pensar en lo que se quiere representar en esta lista y cómo ha de utilizarse.

> The list still provides value. It does. And I appreciate everyone's work on the project. I just think it would be far more useful with more clarity around its identity and intended use
