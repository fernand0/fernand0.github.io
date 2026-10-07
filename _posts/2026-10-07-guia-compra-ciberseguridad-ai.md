---
layout: post
title: "¿Cómo validar a los proveedores de productos de seguridad que incluyen IA?"
date: "2026-10-07 14:44:36 +0200"
category: seguridad
tags:
- seguridad
- IA
- vendedores
- productos
- consejos
imagefeature: "https://live.staticflickr.com/7417/11685239403_a59b0f3418_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/11685239403/" title="Tienda navideña"><img src="https://live.staticflickr.com/7417/11685239403_a59b0f3418_z.jpg" width="640" height="427" alt="Tienda navideña"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Ya había productos de ciberseguridad que decían utilizar la IA para protegernos antes de la explosión de la IA generativa: algunos CISOs apoyaban estas aproximaciones y otros las miraban con escepticismo. Sin embargo, ahora ya parece fuera de toda duda que la IA debe incluirse en el arsenal defensivo de cualquier empresa. En [A CISO's Guide to Vetting AI Security Vendors](https://calebsima.com/writing/a-cisos-guide-to-vetting-ai-security-vendors) dan algunas recomendaciones sobre la elección de proveedores, basándose en tres pilares.

* ¿Resuelven algún problema importante?

> Pillar 1: The Problem — Are You Solving Anything That Matters?

Se basa en un par de preguntas interesantes: ¿qué problema está resolviendo esta IA?

> "What specific pain is your AI solving?"

Y la respuesta debería ser concreta, fácil de entender...

> A vendor who can give you a concrete, understandable example of their product's value actually understands the problem.

¿Realmente es necesaria la IA para eso?

> "Why is AI necessary here? How is it superior to simpler methods?"

Esta es una pregunta que deberíamos estar haciéndonos en todos los ámbitos, claro: leí en algún sitio (y trato de seguirlo) que no deberíamos utilizar IA si lo podemos resolver con un programa 'normal'.
O, como dice en el texto, a veces un centenar de expresiones regulares puede producir mejores resultados que un modelo malo al que llaman IA.

> Many times, a hundred regular expressions can produce better results than a poorly implemented model, but the vendor just calls it "AI."

* ¿Realmente funciona?

> Pillar 2: The Proof — Does It Actually Work?


En este caso, la primera pregunta sería ¿Cuáles son los datos de entrada de tu modelo? ¿Qué algoritmo utilizas?

> "What are the inputs to your model? What algorithms are you using?"

Se trata de conocer cómo funciona el producto.

También sobre la calidad, ¿qué tasas de falsos positivos y falsos negativos tiene el modelo?

> "What are your model's false positive and false negative rates?"

Se trata de hablar de precisión y sensibilidad (*recall*): si no pueden darnos esa información es porque probablemente no la conocen, no les interesa, o no es muy buena.

> Any serious AI vendor tracks precision and recall. If they can't give you hard numbers, that's a red flag. Ask for them in the context of a real customer deployment, not a lab test.

¿Cómo maneja el modelo las amenazas que nunca antes se han visto?

> "How does your system handle a threat it has never seen before?"

No debemos olvidar que algunas IAs (LLMs, en particular) proporcionarán respuestas aleatorias en esos casos.

> If you pass an LLM a complex attack with multiple TTPs it hasn't seen before, it might have low confidence and just spit out random MITRE ATT&CK categories.

* ¿Cómo impactará esto en mi equipo?

> Pillar 3: The Practicality — How Will This Impact My Team?

La primera pregunta sería ¿cuál es el verdadero coste de tener esta solución?

> "What is the true cost of ownership?"

No se trata de hablar solo del coste de la licencia sino de otros aspectos (el propio funcionamiento, ¿va incluido en la suscripción o aparecerá en mi factura de operaciones en la nube?

> This isn't just the license fee. If the product is feeding massive amounts of data into an LLM, who pays the inference cost? Is it included in your subscription, or is that going to show up on my cloud bill?

Pero también el coste para las personas: ¿cuánto tiempo necesitarán para validar las alertas y resultados que ofrezca la herramienta?

> Even more importantly, what is the cost of my team's time? If my analysts have to spend their days validating the AI's output, I haven't saved them work; I've just shifted it.

Otra pregunta interesante estaría relacionada con la corrección de errores: ¿si encontramos fallos podemos hacer que la IA aprenda para que no los vuelva a cometer?

> "Can my analysts correct the AI's mistakes, and does it learn from them?"

La última pregunta tendría que ver con la explicabilidad y el cumplimiento: ¿cómo proporciona el sistema la información para los auditores?

> "How does your system provide 'explainability' for auditors or the board? I need to see detailed decision logs, confidence scores, and visualization tools."

Complementa el escrito con las señales de alarma (*red flags*) que incluyen las típicas que hemos visto en otros contextos:

* Nuestro producto es propietario y no podemos darte detalles.

> "Our AI is proprietary and we can't share details." Transparency is non-negotiable.

* No hacemos seguimiento de la tasa de falsos positivos.

> "We don't track false positive rates." If they don't measure accuracy, they can't improve.

* Funciona sin tener que tocar nada.

> "It works out of the box with no tuning." Real-world environments always require configuration.


Buena lista de recomendaciones.







