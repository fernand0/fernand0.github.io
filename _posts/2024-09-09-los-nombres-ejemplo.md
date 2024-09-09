---
layout: post
title: "Los nombres son importantes en la nube"
date: "2024-09-09 15:00:00 +0000"
category: seguridad
tags:
- nombres
- recursos
- colisiones
- ataques
imagefeature: "https://live.staticflickr.com/42/84771552_5aef10ecaf_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/84771552/in/photolist-4aaFZT-4dFXsq-4f3pjr-4hMNoP-4hRUzj-duyF-duyR-tQzpw-5QdnmL-5Qdo7G-hKcU-hKdi-v6wJF-hXAN-6bhcwF-xioXt-6EKZ8-6EL3N-7waXk-7Y6WM-7Y74J-8sePF-8utCu-8utRb" title="Otro paquete"><img src="https://live.staticflickr.com/42/84771552_5aef10ecaf_z.jpg" width="640" height="492" alt="Otro paquete"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>


En [How an empty S3 bucket can make your AWS bill explode](https://medium.com/@maciej.pocwierz/how-an-empty-s3-bucket-can-make-your-aws-bill-explode-934a383cb8b1) un (otro) recordatorio de la importancia de los nombres de las cosas.

En este caso, descubierto por casualidad: el autor habilita un entorno en la nube para una prueba de concepto de un cliente suyo, sube unos documentos y dos días después, cuando vuelve a mirarlo, se encuentra con una factura importante.
En un servicio que en teoría casi no había tenido uso:

> A few weeks ago, I began working on a PoC of a document indexing system for my client. I created a single S3 bucket in the eu-west-1 region and uploaded some files there for testing. Two days later, I checked my AWS billing page, primarily to make sure that what I was doing was well within the free-tier limits. Apparently, it wasn’t. My bill was over $1,300, with the billing console showing nearly 100,000,000 S3 PUT requests executed within just one day!

¿El problema?

El nombre que había elegido para su recurso coincidía con uno que utiliza una conocida herramienta por defecto.

> Was it some kind of DDoS-like attack against my account? Against AWS? As it turns out, one of the popular open-source tools had a default configuration to store their backups in S3. And, as a placeholder for a bucket name, they used… the same name that I used for my bucket.

Eso era un riesgo solo por los accesos de consultas, pero también podría ser un asunto de seguridad si se permite escribir, porque alguien lo hará y puede encontrarse con sus datos confidenciales por ahí.

> I opened my bucket for public writes and collected over 10GB of data within less than 30 seconds. Of course, I can’t disclose whose data it was. But it left me amazed at how an innocent configuration oversight could lead to a dangerous data leak!

Además del susto, algunos aprendizajes:

* Si alguien conoce los nombres de nuestros recursos puede darnos un buen susto con la factura

> Lesson 1: Anyone who knows the name of any of your S3 buckets can ramp up your AWS bill as they like.

* Siempre es una buena idea añadir un sufijo aleatorio a nuestros recursos para que sea más difícil que el nombre coincida con el que alguien pueda usar.

> Lesson 2: Adding a random suffix to your bucket names can enhance security.

* Controlar desde dónde se puede acceder a los recursos, por lo menos.

> Lesson 3: When executing a lot of requests to S3, make sure to explicitly specify the AWS region.

