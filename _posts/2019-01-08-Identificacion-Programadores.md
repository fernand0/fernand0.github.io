--- 
layout: post
title: "¿Quién programó esto?"
date: "Tue Jan 08 16:15:01 +0100 2019"
category: desarrollo
tags: [desarrollo, anonimato, programadores, identificación, estilo]
imagefeature: https://c2.staticflickr.com/6/5223/5782150733_e0c82e05e8_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/5782150733" title="Código"><img src="https://c2.staticflickr.com/6/5223/5782150733_e0c82e05e8_m.jpg" width="240"  alt="Código" style="float:left; margin:5px"></a>
Durante el año pasado se ha hablado mucho de *machine learning* e inteligencia artificial. Traemos aquí un artículo sobre identificación de programadores, que podíamos leer en [Even anonymous coders leave fingerprints](https://www.wired.com/story/machine-learning-identify-anonymous-code/).

La idea es sencilla: tenemos código de varios programadores (por ejemplo, de sus repositorios públicos) y tenemos un código fuente del que desconocemos la autoría. En el artículo nos cuentan que podríamos identificar al autor con una probabilidad bastante buena de acertar.

El resultado se presentó en una conferencia de seguridad y utilizaba *machine learning* (aprendizaje automático) para des-anonimizar los autores de algunas muestras de código.

> At the DefCon hacking conference Friday, the pair will present a number of studies they've conducted using machine learning techniques to de-anonymize the authors of code samples. 

Podría utilizarse para dirimir temas relacionados con la copia (el plagio que también ha estado de moda desde el verano). También podría preocupar a programadores que contribuyen a proyectos de software libre.

> Their work, some of which was funded by and conducted in collaboration with the United States Army Research Laboratory, could be useful in a plagiarism dispute, for instance, but also has privacy implications...

Curiosamente, los programas se hacen en lenguajes estructurados donde la sintáxis es más o menos rígida, no hay mucha variedad de palabras para elegir... Pero aún así, hay características únicas para cada persona que programa.

> Think of every aspect that exists in natural language: There's the words you choose, which way you put them together, sentence length, and so on. Greenstadt and Caliskan then narrowed the features to only include the ones that actually distinguish developers from each other ...

Por ejemplo, la estructura del código

> Their technique is akin to prioritizing someone's sentence structure, instead of whether they indent each line in a paragraph.

Aparentemente, estos aspectos sobrevivirían incluso a algunas de las técnicas de ofuscación del código empleadas habitualmente.

> ... have found that some off-the-shelf obfuscation methods, tools used by software engineers to make code more complicated, and thus secure, aren't successful in hiding a developer's unique style.

Y, claro, el estilo se desarrolla con el tiempo y la experiencia:

> For example, they have found that experienced developers appear easier to identify than novice ones. The more skilled you are, the more unique your work apparently becomes. 

También contribuye si el problema que se va a resolver es más complicado.

> Similarly, they found that code samples addressing more difficult problems are also easier to attribute. Using a sample set of 62 programmers, who each solved seven "easy" problems, the researchers were able to de-anonymize their work 90 percent of the time. When the researchers used seven "hard" problem samples instead, their accuracy bumped to 95 percent.

Interesante.
