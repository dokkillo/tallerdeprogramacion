---
layout: post
title: Introducción a los webservices
category: csharp
comments: true
description: Actualmente los webservices es uno de los componentes principales del mundo informatico actual, una de sus caracteristicas principales es que los mismos webservices pueden ser usados por una aplicación web, como una aplicación de escritorio, una web ligera (SPAs) o aplicaciones moviles, solo teniendo que hacer la parte del frontend, y no tener que rehacer el backend.
tags:
    - programacion
    - webservices 
---

Actualmente los webservices es uno de los componentes principales del mundo informatico actual, una de sus caracteristicas principales es que los mismos webservices pueden ser usados por una aplicación web, como una aplicación de escritorio, una web ligera (SPAs) o aplicaciones moviles, solo teniendo que hacer la parte del frontend, y no tener que rehacer el backend.

Según la wikipedia, un webservice o servicio web es: "es una tecnología que utiliza un conjunto de protocolos y estándares que sirven para intercambiar datos entre aplicaciones. Distintas aplicaciones de software desarrolladas en lenguajes de programación diferentes, y ejecutadas sobre cualquier plataforma, pueden utilizar los servicios web para intercambiar datos en redes de ordenadores como Internet. La interoperabilidad se consigue mediante la adopción de estándares abiertos", según esa definición tenemos varias caracteristicas de los webservices:

* Sirve para intercambiar datos entre diferentes aplicaciones.
* Da igual el lenguaje que este programado el webservice o el cliente que use el webservice, una aplicación hecha en javascript puede llamar a un webservice hecho en .NET
* Libertad de plataforma, un webservice alojado en IIS puede ser llamado tanto por una aplicación hecha para Android o una aplicación de escritorio sobre linux.

En este post sobre todo quiere hacer un inciso a las diferentes terminos y siglas que siempre veo relacionado con los webservices, y ponerlos en su contexto, más adelante, cuando el tiempo lo permita ire entrando en profundidad en cada uno.


## REST

La Transferencia de Estado Representacional (Representational State Transfer) o REST es un estilo de arquitectura software para sistemas hipermedia distribuidos como WWWW, originalmente el termino se referia a unos principios de arquitectura, pero en la actualidad se usa para un sentido más amplio y abarca cualquier interfaz que use HTTP para trabajar con datos, dando igual el formato de estos (XML, JSON etc).

Caracteristicas:

* Es un protocolo cliente - servidor sin estado, es decir, cada petición HTTP tiene toda la información necesaria para entender la petición. Aunque se suelen usar cookies o otras maneras de mantener una sesion.

* Tiene un conjunto de operaciones bien definidas, basadas en los verbos de HTTP (GET, POST, PUT, DELETE) que se pueden equiparar con las operaciones CRUD (CREATE,READ, UPDATE,DELETE)

* En REST cada recurso es solo accedible a traves su propia URI

* Uso de hipermedios, es decir, la representación de los datos se hace mediante HTML o XML por lo que es posible ir navegando entre los diferentes resultados.

## RESTFUL

Otro termino tambien bastante usado es RESTful, REST suele hacer referencia al "estilo arquitectonico" que se aprovecha de la tecnologia y los patrones para haer el webservice, mientras el termino RESTful se refiere a los webservices que usan esa arquitectura.

## RPC



## ASP.NET WEB API

## WCF

## SOA

## SOAP

## WSDL




