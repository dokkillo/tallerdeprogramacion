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

```csharp
     public void button_Click(object sender, EventArgs e)
     {
         //codigo ejemplo
     }
```

