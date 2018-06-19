---
title: Ámbito de las variables en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 5856cdca-0ebd-4e16-8739-7bd50753b9f9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82803cd7f2b0beb8349e978fdd7b9e453dca31ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288124"
---
# <a name="variable-scope-in-orchestrations"></a>Ámbito de las variables en orquestaciones
Es necesario que comprenda algunas cuestiones importantes acerca de la visibilidad y el estado de las variables y los parámetros de las orquestaciones en varios lugares de una orquestación, incluidos los controladores de excepción y los bloques de compensación.  
  
-   Los parámetros de una orquestación se pueden ver en el cuerpo de la orquestación y en el bloque de compensación correspondiente.  
  
-   Las variables de nivel de ámbito se pueden ver en el cuerpo del ámbito, así como en todos los controlares de excepción y bloques de compensación correspondientes. Dentro de los controladores de excepción, las variables se consideran no inicializadas, ya que no se puede determinar si la excepción que provocó un controlador concreto tuvo lugar antes o después de cualquier inicialización en el cuerpo. Por este motivo, si declara una variable en un ámbito y la inicializa en el cuerpo, no podrá leerla en un controlador de excepción u obtendrá un error del compilador. Existe una solución a este error en el caso de las transacciones de larga ejecución. El siguiente ejemplo muestra cómo se puede usar el operador succeeded() para garantizar un comportamiento adecuado en tiempo de ejecución:  
  
    > [!NOTE]
    >  El código siguiente es un pseudocódigo que describe un proceso lógico; este código no se puede usar en una forma Expresión de orquestación.  
  
    ```  
    scope longrunning transaction L  
    {  
       System.Int32 i;  
       System.Int32 v;  
       body  
       {  
          i = 3;  
          scope longrunning transaction T  
          {  
             body  
             {  
                i = 5;  
             }  
          }  
       }  
       exceptions  
       {  
          catch  
          {  
             if(succeeded(T))  
             {  
                v = i;  // OK to read from it here — no compiler errors!  
             }  
          }  
       }  
    }  
    ```  
  
-   Dentro de un bloque de compensación, todas las variables asumen los valores que tenían en el momento de confirmarse el cuerpo del ámbito. Tenga en cuenta que el bloque de compensación de un ámbito nunca se ejecuta justo después de que finalice el cuerpo; siempre hay código que interviene. Si parte de ese código que interviene actualiza algunas variables de ámbito externo y, a continuación, se ejecuta el bloque de compensación, dichas actualizaciones no se verán dentro del bloque de compensación. En lugar de ello, el valor de las variables se revertirá al existente en el momento de confirmarse el ámbito que es propietario de esa compensación.  
  
-   Cuando una transacción está anidada dentro de un bucle, la transacción se compensa tantas veces como se ejecuta el bucle. Dentro del bloque de compensación, para cada iteración, las variables de ámbito externo asumirán los valores que tenían en el momento de confirmarse la iteración de la transacción.  
  
-   Cualquier actualización realizada en las variables de ámbito externo o en los parámetros de la orquestación dentro de los bloques de compensación de los ámbitos internos no se verá después de que el bloque de compensación finalice. En otras palabras, el bloque de compensación no se puede usar para modificar directamente los valores de las variables de ámbito externo.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos de XLANG-s](../core/xlang-s-data-types.md)