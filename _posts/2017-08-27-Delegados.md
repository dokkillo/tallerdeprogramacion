---
layout: post
title: Los delegados en c#
category: csharp
comments: true
description: Un delegado es un tipo que representa referencias a métodos con unos parámetros determinados y un tipo de valor devuelto. Cuando se crea una instancia de un delegado, puede asociar su instancia a cualquier método mediante una signatura compatible. Puede invocar al método a través de la instancia del delegado.
tags:
    - programacion
    - eventos
 
---

Un delegado es un tipo que representa referencias a métodos con unos parámetros determinados y un tipo de valor devuelto. Cuando se crea una instancia de un delegado, puede asociar su instancia a cualquier método mediante una signatura compatible. Puede invocar al método a través de la instancia del delegado.

Puedes ver el [Codigo de Ejemplo](https://gist.github.com/dokkillo/572da28a6dfc0f2d2fad2c224756a404)

Es decir, si un metodo cumple la misma firma que necesita el delegado, tanto los parametros como el tipo a devolver este metodo podra ser llamado por el parametro.

Para usar un delegado, solo necesitamos usar la keyword delegate, en el siguiente codigo vemos un ejemplo de como crear un delegado.

{% highlight csharp linenos %}

 public delegate void WorkPerformedHandler(int hours, int type);

{% endhighlight %}

Por ejemplo, el metodo WorkPerformed1, entra perfectamente en la firma del delegado, es decir puede ser usado perfectamente como Handler.

{% highlight c# linenos %}

   static void WorkPerformed1(int hoursWorked, int typeWork)
    {
      Console.WriteLine("llamado metodo WorkPerformed1");
    }

{% endhighlight %}

Y para instanciar el delegado, lo haremos de esta manera:

{% highlight c# linenos %}

   WorkPerformedHandler del1 = new WorkPerformedHandler(WorkPerformed1);

{% endhighlight %}


Ahora tendriamos una funcion llamada del1, a la que podriamos pasar unos parametros, y ejecutaria el codigo del metodo WorkPerformed1.

{% highlight c# linenos %}

     del1(5, 1);

{% endhighlight %}

## ¿Y que ganamos con esto?

Podrias pensar, para que usar los delegados con esto, y no llamar directamente al metodo, muy simple, imagina que tiene que notificar un evento (una nueva entrada, un nuevo proveedor etc..) a varias partes de la aplicación. Imaginate que a los meses, hay que añadir una nueva parte en la aplicación y esta tambien tiene que recibir las notificaciones, sin los delegados, eso significaria ir parte por parte de la aplicación añadiendo un nuevo metodo a la lista de los metodos a notificar.

Ejemplo:

{% highlight c# linenos %}

  WorkPerformed1(5, 1);
  WorkPerformed2(5, 1);
  WorkPerformed3(5, 1);

{% endhighlight %}

Con los delegados, hariamos lo siguiente:

* Añadiriamos un nuevo delegado que llamaria a un nuevo metodo, recuerda que el nuevo metodo WorkPerformed2, tiene que tener la misma firma que el requiere el delegado.

{% highlight c# linenos %}
    WorkPerformedHandler del2 = new WorkPerformedHandler(WorkPerformed2);
{% endhighlight %}

* Ya que ambos delegados son del mismo tipo, añadiriamos la llamada del segundo dentro del primero, y cada vez que se llamara al del1, tambien se llamaria al del2, por lo que no haria falta buscar y tocar cada parte de la aplicación solo una.

{% highlight c# linenos %}
    del1 += del2;
{% endhighlight %}

