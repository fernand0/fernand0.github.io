---
layout: post
title: "No guardar secretos en repositorios de código"
date: "2021-12-14 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- secretos
- repositorios
- código
- git
imagefeature: 'https://live.staticflickr.com/5300/5543123497_f850371f0c.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/5543123497/" title="Centro de Exposiciones del Centro de Conocimiento sobre se… "><img src="https://live.staticflickr.com/5300/5543123497_f850371f0c.jpg" alt="Centro de Exposiciones del Centro de Conocimiento sobre servicios públicos electrónicos. Almacenamiento. " width="240" style="float:left; margin:5px"></a>
Esto es de primero de seguridad y desarrollo, pero parece que hace falta recordarlo (bueno, vale, ¿quién no ha hecho por error un *commit* con datos delicados?).
En [Why We Shouldn't Commit Secrets into Source Code Repositories](https://littlemaninmyhead.wordpress.com/2021/04/05/why-we-shouldnt-commit-secrets-into-source-code-repositories/) hablan del tema.

Nos dice que enviar secretos a un repositorio es uno de los fallos más frecuentes:

> Committing secrets into source code repositories is one of the most frequent problems I see in application security code review, and has been so for at least 5 years. I'm speaking as one who has reviewed numerous code repositories for a variety of different companies. It is a problem that never seems to go away.

Luego da algunos ejemplos de empresas que se han visto afectadas por este tipo de problemas, como Uber (credenciales de AWS S3), Stackoverflow (que consiguieron acceso al código y, a partir de allí, a más cosas por la información obtenida).O el caso de AShley Madison (un sitio de citas, que también teńia contrasweñas en el código). Y algunos ejemplos más.

Pero casi todo el tiempo hemos estado hablando de secretos (y no de contraseñas) porque, nos dicen, las claves SSH, las conexiones a bases de datos y otras informaciones también deberían ser secretas. Y en caso de duda, casi cualquier información. Cuidado.

> Educate engineers that "secrets aren't just passwords." Protect SSH keys and database connection strings too. When in doubt, protect it. If you must store secrets in a Git repo, protect them with git-crypt or Blackbox."
