---
layout: post
title: "Ataques a los datos de entrenamiento de inteligencias artificiales"
date: "2022-01-17 15:00:00 +0000"
category: IA
tags:
- inteligencia artificial
- IA
- ataques
- contaminación
- envenenamiento
imagefeature: 'https://live.staticflickr.com/5504/10044005026_63e84e9910.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/10044005026/" title="Calentando "><img src="https://live.staticflickr.com/5504/10044005026_63e84e9910.jpg" alt="Calentando " width="240" style="float:left; margin:5px"></a>
Solemos decir que tomamos decisiones basadas en los datos. El problema que surje con esto es cuando nuestros datos no reflejan adecuadamente la realidad.
En el mundo de la inteligencia artificial esto podría ser un problema, tal y como nos cuentan en [Data poisoning in action](https://blog.f-secure.com/data-poisoning-in-action/).

Si podemos introducir errores en los modelos que se utilizan para entrenar las inteligencias artificiales, podremos causar problemas:

> Data poisoning attacks compromise the integrity of machine learning models by injecting incorrect data in their training set.

Se trata de modificar un conjunto de datos de los que se emplean en el entrenamiento, para lograr que el resultado sean predicciones incorrectas.

> A data poisoning attack aims to modify a training set such that the model trained using this dataset will make incorrect prediction

El objetivo es degradar el modelo obtenido (en el entrenamiento o cuando se le alimentan nuevos datos para volver a entrenarlo). Estos ataques podrían tener un efecto duradero, porque comprometen la integridad del modelo y le hacen cometer errores de  manera consistente. Una vez comprometido, recuperar el sistema es un problema de solución no trivial.

> Poisoning attacks have a long-lasting effect because they compromise the integrity of the model and cause it to make consistent errors at _runtime_ when making predictions. Once a model has been poisoned, recovering from the attack at a later date is a non-trivial procedure.

Como ejemplo, nos habla de lo que sucedería si en un modelo orientado a detectar pedidos fraudulentos (y que, lógicamente, se entrenará con pedidos reales anteriores). Podría contaminarlo realizando una serie de pedidos y luego pagando algunos y otros no, con lo que podría conseguir degradar la capacidad de predicción.

> The model should be able to predict whether a placed order will be paid for ( _legitimate_ ) or not ( _fraudulent_ ) based on information about the given order. The training set for this model consists of details contained in historical orders placed on the website. In order to poison this training set, an attacker would pose as a user or users of the site and place orders. The attacker pays for some orders and doesn't pay for others such that the predictive accuracy of the model is degraded when it is next trained.

Hay dos formas de contaminar estos datos:

* Inyección de datos, tal y como decíamos arriba.

> Data injection: by injecting new data in the training set, as illustrated above with the attacker creating new orders. This new data can be synthetic in nature.

* Cambio de etiquetas. Esto es, se trata de cambiar los valores que asigna el modelo a algunos datos.

> Label flipping: by changing labels of existing real data in the training set.

Si conocemos el modelo utilizado y los datos que se utilizan para entrenarlo, se podría ir más allá, sintentizando (generando) datos que podrían optimizar el proceso de contaminación.

>  Given some knowledge about the model and its training data, an attacker can generate synthetic training data points that will optimally degrade the accuracy of the model. 

Como defensa, se pueden utilizar modelos lo más complejos posibles, que serán más resistentes y robustos frente a los ataques.

>  In general, this means that complex models (models having a high capacity) are more resilient than simple models to DoS poisoning attacks, they require more poisoning data points to be compromised, and it is difficult to decrease their accuracy as a whole.  

Muy interesante. Cada vez que hagamos un sistema automático, alguien intentará hacer que se comporte de manera diferente a la prevista.

> 
