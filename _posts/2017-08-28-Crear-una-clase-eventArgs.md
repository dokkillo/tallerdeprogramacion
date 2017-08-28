---
layout: post
title: Crear una clase EventArgs
category: csharp
comments: true
description: La clase EventArgs es usada como firma de muchos delegados y event handlers, muchas veces podemos tener delegados que necesitan una gran cantidad de parametros y en estos casos puede ser muy interesante extender la clase EventArgs. En este articulo explicaremos como hacerlo.
tags:
    - programacion
    - eventos
 
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

Puedes ver el codigo entero en:

<script src="https://gist.github.com/dokkillo/1f6962e95b62afdcea65f95f9a48dcd5.js"></script>




