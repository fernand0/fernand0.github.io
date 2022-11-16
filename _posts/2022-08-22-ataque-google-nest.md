---
layout: post
title: "Explicando los fallos en el arranque seguro de un Google Nest"
date: "2022-08-22 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- vulnerabilidades
- análisis
- ataques
imagefeature: 'https://live.staticflickr.com/65535/52164028347_cc33b620a2.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52164028347/" title="Bolas chinas concéntricas "><img src="https://live.staticflickr.com/65535/52164028347_cc33b620a2.jpg" alt="Bolas chinas concéntricas " class="img-responsive img-centered"></a>
Seguimos con las entradas veraniegas. Esperamos que sirvan para hacerse una idea (no es necesario comprender todos los detalles) de lo complejos que pueden llegar a ser algunos fallos y los ataques correspondientes.

En este caso hablamos de [Breaking Secure Boot on Google Nest Hub (2nd Gen) to run Ubuntu](https://fredericb.info/2022/06/breaking-secure-boot-on-google-nest-hub-2nd-gen-to-run-ubuntu.html).

Las técnicas son variadas y utilizan algo de lo que hemos hablado de vez en cuando, el *fuzzing*, por ejemplo. No se trata de una contaminación a lo loco, sino con objetivos bastante concretos.

> We build a fuzzing harness that injects data in blk_dread (function that reads data from a block device), and triggers execution by calling fat_read_file. 

Luego, siguen con la técnica para probar con parámetros que un atacante podría controlar.

> In a second phase, we extend the fuzzing to the initialized state since some parameters can be controlled by the attacker. For example, the USB Mass Storage driver sets multiple parameters in structure blk_desc that describe the detected block device in initialized state.

Y algunas cosas más, claro.

En las conclusiones nos cuentan cómo todo este proceso les llevó a encontrar un puerto USB inesperado. Desde allí se podía arrancar con un dispositivo externo, y luego aprovechar otros fallos existentes.

> Hardware exploration led to uncovering an unexpected USB port. Software exploration revealed that it can boot from an USB Mass Storage device. Bug hunting exposed a stack overflow vulnerability in the DOS partition parser.
