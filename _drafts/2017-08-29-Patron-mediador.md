---
layout: post
title: Patrón de diseño mediador
category: csharp
comments: true
description: El patrón de diseño mediador define un objeto que encapsula como un conjunto de objetos interactuan, se le considera un patrón de comportamiento, ya que puede alterar el comportamiento del programa en ejecución.
Con este patrón, la comunicación entre objetos es encapsulada por un objeto mediador, es decir los objetos no se comunican entre ellos, sino que se comunican mediante el mediador.
tags:
    - programacion
    - patrones
 
---

El patrón de diseño mediador define un objeto que encapsula como un conjunto de objetos interactuan, se le considera un patrón de comportamiento, ya que puede alterar el comportamiento del programa en ejecución.
Con este patrón, la comunicación entre objetos es encapsulada por un objeto mediador, es decir los objetos no se comunican entre ellos, sino que se comunican mediante el mediador.

## Cuando usar el patrón de diseño mediador

El patrón de diseño mediador, es ideal pensar en usarlo cuando se cumplen estas opciones:

* Cuando hay una gran cantidad de objetos del mismo tipo que necesitan comunicar entre ellos.

* Cuando la comunicacion entre los objetos es muy compleja.



 


``` csharp

    worker.WorkCompleted += new EventHandler(worker_workCompletedEmail);

    private static void worker_workCompletedEmail(object sender, EventArgs e)
    {
         Console.WriteLine("Enviar Email notificando el proceso ha finalizado");
    }
      

```


