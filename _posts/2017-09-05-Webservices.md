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

RPC significa Remote Procedure Call o llamada a procedimiento remoto, y según la wikipedia su definición es: "es un programa que utiliza una computadora para ejecutar código en otra máquina remota sin tener que preocuparse por las comunicaciones entre ambas. El protocolo que se utiliza para esta llamada es un gran avance sobre los sockets de Internet usados hasta el momento. De esta manera el programador no tenía que estar pendiente de las comunicaciones, estando estas encapsuladas dentro de las RPC."

Tiene dos implementaciones principales, XM-RPC y SOAP, ambas usan XML para transmitir los datos.


## ASP.NET WEB API

ASP.NET WEB API es un framework de .NET que permite crear servicios web, es una plataforma ideal para crear servicios RESTFUL.

## WCF

Windows Comunication Foundation, es un framework de .NET para hacer aplicaciones orientadas a servicios. 

## SOA

Service Oriented Arquitecture o Arquitectura Orientada a Servicios, es una forma de pensar en servicios, su construccion y resultados, puedes ver más informacion en los [Principios de SOA](http://www.soa-manifesto.org/default_spanish.html)

SOA consiste en descomponer la lógica de negocio de una organización, en pequeñas unidades de funcionalidad o servicios, con esto conseguimos romper con el concepto de aplicaciones “silo”, donde se creaba una aplicación para resolver una necesidad de negocio concreta, otra para resolver otra, etc… Lo que tendremos será una plataforma transversal formada por un inventario de servicios (o varios) de forma que no solventaremos las necesidades cambiantes del negocio creando nuevas aplicaciones sino combinando diferentes servicios.

## SOAP

SOAP o Simple Object Accss Protocol, es un protocolo estándar que define cómo dos objetos en diferentes procesos pueden comunicarse por medio de intercambio de datos XML. Este protocolo deriva de un protocolo llamado XML-RPC.


## WSDL

WSDL, Web Services Description Language, describe la interfaz pública a los servicios Web. Está basado en XML y describe la forma de comunicación, es decir, los requisitos del protocolo y los formatos de los mensajes necesarios para interactuar con los servicios listados en su catálogo. Las operaciones y mensajes que soporta se describen en abstracto y se ligan después al protocolo concreto de red y al formato del mensaje.





