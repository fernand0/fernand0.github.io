---
layout: post
title: "La IA genera más fallos de seguridad y a más velocidad"
date: "2026-08-10 14:00:00 +0000"
category: seguridad
tags:
- seguridad
- programación
- desarrollo
- IA
- herramientas
imagefeature: "https://live.staticflickr.com/65535/55409660230_380067a87f_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/55409660230/" title="Armadura del Sultán Mustafá III"><img src="https://live.staticflickr.com/65535/55409660230_380067a87f_z.jpg" width="427" height="640" alt="Armadura del Sultán Mustafá III"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Cualquiera que venga por aquí de vez en cuando imaginará que esto es así. En [AI Coding Tools Are Creating a Security Gap We Must Close Immediately](https://www.veracode.com/blog/ai-coding-tools-security-gaps/) (que lei a través de [AI code generators are writing vulnerable software nearly half the time](https://nerds.xyz/2025/07/ai-security-flaws-veracode-2025/) pero ahora parece no estar disponible) nos dicen que a los desarrolladores les gusta mucho usar los LLMs: escriben código más rápido, hacen menos trabajo repetitivo y se pueden añadir más características fácilmente.

> Developers love AI coding tools. And why wouldn’t they? After all, they write code faster. They reduce repetitive work. They help junior engineers ship features that used to take days.

Pero hay un problema, esta aceleración también se produce en la generación de fallos y problemas de seguridad.

> AI coding tools are producing insecure code at massive scale. And the industry is running out of time to fix it.

Si lo pensamos, esto es normal: con tanto código malo como hay por ahí disponible, seguramente al entrenar a esos LLMs no se habrá filtrado adecuadamente el código malo.

El resumen que nos da es que solo el 55% del código generado en las pruebas de Veracode pasa pruebas básicas de seguridad.

> Here it is, plain and simple. Across more than 150 large language models tested, only 55% of AI-generated code passes basic security tests.

Por ponerlo más claro: en casi la mitad del código generado por un LLM se introduce alguna vulnerabilidad **conocida**.

> That means in nearly half of all cases, an AI coding tool may introduce a known security vulnerability directly into your codebase.

El contraste es interesante, porque es código es perfecto desde el punto de vista sintáctico, pasa las pruebas unitarias, se mezcla con el código anterior ...

> What makes this worse is the contrast. Those same AI models achieve syntax correctness rates above 95%. The code looks right. It runs. It passes unit tests. It gets merged. And it contains a security hole.

Algunos tipos de fallo son mejores que otros, por ejemplo para la inyección de SQL los modelos alcanzan un 82% de paso de las pruebas de seguridad, y en el caso del uso inseguro de criptografía es incluso mejor, el 86%. Son datos ampliamente disponibles y bien conocidos.

> For SQL injection, AI models achieve an 82% security pass rate. For insecure cryptographic algorithms, it’s 86%. These are common, well-documented patterns. The models have seen them thousands of times in training data. They’ve learned to avoid the obvious anti-patterns.

Sin embargo, si nos referimos a la inyección cruzada (*cross-site scripting (XSS),*), la cosa baja a un 15% (¡Ay la web!) y en el caso de inyección en el registro de actividad (*log injection*) estamos hablando del 13% ¿tus programadores se preocupan de lo que se escribe en el registro de actividad?.

Nos dice que la cosa no ha mejorado en estos años con los sucesivos modelos, porque son buenos con el manejo de patrones, y lo que ya han visto, pero no lo son tanto con razonamientos sutiles, dependientes del contexto y de su lógica.

> These numbers have barely moved since initial research began two years ago. This isn’t a bug that’s getting patched. It’s a structural limitation. AI models are pattern-matchers. They’re excellent at reproducing what they’ve seen. They’re poor at reasoning through subtle, context-dependent security logic — exactly the kind that produces XSS and log injection vulnerabilities.

Hay alguna excepción, como OpenAI con su ChatGPT 5, con una tasa de paso de entre 70–72%, pero eso deja todavía un 30% de código con fallos.

> There is one bright spot worth noting. OpenAI’s reasoning-focused models — the GPT-5 series with extended reasoning — achieved security pass rates between 70–72%. That’s a real improvement over the standard 55% baseline. It suggests that models built to think through problems, not just autocomplete them, produce safer code. But 70% still means 30% of AI-generated code contains known flaws. That’s not a solution. It’s a direction.

Naturalmente, esto conduce al éxito de los ataques, con el 81% de las organizaciones siendo víctimas de ataques exitosos.

>  81% of organizations experienced at least one successful cyberattack in the past year. And the number of organizations suffering six or more successful attacks is actually increasing.

Y sin olvidar que los malos también usan las herramientas, generando programas maliciosos guiados por IA.

> The 2026 Cyberthreat Defense Report found that AI-enabled evasive malware is the number one AI-related threat concern, cited by 45.5% of security professionals.

Como solemos decir, el problema no es por generar código rápido, el problema está en confiar en ese código demasiado pronto. Sobre todo porque el verdadero cuello de botella es arreglar ese código cuando aparecen problemas.

> The real bottleneck has always been fixing them, governing how they enter codebases, and proving to boards, regulators, and customers that the software you’re running is trustworthy.

Nos recomiendan, por lo tanto, priorizar:

1. No lo arregles todo. Arregla primero lo correcto.

> 1. Stop trying to fix everything. Fix the right things first.

2. Pídele seguridad a la IA, no es una sugerencia.

> 2. Make security prompting a standard, not a suggestion.

3. Reemplazar las pruebas manuales por pruebas automatizadas.

> 3. Replace manual testing with continuous, automated scanning.

4. Construye visibilidad antes que planes de reparación.

> 4. Build visibility before you build remediation plans.

5. Demuéstralo. Al comité, los reguladores, y los clientes.

> 5. Prove it — to your board, your regulators, and your customers.

A pesar de que se trata de un texto de parte (venden herramientas, consultoría sobre seguridad, ...) me parece un texto muy interesante y valioso.
