---
layout: post
title: "Inyección de SQL basada en la evaluación de enteros en expresiones anidadas"
date: "Wed Dec 27 13:04:01 +0100 2014"
category: seguridad
tags: seguridad SQL enteros expresiones anidadas  
---

En [Exploiting Integer Based SQL Injection in Nested SQL Queries](http://blog.gdssecurity.com/labs/2013/10/8/exploiting-integer-based-sql-injection-in-nested-sql-queries.html) una demostración más de que las cosas que pueden ir mal se encuentran en cualuquier parte.

En este caso se trata de una pregunta SQL anidada que evalúa los parmámetros enteros que se le pasan como parámetro. Y también, cuando evaluamos otras cosas que el sistema de gestión de bases de datos sabe evaluar. Es un proceso bastante manual, claro, pero en los casos en los que no se hace validación de los datos puede permitir conocer cosas sobre la base de datos que no debería.
