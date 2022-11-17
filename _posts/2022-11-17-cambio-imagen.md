---
layout: post
title: "Nueva imagen y algunas novedades"
date: "2022-11-17 15:00:00 +0000"
category: meta
tags:
- meta
imagefeature: 'https://live.staticflickr.com/65535/52395373369_11eae289c8.jpg'
---
<a href="https://flickr.com/photos/fernand0/52395373369/" title="Herramientas de carpintero "><img src="https://live.staticflickr.com/65535/52395373369_11eae289c8.jpg" alt="Herramientas de carpintero " class="img-responsive img-centered"></a>
Este sitio comenzó gracias al sistema de [Páginas de GitHub con Jekyll](https://docs.github.com/es/pages/setting-up-a-github-pages-site-with-jekyll) ([Cuarta etapa](https://fernand0.github.io/Cuarta-Etapa/).
Elegirmos en su momento [Jekyll-now](https://github.com/barryclark/jekyll-now) que nos permitía iniciar la página con comodidad. El proyecto está abandonado desde 2018 (y entonces sólo hubo pequeños cambios), así que había llegado el momento de buscar alternativas.

Hemos sido poco creativos porque descubrimos un proyecto 'heredero', [Forever Jekyll](https://github.com/forever-jekyll/forever-jekyll) que nos trae una actualización del tema-plantilla original y que podía darnos menos miedo a la hora de hacer el cambio.

El cambio lo hicimos en la página de GitHub de este sitio: [fernand0.github.io](https://github.com/fernand0/fernand0.github.io). Tal vez haya una forma más 'civilizada' de hacerlo, pero esta me funcionó sin mucha dificultad. Recomiendo haber preparado los cambios que vayamos a relizar para que el sitio esté desaparecido el menor tiempo posible:

1. Eliminamos la página vieja, cambiándole el nombre (en este momento el sitio deja de estar disponible, cuidado).
2. Hacemos un *fork* del proyecto que vamos a usar.
3. Lo descargamos en nuestro sitio: `git clone https://github.com/fernand0/fernand0.github.io.git`
4. Actualizamos las personalizaciones que podamos necesitar (mejor tenerlas ya preparadas, porque si no el sitio estará desaparecido mientras realizamos el proceso).
5. Copiar las entradas que teníamos a `_posts`.
6. Hacer `commit` de los cambios y subirlos (`git push`).
7. ¡Ya está!

¿Qué hemos ganado con el cambio?

El aspecto parece un poco más moderno, las categorías vuelven a funcionar (y copiando el código tenemos también etiquetas; en realidad las etiquetas y las categorías se tratan de la misma forma, pero son páginas diferentes).
Hay un buscador, que parece que funciona bastante bien buscando las entradas que contienen la palabras que introducimos.
También tenemos iconos sociales modernizados (utilizando *font awesome*), entradas relacionadas para cada una de ellas. 
Aparecen los botones de compartir (no sé si los dejaremos, mi experiencia es que luego la gente los usamos poco). Son botones con imágenes locales, así que no hacen de espías de nuestra navegación para las distintas redes.
Finalmente (hay más cosas, sólo señalo las que me llaman más la atención), un modo oscuro (pulsando el botoncito de abajo a la derecha).

Todavía faltan algunos ajustes y veremos si introducimos algún cambio más, pero ha sido mucho menos 'doloroso' de lo que pensábamos.
