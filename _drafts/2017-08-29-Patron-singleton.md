---
layout: post
title: Patrón de diseño singleton
category: csharp
comments: true
description: La clase EventArgs es usada como firma de muchos delegados y event handlers, muchas veces podemos tener delegados que necesitan una gran cantidad de parametros y en estos casos puede ser muy interesante extender la clase EventArgs. En este articulo explicaremos como hacerlo.
tags:
    - programacion
    - patrones
 
---

La clase EventArgs es usada como firma de muchos delegados y event handlers, muchas veces podemos tener delegados que necesitan una gran cantidad de parametros y en estos casos puede ser muy interesante extender la clase EventArgs. En este articulo explicaremos como hacerlo.

La clase EventArgs, la usamos con frecuencia, por ejemplo en toda la parte de UI, y gracias a ella podemos encapsular todas las diferentes opciones que pasan los diferentes componentes de la capa UI sin "ensuciar" los metodos con decenas de parametros.

``` csharp

     public void button_Click(object sender, EventArgs e)
     {
         //codigo ejemplo
     }

```

Para crear una clase custom de EventArgs, lo principal es que nuestra clase tiene que heredar de System.EventArgs. Siguiendo los ejemplos anteriores, nuestra clase custom de EventArgs se quedaria asi:

``` csharp

    public class WorkPerformedEventArgs :System.EventArgs
    {
        public WorkPerformedEventArgs(int hours, int type)
        {
            Hours = hours;
            Type = type;
        }

        public int Hours { get; set; }
        public int Type { get; set; }
    }

```

Asi que volveremos a la clase work.cs que hemos estado trabajando en anteriores articulos, vamos a modificar la clase para asi añadir la clase custom de EventArgs que hemos creado. 

Nuesto antiguo delegado, pasa de:

``` csharp

       public delegate int WorkPerformedHandler(int hours, int type);

```
a

``` csharp

    public delegate int WorkPerformedHandler(object sender, WorkPerformedEventArgs e);


```

Una de las mejoras principales, es que si en un futuro, tenemos que añadir una propiedad más al evento, solo cambiando la clase WorkPerformedEventArgs ya estaria, no haria falta tocar el resto del codigo.

Ahora lo que nos faltaria seria, tocar la clase program.cs para que pudieramos ejecutar el codigo del evento que hemos estado creando, lo primero de todo, en la clase program.cs de nuestra aplicación de consola, creariamos dos nuevos metodos para que cada vez que nuestros eventos fuesen llamados, se ejecutaran para ello deben tener la misma firma que nuestros eventos.

Para nuestro evento WorkPerformed, creariamos este metodo:

``` csharp

     private static int worker_workPerformed(object sender, WorkPerformedEventArgs e)
     {
            Console.WriteLine(e.Hours + " " + e.Type);
            return e.Hours - 1 ;
     }

```
Mientras que para nuestro evento WorkCompleted, usariamos este:

``` csharp

      private static void worker_workCompleted(object sender, EventArgs e)
        {
            Console.WriteLine("proceso finalizado");
        }

```

Ahora ya solo nos faltaria decirle al programa que enlace los eventos con estos metodos, el metodo es parecido al que hicimos con los delegados:

``` csharp

      worker.WorkPerformed += new Eventos.WorkPerformedHandler(worker_workPerformed);
      worker.WorkCompleted += new EventHandler(worker_workCompleted);

```

Y el ultimo paso, ejecutar el metodo DoWork, de nuestra clase Worker, que se ocupara de lanzar los eventos que estan asociados a los metodos que le hemos referenciado.

``` csharp

    worker.DoWork(5, 1);
      
```


## Asociar más metodos a un solo Evento

Como todo codigo de software, nunca es estatico, siempre habra nuevos requerimientos, y habra que añadir nuevas funcionalidades, imaginate que necesitamos que cuando el proceso haya finalizado, se envie un email diciendonos que el proceso ha acabado, con los eventos, esto es bastante facil, solo hace falta asociar un metodo que envie un email, a nuestro evento WorkCompleted.

``` csharp

    worker.WorkCompleted += new EventHandler(worker_workCompletedEmail);

    private static void worker_workCompletedEmail(object sender, EventArgs e)
    {
         Console.WriteLine("Enviar Email notificando el proceso ha finalizado");
    }
      

```



Puedes ver el codigo entero en:

<script src="https://gist.github.com/dokkillo/1f6962e95b62afdcea65f95f9a48dcd5.js"></script>




