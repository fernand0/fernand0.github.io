--- 
layout: post
title: "Ocupación de nombres en paquetes de Ruby"
date: "Mon Jan 04 15:02:01 +0100 2021"
category: seguridad
tags: [seguridad, desarrollo, gemas, ruby, ocupación, nombres, typosquatting]
imagefeature: http://live.staticflickr.com/207/523829842_de2311f514.jpg
---

<a href="https://www.flickr.com/photos/fernand0/523829842/" title="Libro. Por escribir sus nombres "><img src="http://live.staticflickr.com/207/523829842_de2311f514.jpg" alt="Libro. Por escribir sus nombres " width="240" style="float:left; margin:5px"></a>
En [Mining for malicious Ruby gems](https://blog.reversinglabs.com/blog/mining-for-malicious-ruby-gems) por completitud, puesto que ya hablamos de algo similar en [Los nombres y la seguridad. El caso de Python y PyPI](https://fernand0.github.io/Python-Y-Ocupacion-Nombres/).

'Typosquatting' es un tipo de ataque basado en la similitud de nombres, esperando aprovecharse de los errores de los usuarios:

> Typosquatting is particularly interesting. Using this type of attack, the threat actors intentionally name malicious packages to resemble the popular ones as closely as possible (e.g. rspec-mokcs instead of rspec-mocks), in hopes that an unsuspecting user will mistype the name and unintentionally install the malicious package instead.

Como decía, es un tipo de fallos que ya se habían encontrado en Python. Y también en Javascript (`npm`):

> This idea has already proven its merit - we have successfully discovered malicious packages within PyPI, and NPM repositories, as reported in our previous blogs.

En este caso se ocupan de RubyGems y su repositorio.

> RubyGems is a package manager for the Ruby programming language. According to their own site statistics, the repository contains around 158 thousand packages (called gems) with nearly 49 billion total downloads. 

Usan una lista de `gemas` populares y luego observan lo que va sucendiendo:

> In our PyPI and NPM analysis we focused on a large-scale repository analysis. With RubyGems, we employed a slightly different approach. We monitored our gem ingestion queue for typosquatted names, and sent those gems for processing to our Titanium Platform.

En este caso encuentran gemas maliciosas, y un par de usuarios 'peligrosos'. 

> By looking at the RubyGems repository, we discovered that all those gems originated from two user accounts - “JimCarrey” and “PeterGibbons” - with a fairly high number of total downloads.

Muy interesante.
