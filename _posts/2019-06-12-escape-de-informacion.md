--- 
layout: post
title: "¿Dónde guardas tus secretos?"
date: "Wed Jun 12 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, secretos, github, paper, artículo, git, versiones, control]
imagefeature: https://live.staticflickr.com/4338/37251899012_eeea0637df_b.jpg
---


<a href="https://www.flickr.com/photos/fernand0/37251899012" title="Escondido"><img src="https://live.staticflickr.com/4338/37251899012_eeea0637df_b.jpg" width="240"  alt="Escondido" style="float:left; margin:5px"></a>
El otro día hablábamos de fugas de información a través de los canales de comunicación de las empresas y cómo los 'malos' podían sacar partido de diversos automatismos en [Interacciones inseguras entre sistemas de ayuda y otros](http://fernand0.github.io/Ingenieria-Social-Ataques/). Hoy traemos otro [How bad can it git? Characterizing secret leakage in public GitHub repositories ](https://blog.acolyer.org/2019/04/08/how-bad-can-it-git-characterizing-secret-leakage-in-public-github-repositories/) relacionado con la difusión de secretos que no deberían estar en los sistemas de control de versiones.

Los desarrolladores no deberían incluir secretos en los sistemas de control de versiones, nada nuevo:

> On the one hand you might say there’s no new news here. We know that developers shouldn’t commit secrets, and we know that secrets leaked to GitHub can be discovered and exploited very quickly.

Ofrecen expresiones regulares que podrían utilizarse como chequeo antes de enviar la información al sistema de control de versiones, que pueden encontrarse en el artículo, en [How Bad Can It Git? Characterizing Secret Leakage in Public GitHub Repositories](https://www.ndss-symposium.org/ndss-paper/how-bad-can-it-git-characterizing-secret-leakage-in-public-github-repositories/).

Hay una implementación previa, que incorpora el sistema en [truffleHog](https://github.com/dxa4481/truffleHog) y otro proyecto con ideas similares [git-secrets](https://github.com/awslabs/git-secrets).

Vale la pena leerlo todo, muy interesante.
