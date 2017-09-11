---
layout: post
title:  Usando TPL 
category: csharp
comments: true
description: La biblioteca TPL (Task Parallel Library) es una API ideal para escribir codigo multiproceso, asincróno y paralelo. 
tags:
    - programacion
---

La biblioteca TPL (Task Parallel Library) se basa en el concepto de una tarea, que representa una operación asincrónica. De cierta forma, una tarea recuerda a un subproceso pero en un nivel más alto de abstracción. El término paralelismo de tareas hace referencia a la ejecución simultánea de una o varias tareas independientes.

Las tareas proporcionan dos ventajas fundamentales:

*	Un uso más eficaz y más escalable de los recursos del sistema.

En segundo plano, las tareas se ponen en la cola del elemento ThreadPool, que se ha mejorado con algoritmos que determinan y ajustan el número de subprocesos y que ofrecen el equilibrio de carga para maximizar el rendimiento. Esto hace que las tareas resulten relativamente ligeras y que, por tanto, pueda crearse un gran número de ellas para habilitar un paralelismo pormenorizado.

*   Un mayor control mediante programación del que se puede conseguir con un subproceso o un elemento de trabajo.

Las tareas y el marco que se crea en torno a ellas proporcionan un amplio conjunto de API que admiten el uso de esperas, cancelaciones, continuaciones, control robusto de excepciones, estado detallado, programación personalizada, y más.


## Crear un Task


Cuando se crea un Task, se proporciona un delegado de usuario con la tarea que va a ejecutar. Este delegado se puede expresar con un delegado con nombre, un metododo anonommo o una expresion lambda.
Si el Task devuelve un valor se representara mediante la clase Task<TResult>.