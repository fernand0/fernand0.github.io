--- 
layout: post
title: "Sobre el método usado para generar ficheros .zip"
date: "Mon Aug 10 15:02:01 +0100 2020"
category: desarrollo
tags: [desarrollo, zip, algoritmos, compresión, empaquetado]
imagefeature: http://live.staticflickr.com/2348/2137644411_23bae9346f.jpg
---

<a href="https://www.flickr.com/photos/fernand0/2137644411/" title="¡Oh! ¡Qué bonito! "><img src="http://live.staticflickr.com/2348/2137644411_23bae9346f.jpg" alt="¡Oh! ¡Qué bonito! " width="240" style="float:left; margin:5px"></a>

Casi a título de inventario. Una necesidad frecuente en el mundo de la informática es el empaquetado (reunir varios ficheros/documentos para su distribución, por ejemplo, de manera conjunta) y la compresión (hacer que lo guardado ocupe el menor espacio posible).

En [History, Explanation and Implementation](https://www.hanshq.net/zip.html) nos cuentan el caso del formato zip que no es especialmente bueno ni moderno, pero que se puede entender bien con la voluntad adecuada. Incluye ejemplos de código:

> This article explains how the Zip file format and its compression scheme work in great detail: LZ77 compression, Huffman coding, Deflate and all. It tells some of the history, and provides a reasonably efficient example implementation written from scratch in C. 

La forma en que trabaja este método de compresión es extraer la información común, codificarla adecuadamente y sustituirla por códigos más breves cuando aparezca.

> One way of compressing text is to maintain a list of common words or phrases, and replace occurrences of those words in the text with references to the dictionary. For example, a long word such as "compression" in the original text might be represented more efficiently as #1234, where 1234 refers to the position in the word list. This is known as dictionary-based compression.

Interesante.
