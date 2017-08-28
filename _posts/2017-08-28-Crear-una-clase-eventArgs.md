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
        public int Hours { get; set; }
        public int Type { get; set; }
    }

```



