---
layout: post
title: "Alguien puede estar tratando de conocerte mejor"
date: "Fri Jan 14 11:50:01 +0100 2016"
category: seguridad
tags: [seguridad, servidores, vigilancia, escaneo, ataques, información, meta-información, procesos, debilidades]
---




<a href="https://www.flickr.com/photos/fernand0/3699265044" title="Faro vigilando..."><img src="https://c1.staticflickr.com/3/2424/3699265044_962fae8d8d_m.jpg" width="240"  alt="Faro vigilando..." style="float:left; margin:5px"></a>
Si tenemos acceso al registro de actividad de un servidor cualquiera podemos ver todo tipo de intentos de obtención de información; muchas veces se trata de simples troyanos de máquinas infectadas por ahí que simplemente tratan de propargarse y otras de intentos dirigidos (seguramente más raros en servidores 'caseros').

En [Who’s Scanning Your Network? (A: Everyone)](http://krebsonsecurity.com/2015/05/whos-scanning-your-network-a-everyone/) hablaban del tema entrevistando a Zakir Durumeric y Michael D. Bailey que son investigadores de la Universidad de Michigan y que, entre otros proyectos, mantienen el [Internet-Wide Scan Data Repository](https://scans.io/) que es un archivo público de datos recolectados mediante escaneos de la parte pública de internet.
La respuesta es, como decíamos arriba, que mucha gente nos está vigilando y tratando de obtener información.

Con estos datos son capaces de detectar servidores y servicios vulnerables (e incluso avisarles en situaciones de crisis como el reciente [Heartbleed](http://heartbleed.com/) del que hablamos en su momento en [Heartbleed, código y memoria](http://fernand0.github.io/Heartbleed-Y-Certificados/].

Pero no sólo eso, sino también tener cierta capacidad predictiva, com dice Durumeric en:

> So, if you can watch, for example, how an organization runs their Web server, how they respond to certificate revocation, or how fast they patch — that actually tells you something about the security posture of the organization, and you can start to build models of risk profiles of those organizations. It moves away from this sort of patch-and-break or patch-and-pray game we’ve been playing.

Por supuesto, no hay que olvidar que esto mismo lo pueden hacer los 'malos', vigilando nuestra 'meta'-información pueden ser capaces de encontrar nuestros puntos débiles y los mejores momentos para atacar (como en las películas 'clásicas' de ladrones de bancos, que el atacante aprende los protocolos y momentos adecuados para actuar). 

Dicen muchas más cosas interesantes pero nos recuerdan que la seguridad no sólo es algo tecnológico, sino que también tiene que ver con nuestros procesos y forma de actuar. Y que aunque esa información no sea pública tal vez sea posible deducirla.
