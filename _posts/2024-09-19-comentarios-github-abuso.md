---
layout: post
title: "Los nombres son importantes en la nube"
date: "2024-09-19 15:00:00 +0000"
category: seguridad
tags:
- nombres
- archivos
- comentarios
- ataques
- GitHub
imagefeature: "https://live.staticflickr.com/65535/51937193057_6629e03564_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/51937193057/in/photolist-2n8vFZ4-2n8vG2P" title="Incunables en su contenedor"><img src="https://live.staticflickr.com/65535/51937193057_6629e03564_z.jpg" width="640" height="427" alt="Incunables en su contenedor"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

La afirmación habitual de muchos desarrolladores, a veces, es: ¿quién usaría esto para hacer esto otro?. La respuesta de muchos atacantes es: vamos a ver qué podemos hacer con esta característica a la que no han prestado mucha atención.

En este caso hablamos de los comentarios de GitHub y cómo han sido utilizados para enviar *malware* [GitHub comments abused to push malware via Microsoft repo URLs](https://www.bleepingcomputer.com/news/security/github-comments-abused-to-push-malware-via-microsoft-repo-urls/).

La clave está en que al enviar un comentario en GitHub es posible adjuntar un fichero (documentos, archivos, ...) que se subirá al sitio que tienen previsto para ello y que tendrá una dirección web (URL) con el nombre del proyecto.

> When leaving a comment, a GitHub user can attach a file (archives, documents, etc), which will be uploaded to GitHub's CDN and associated with the related project using a unique URL in this format: 'https://www.github.com/{project_user}/{repo_name}/files/{file_id}/{file_name}.'

Pero el problema es que la URL no se genera después de publicar el comentario, sino que está disponible incluso cuando el comentario no ha sido ni siquiera guardado todavía.

> Instead of generating the URL after a comment is posted, GitHub automatically generates the download link after you add the file to an unsaved comment, as shown below.

Se genera la URL, se almacena el fichero, incluso cuando no publiquemos el comentario.

> Even if you decide not to post the comment or delete it after it is posted, the files are not deleted from GitHub's CDN, and the download URLs continue to work forever.

Y estas direcciones parece que son legítimas del proyecto, así que ahí tenemos una vía para distribuir cosas peligrosas.

¡Qué cosas!
