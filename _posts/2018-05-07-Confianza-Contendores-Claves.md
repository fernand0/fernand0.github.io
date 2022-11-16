---
layout: post
title: "Secretos compartidos. Cuidado con la confianza."
date: "Mon May 07 16:02:01 +0100 2018"
category: seguridad
tags: [seguridad, confianza, secretos, contenedores, claves, estudios]
imagefeature: https://c1.staticflickr.com/5/4338/37251899012_eeea0637df_m.jpg
---



<a href="https://www.flickr.com/photos/fernand0/37251899012" title="Oculto"><img src="https://c1.staticflickr.com/5/4338/37251899012_eeea0637df_m.jpg" width="240"  alt="Oculto" style="float:left; margin:5px"></a>
Lo miremos como  lo miremos, somos gente confiada. Queremos compartir y lo hacemos con pocas precauciones. O esa es la conclusión habitual, que ya no nos sorprende mucho. En [Keys, tokens and too much trust found in container images](https://www.helpnetsecurity.com/2017/06/16/trust-container-images/) hablaban del tema relacinado con la compartición de contenedores. 

Comprobaron las 1000 imágenes de contenedores más populares para ver qué encontraban por ahí y encontraron que al menos el 67% de las imágenes contenían, al menos, un secreto:

> To get a taste of the prevalence of such secrets, we scanned the top 1,000 most popular container images found on public registries. We were not only looking for default passwords, but mostly for less obvious examples of secrets. We selected only the latest images, from the top starred public repositories. What we found convinced us that the risk is very real, as 67% of images had at least one form of a secret.

Tokens de acceso, certificados, máquinas no confiables aceptadas como si lo fueran, ficheros de autorización de contraseñas (authorized_keys), etc.

Compartir es bueno. Pero hay que hacerlo con cuidado.
