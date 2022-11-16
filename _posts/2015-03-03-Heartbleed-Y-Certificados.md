---
layout: post
title: "Heartbleed, código y memoria"
date: "Tue Mar 03 11:55:01 +0100 2015"
category: seguridad
tags: seguridad openSSL bugs fallos código vulnerabilidades heartbleed 
---


<a href="https://500px.com/photo/80594251/el-bol%C3%ADgrafo-que-se-negaba-a-volver-de-las-vacaciones-by-fernando-tricas" title="Manos manchadas"><img src="https://drscdn.500px.org/photo/80594251/w=280_h=280/5764bd9ad1598183c6287ad8ad2975cb?v=0" width="240"  alt="Rojo"></a> 
Uno de los sucesos más llamativos de seguridad del año pasado fue [Heartbleed](http://heartbleed.com/) un fallo en la implementación de OpenSSL que permitiría a un atacante obtener información en conexiones cifradas (desde claves a contenidos). 

Aunque en [Answering the Critical Question: Can You Get Private SSL Keys Using Heartbleed?](https://blog.cloudflare.com/answering-the-critical-question-can-you-get-private-ssl-keys-using-heartbleed/) tratan de resolver esta pregunta y el mensaje es tranquilizador, lo más interesante es el análisis del código responsable del problema, los detalles de la pila y ese tipo de análisis más técnicos que nos gusta referenciar por aquí.
