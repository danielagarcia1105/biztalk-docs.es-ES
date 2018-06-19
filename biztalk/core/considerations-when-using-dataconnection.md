---
title: Consideraciones al utilizar DataConnection | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Business Rules Engine, DataConnection tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], DataConnection
ms.assetid: 1b4c8aa5-053f-43d7-9f5f-050383405fed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f99110daafa74cb16b6cc5b98e1382049bbb158
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22238956"
---
# <a name="considerations-when-using-dataconnection"></a>Consideraciones al utilizar DataConnection
Considere lo siguiente al utilizar DataConnection con el motor de reglas de negocios.  
  
## <a name="use-primary-keys"></a>Utilice claves principales  
 Cuando hay una clave principal, la igualdad de dos filas se determina considerando si las filas tienen la misma clave principal en vez de comparando objetos. Si se determina que las filas son iguales, solo se conserva una copia en la memoria y la otra se descarta. Esto supone una menor utilización de la memoria.  
  
 Cuando un **DataConnection** se impone en el motor de reglas por primera vez, el motor siempre intenta localizar su información de clave principal de su esquema. Si existe una clave principal, se recupera la información y se utiliza en todas las evaluaciones posteriores.  
  
> [!NOTE]
>  Es obligatoria una clave principal si hay que hacer cambios en la base de datos.  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a>Proporcione una transacción de ejecución a la DataConnection siempre que sea posible  
 Sin una transacción, cada uno de ellos consultar y actualizar en el **DataConnection** inicia su propia transacción local y diferentes consultas podrían devolver diferentes resultados en diferentes partes de las evaluaciones de reglas. Los usuarios pueden experimentar un comportamiento incoherente si hay cambios en la tabla de la base de datos subyacente.  
  
 Aunque puede usar un **DataConnection** sin proporcionar ninguna transacción cuando la tabla no cambia con el tiempo, se recomienda utilizar una transacción incluso si la **DataConnection** solo se va a se utiliza para operaciones de lectura.  
  
 Sin embargo, siempre se debe utilizar una transacción cuando actualice datos.  
  
## <a name="number-of-queries-may-grow-linearly"></a>El número de consultas se puede incrementar linealmente  
 Al igual que las consultas en el **DataConnection** parametrizadas por otros objetos combinados, el número de consultas ejecutadas en la **DataConnection** se corresponde directamente con el número de objetos combinados alcanzar la **DataConnection**. Por lo tanto, si el número de combinar objetos alcanzar la **DataConnection** objeto incrementa linealmente, el número de consultas en el **DataConnection** aumentará linealmente así. Actualmente, no existe ninguna optimización para reducir el número de consultas.  
  
 Un ejemplo es la regla:  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 A representa un **ObjectBinding**, DC representa una **DataConnection**y x e y representan atributos de A y DC.  
  
 Para cada instancia de un que pasa la prueba (x = 7), se genera una consulta mediante el uso de la **DataConnection**. Si existen muchas instancias coincidentes, se producirán el mismo número de consultas.  
  
## <a name="use-or-conditions-with-caution"></a>Utilice las condiciones OR con precaución  
 Si la regla utiliza solo conjuntivas (**AND**) condiciones, las pruebas y las consultas se ejecutarán tan pronto como sea posible, por lo que se reducirá instancias de objetos que se pasan a través. Como resultado, el número de consultas en la subsiguiente **DataConnection** se reducirá proporcionalmente. Si disyuntiva (**o**) condiciones y una **DataConnection** se utilizan conjuntamente en una regla, condición todas las evaluaciones se insertará en la consulta final. Si más de un **DataConnection** se utiliza en una regla, todas las consultas excepto la última de ellas se convierte en una instrucción de consulta Select-ALL.  
  
 En general, es mejor dividir cualquier regla con una condición OR en dos o más reglas discretas, porque la utilización de condiciones OR disminuirá rendimiento si se compara con la definición de más reglas atómicas. Esto es así independientemente de que se utilicen DataConnections o no.  
  
 También puede considerar la utilización de reglas separadas que consten solo de condiciones conjuntivas en vez de una regla con **o** condiciones. Con **o** condiciones, el número de consultas aumenta la velocidad de multiplicación de las instancias de todos los objetos combinados. Esto se muestra en el ejemplo siguiente.  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 En este ejemplo, se representa A un **ObjectBinding**; DC representa una **DataConnection**y x, y y z representan atributos de A y DC. Si A tiene 100 instancias y x es 1 en el primer objeto, 2 en el segundo objeto, hasta 100 en el objeto 100, 100 consultas tienen que ejecutar en el **DataConnection**.  
  
 Es mejor volver a escribir la regla anterior dividiéndola en dos reglas.  
  
 **Regla 1**  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 **Regla 2**  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a>SQL no admite algunos predicados y funciones  
 SQL no admite algunos predicados y funciones que admite el motor de reglas. Si estos predicados y funciones no admitidos se utilizan en las condiciones de la regla, no se pueden incorporar a la consulta. Los términos siguientes no se pueden optimizar como una consulta SQL:  
  
-   Algunas de las funciones integradas del motor no tienen equivalente en una consulta SQL. Se trata de **Power**, **FindFirst**, y **Encontrartodos**. Con un **DataConnection** columna como uno o más de sus argumentos no se puede optimizar como parte de una consulta; por ejemplo, potencia (2, controlador de dominio. Column1).  
  
-   Predicado integrado coincidencia que utiliza un **DataConnection** columna como su argumento de expresión regular (primer argumento). Por ejemplo, Coincidencia("abc*", dc1.Column2) es válido, pero Coincidencia(dc1.Column1, dc1.Column2) no se puede traducir.  
  
-   Con una función de usuario que tiene un **DataConnection** columna como uno de sus parámetros. Por ejemplo, c1.M(dc.Column1) no se puede optimizar porque la función de usuario no se puede ejecutar en el servidor de base de datos, sino que debe ejecutarlo el motor de reglas de negocios.  
  
-   Funciones de usuario que representan las operaciones set en el **DataConnection**; por ejemplo, controlador de dominio. Column1(5).  
  
-   Funciones que utilizan un **ObjectReference** a la **DataConnection**; por ejemplo, objecref (DC).  
  
-   Si no es posible traducir uno o más argumentos de una función, la llamada a la función se convierte en intraducible; por ejemplo, Agregar(c1.M(dc.Column1), 5 ).  
  
## <a name="see-also"></a>Vea también  
 [Acceso a datos en el motor de reglas de negocio](../core/data-access-in-the-business-rule-engine.md)