---
layout: post
title:  Usando Parameter binding en ASP.NET Web API
category: csharp
comments: true
description: Cuando una web api llama a un metodo de un controller, se deben asignar unos valores a los parametros, este proceso se conoce como bindding. Por defecto Web api trata a los parametros de dos maneras, segun el tipo de parametro, sean simples o complejos.
tags:
    - webservices
---

Cuando una web api llama a un metodo de un controller, se deben asignar unos valores a los parametros, este proceso se conoce como bindding. Por defecto Web api trata a los parametros de dos maneras, segun el tipo de parametro, sean simples o complejos.

* Simple:

Si el parametro es de tipo simple (int, bool, double, timestamp,datetime, guid, decimal, string ), web api coge el valor desde la URI.

* Complejo: 

Para los parametros de tipo complejo, como puede ser una clase creada por nosotros, Web API lee los valores desde el body, usando media-type formatters (como por ejemplo [FromBody] o [FromUri])



## FromUri

El atributo [FromUri] se le añade al parametro del metodo del Controller, sirve para decirle a la aplicación que debe coger el valor desde la URI.

Por ejemplo, si tenemos una clase que sea cordenadas, donde hay dos propiedades, latitud y longitud.


``` csharp
public class Cordenadas
{
    public double Latitud { get; set; } 
    public double Longitud { get; set; }
}

public ValuesController : ApiController
{
    public HttpResponseMessage Get([FromUri] Cordenadas posicion) { ... }
}

```

Web Api espera que pasemos las cordenadas por URI, asi que le pasamos la longitud y latitud, y el Controller ya recibira el objeto Cordenadas.

http://localhost/api/values/?Latitud=32.3232&Longitud=14.5


Hay otro atributo llamado [FromRoute] que es basante parecido a [FromUri] 

## FromBody

Al añadir el atributo [FromBody] al parametro del metodo del controller, se fuerza a Web Api que coja el valor del request body.

``` csharp

public HttpResponseMessage Post([FromBody] string name) { ... }

```

La petición a web api deberia ser algo asi:

``` csharp

POST http://localhost:5076/api/values HTTP/1.1
User-Agent: Fiddler
Host: localhost:5076
Content-Type: application/json
Content-Length: 7
"Alice"

``` 

Lo que no es posible es que dos parametros del mismo metodo vayan con [FromBody], ya que el request body solo puede leerse una vez.





