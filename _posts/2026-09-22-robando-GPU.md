---
layout: post
title: "Los atajos salen caros, también en defensa."
date: "2026-09-22 14:44:36 +0200"
category: seguridad
tags:
- seguridad
- malware
- trucos
imagefeature: "https://www.flickr.com/photos/fernand0/55465265819/"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/55465265819/" title="Trono"><img src="https://live.staticflickr.com/65535/55465265819_7d8f0b88f1_z.jpg" width="427" height="640" alt="Trono"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En [“GPUGate” Malware Abuses Google Ads and GitHub to Deliver Advanced Malware Payload](https://cybersecuritynews.com/gpugate-abuses-google-ads/) nos contaban cómo atacaban a usuarios poco vigilantes mediante anuncios y enlaces a GitHub.

1. Aparece un anuncio malicioso, que apunta a un enlace que aparentemente es de GitHub, con un producto que parece 'interesante' (*GitHub Desktop*)

> The attack begins with malicious advertising, where attackers place a sponsored ad at the top of Google search results for terms like “GitHub Desktop.” This ad directs users to what appears to be a legitimate GitHub page.

2. El enlace lleva a un página de GitHub dentro de un repositorio, todo parece legítimo, pero allí hay enlaces de descarga alterados.

> In reality, the link leads to a specific, manipulated “commit” page within a repository. This page looks authentic, retaining the repository’s name and metadata, but contains altered download links that point to an attacker-controlled domain.

3. Para evitar los filtros de contenido el tamaño del instalador es muy grande (para aprovecharse de que muchos mecanismos de seguridad que tienen limitación de tamaño).

> What makes GPUGate particularly notable is its unique evasion method. The initial installer is a large 128 MB file, designed to bypass security sandboxes that often have file size limits.

4. Finalmente, y para evadir la vigilancia mejor, solo se activa en caso de que haya disponible una GPU.

> Its most innovative feature is a GPU-gated decryption routine. The malware will only decrypt its malicious payload if it detects a real, physical GPU with a device name longer than ten characters, Arctic Wolf said.

En este caso se está abusando de la confianza en los anuncios de Google, y en las páginas de GitHub. Pero eso es un problema, claro.

> This “trust bridge” exploits the user’s confidence in both Google and GitHub to deliver the malicious payload.

Además, se implantan algunas medidas que son habituales en las máquinas de vigilancia y de los analistas, lo que haría más difícil la detección y análisis.

Curioso.
