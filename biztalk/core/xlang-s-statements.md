---
title: Instrucciones de XLANG s | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 620d0452-a8da-4285-b8b2-5a932ffcde28
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50f2ea904d134d22f08d86b1d600fdb3133a9c45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290340"
---
# <a name="xlang-s-statements"></a>Instrucciones de XLANG-s
Instrucciones de XLANG/s suelen pertenecen a una de estas dos categorías: instrucciones sencillas que actúan por sí mismas, como **recibir** o **enviar**y las instrucciones complejas que contienen o agrupan cualquier instrucciones sencillas o otras instrucciones complejas, como **ámbito**, **paralelo**, y **escuchar**. Cada instrucción se corresponde con una forma de orquestación en el Diseñador de orquestaciones de BizTalk. XLANG/s define las instrucciones siguientes:  
  
-   **grupo.** Se utiliza para agrupar operaciones en una unidad única que puede contraerse o expandirse para mayor facilidad visual.  
  
-   **Enviar.** Se utiliza para enviar un mensaje determinado a un puerto concreto.  
  
-   **recibir.** se utiliza para esperar la recepción de un mensaje determinado procedente de un puerto concreto.  
  
-   **puerto.** Define dónde y cómo se transmiten los mensajes.  
  
-   **vínculo de función.** Se utiliza para crear una colección de puertos que se comunican con el mismo socio comercial lógico, quizá mediante diferentes transportes o extremos.  
  
-   **transformar.** Se utiliza para asignar los campos de mensajes ya existentes a nuevos mensajes.  
  
-   **asignación de mensajes.** Se utiliza para enviar un mensaje determinado a un puerto concreto.  
  
-   **Construir mensaje.** define un bloque de código XLANG/s donde se crea e inicializa un mensaje. Los mensajes existentes pueden enviarse a un programa XLANG/s, pero no se pueden crear fuera de una construcción. Este mecanismo ofrece la distribución y el seguimiento de mensajes complejos porque el estado de un mensaje se conoce en todo momento.  
  
-   **orquestación de llamada.** realiza llamadas de forma sincrónica desde una orquestación a otra. Los parámetros se pueden pasar y devolver.  
  
-   **Iniciar orquestación.** Se utiliza para que su orquestación llame a otra orquestación de forma asincrónica.  
  
-   **reglas de llamada.** Permite crear una directiva de reglas de negocios para ejecutarla en la orquestación.  
  
-   **expresión.** XLANG/s es compatible con sintaxis de expresión compleja para admitir la amplia gama de escenarios de uso necesarios para la definición de protocolo. Esta instrucción se utiliza para asignar propiedades de puerto, propiedades de vínculo de servicio, mensajes, variables y objetos, así como para invocar métodos, propiedades o campos de datos estáticos.  
  
-   **decidir.** se utiliza para ejecutar de forma condicional una de las diversas rutas de ejecución, según sea el valor de sus condiciones asociadas.  
  
-   **retraso.** se utiliza para esperar hasta que se alcanza un tiempo absoluto o un tiempo relativo.  
  
-   **escuchar.** Al igual que con un **paralelo** (instrucción), el **escuchar** instrucción tiene varias rutas de ramas de ejecución. Sin embargo, la ramas deben comenzar con un **retraso** instrucción o un **recibir** instrucción. Se ejecuta la rama que recibe la primera invocación. Las demás ramas de la **escuchar** nunca se ejecuta la instrucción.  
  
-   **Acciones paralelas.** ejecuta diversas ramas de un proceso empresarial de forma simultánea. Todas las ramas deben completar el procesamiento antes de que se ejecute cualquier instrucción posterior a la instrucción parallel.  
  
-   **bucle.** se ejecuta varias veces mientras su condición asociada siga siendo true.  
  
-   **ámbito.** proporciona contexto para un bloque de código que define variables y semánticas de transacciones que se aplican a dicho bloque. El período de vida de las variables puede restringirse a dicho ámbito. La semántica de transacciones, como de larga ejecución, atómica o ninguna, puede aplicarse a un ámbito para influir en su comportamiento.  
  
-   **Iniciar excepción.** se utiliza para invocar de forma explícita un controlador de excepción o error en el bloque de código actual.  
  
-   **compensar.** se utiliza para invocar de forma explícita un bloque de compensación asociado a un ámbito determinado. A **ámbito** instrucción puede tener uno o más bloques de compensación asociados a él. El **compensar** instrucción dirige la ejecución al bloque de compensación seleccionado.  
  
-   **suspender.** detiene temporalmente la ejecución de un proceso, pero puede reiniciarlo un operador o una aplicación. Una expresión de cadena asociada con el **finalizar** instrucción debe ponerse a disposición para operadores y administradores a través de registros adecuados o una interfaz de usuario.  
  
-   **Finalizar.** detiene de forma forzosa e irrevocable todo procesamiento en una programación. Una expresión de cadena asociada con el **finalizar** instrucción debe ponerse a disposición para operadores y administradores a través de registros adecuados o una interfaz de usuario.  
  
## <a name="see-also"></a>Vea también  
 [Formas de orquestación](../core/orchestration-shapes.md)   
 [Tipos de datos de XLANG-s](../core/xlang-s-data-types.md)   
 [Operadores y Variables de XLANG-s](../core/xlang-s-variables-and-operators.md)   
 [Expresiones de XLANG-s](../core/xlang-s-expressions.md)   
 [Palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md)   
 [XLANG-s para las conversiones de tipo de BPEL4WS](../core/xlang-s-to-bpel4ws-type-conversions.md)