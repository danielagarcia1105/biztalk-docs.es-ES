---
title: Consideraciones sobre el rendimiento cuando se usa el motor de reglas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e9020c2-5152-40f6-940b-d4ce4081f069
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24a1c6ffb278d257e16c192e5fc7d827df70e24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266508"
---
# <a name="performance-considerations-when-using-the-rule-engine"></a>Consideraciones de rendimiento al usar el motor de reglas
Este tema trata sobre el rendimiento del motor de reglas en varios escenarios y con diferentes valores en los parámetros de configuración o ajuste.  
  
## <a name="fact-types"></a>Tipos de hechos  
 El motor de reglas tarda menos en obtener acceso a los hechos .NET que a los hechos XML y de base de datos. Si puede elegir entre usar hechos .NET, XML o de base de datos en una directiva, debería optar más bien por usar hechos .NET para obtener un mejor rendimiento.  
  
## <a name="data-table-vs-data-connection-binding"></a>Vs de tabla de datos. Enlace de conexión de datos  
 Cuando el tamaño del conjunto de datos es pequeño (inferior a unas 10 filas), el **TypedDataTable** enlace proporciona mejor rendimiento que la **DataConnection** enlace. Cuando el conjunto de datos es grande (mayor o igual a aproximadamente 10 filas), el **DataConnection** enlace proporciona mejor rendimiento que la **TypedDataTable** enlace. Por lo tanto, debe decidir si desea utilizar el **DataConnection** enlace o la **TypedDataTable** enlace en función del tamaño estimado del conjunto de datos.  
  
## <a name="fact-retrievers"></a>Administradores de almacenes de datos  
 Puede escribir un administrador de almacenes: un objeto que implementa métodos estándares y los utiliza para la fuente de alimentación a largo plazo y que cambian lentamente al motor de reglas antes de ejecutar la directiva. El motor almacena estos datos en caché y los utiliza en varios ciclos de ejecución. En lugar de enviar un hecho estático o casi estático cada vez que invoque el motor de reglas, debería crear un administrador de almacenes de datos que envíe el hecho la primera vez y, a continuación, lo actualice en la memoria solo cuando se necesite.  
  
## <a name="rule-priority"></a>Prioridad de la regla  
 El valor de prioridad de una regla puede oscilar a ambos lados de **0**, con los números más grandes significan una mayor prioridad. Las acciones se ejecutan en orden desde prioridad más alta a prioridad más baja. Cuando la directiva implementa un comportamiento de encadenamiento directo mediante el uso de **Assert/Update** llamadas, el encadenamiento se pueden optimizar mediante el uso de la configuración de prioridad. Por ejemplo, suponga que **Rule2** tiene una dependencia en un valor que se establece de forma **Rule1**. Dando **Rule1** una prioridad más alta significa que **Rule2** solo se ejecutará después **Rule1** se activa y actualiza el valor. Por el contrario, si **Rule2** es tiene una prioridad más alta, se puede desencadenar una vez y, a continuación, se activan después de volver a **Rule1** se activa y actualiza el hecho de que **Rule2** está usando en una condición. Esto puede producir resultados correctos o no, pero está claro que una doble activación repercute más sobre el rendimiento que una sola.  
  
## <a name="update-calls"></a>Llamadas a Update  
 El **actualización** función actualiza un hecho de que existe en la memoria de trabajo del motor de reglas y hace que todas las reglas que usan el hecho actualizado en condiciones para volver a evaluar. **Actualización** llamadas a funciones pueden ser costosas, especialmente si muchas reglas necesitan volver a evaluar debido a actualizaciones de hechos. Hay situaciones en las que es posible evitar que vuelvan a evaluarse las reglas. Por ejemplo, imagine las siguientes reglas:  
  
 **Rule1:**  
  
```  
IF PurchaseOrder.Amount > 5   
THEN StatusObj.Flag = true; Update(StatusObj)  
```  
  
 **Rule2:**  
  
```  
IF PurchaseOrder.Amount <= 5   
THEN StatusObj.Flag = false; Update(StatusObj)  
```  
  
 El resto de reglas de la directiva, utilice **StatusObj.Flag** en sus condiciones. Por lo tanto, cuando **actualización** se llama en el **StatusObj** de objeto, se volverá a evaluar todas las reglas. Independientemente del valor de la **cantidad** campo es, todas las reglas excepto **Rule1** y **Rule2** se evalúan dos veces, una vez antes de la **actualización** llamada y una vez después de la **actualización** llamar.  
  
 En su lugar, puede establecer el valor de la **marca** campo **false** antes de invocar la directiva y, a continuación, usar solo **Rule1** en la directiva para establecer la marca. En este caso, **actualización** sólo se llama si el valor de la **cantidad** campo es mayor que 5, y **actualización** no se llama si la cantidad es menor o igual a 5. Por lo tanto, todas las reglas excepto **Rule1** y **Rule2** se evalúan dos veces solo si el valor de la **cantidad** campo es mayor que 5.  
  
## <a name="use-of-logical-or-operators"></a>Uso de operadores O lógicos  
 El motor de reglas está optimizado para ejecutar lógica **AND** operadores y reconstruye la regla que analizó en una forma disyuntiva normal hasta que **o** operador se usa solo en el nivel superior. Con un número creciente de lógica **o** operadores en las condiciones crea más permutaciones que expanden la red de análisis del motor de reglas, y puede tardar mucho tiempo para el motor de reglas normalizar la regla. La lista siguiente contiene posibles soluciones para este problema.  
  
-   Modifique la regla para que sea la forma disyuntiva normal por lo que la **o** operador es sólo en el nivel superior. Tenga en cuenta que desarrollar una regla en forma disyuntiva normal en el Compositor de reglas de negocio puede ser complicado. Quizás desee considerar la posibilidad de crear la regla mediante programación.  
  
-   Desarrollar un componente de aplicación auxiliar que realiza la **o** las operaciones y devuelve un valor booleano y use el componente en la regla.  
  
-   Considere la posibilidad de dividir la regla en varias y que una regla ejecutada previamente compruebe un conjunto de marcas o bien usar un objeto impuesto por una regla ejecutada previamente, tal como se muestra en los ejemplos siguientes:  
  
    -   Regla 1: IF (un == 1 o == 3), a continuación, b = true  
  
         Regla 2: si (b == true), a continuación...  
  
    -   Regla 1: IF (un == 1 o == 3), a continuación, assert (nueva c())  
  
         Regla 2: IF (c.flag == true), a continuación...  
  
## <a name="caching-settings"></a>Configuración de almacenamiento en caché  
 El motor de reglas usa dos cachés. La primera se encuentra en el servicio de actualización y la segunda en cada uno de los procesos de BizTalk. La primera vez que se usa una directiva, el proceso de BizTalk solicita la información de la directiva al servicio de actualización. El servicio de actualización recupera la información de la directiva desde la base de datos del motor de reglas, la almacena en caché y devuelve la información al proceso de BizTalk. El proceso de BizTalk crea un objeto de directiva basado en esa información y lo almacena en una caché cuando la instancia del motor de reglas completa la ejecución de la directiva. Cuando se vuelve a invocar la misma directiva, el proceso de BizTalk usa nuevamente el objeto de la directiva desde la caché si hay alguno disponible.  
  
 De igual modo, si el proceso de BizTalk solicita la información acerca de una directiva al servicio de actualización, éste busca en primer lugar la información de la directiva en su caché. El servicio de actualización también comprueba cada 60 segundos si ha habido actualizaciones de la directiva que está en la base de datos. Si hay actualizaciones, el servicio de actualización recupera la información y almacena en caché la información actualizada.  
  
 Hay tres parámetros de ajuste del motor de reglas relacionadas con estas cachés: **CacheEntries**, **Tiempodeesperadecaché**, y **PollingInterval**. Se pueden especificar los valores de estos parámetros tanto en el Registro como en un archivo de configuración.  
  
 El valor de **CacheEntries** es el número máximo de entradas en la memoria caché. El valor predeterminado de **CacheEntries** es 32. Puede que desee aumentar el valor de la **CacheEntries** parámetro para mejorar el rendimiento en algunos casos. Por ejemplo, imagine que está usando 40 directivas de forma repetida. En este caso puede que desee aumentar el valor de **CacheEntries** hasta 40 para mejorar el rendimiento. Con ello permitirá al servicio de actualización almacenar los detalles de hasta 40 directivas en la memoria caché. Y también hará que el servicio de BizTalk almacene hasta 40 instancias de directiva en la memoria caché. Puede haber más de una instancia de una directiva en la caché del servicio de BizTalk.  
  
 El valor de **CacheTimeout** es el tiempo (en segundos) para que deje la memoria caché de servicio de actualización las entradas. En otras palabras, el **CacheTimeout** valor hace referencia a cuánto tiempo una entrada de caché para una directiva se conserva en la memoria caché si no hay ninguna referencia a ella. El valor predeterminado de **CacheTimeout** es 3600 segundos (una hora). Esto quiere decir que, si no se hace referencia a la entrada de caché en el transcurso de una hora, se borrará. En algunos casos, puede que desee aumentar el **CacheTimeout** valor para mejorar el rendimiento. Por ejemplo, suponga que se invoca la directiva cada dos horas. Para mejorar el rendimiento de la ejecución de la directiva, aumentar el valor de la **CacheTimeout** parámetro con un valor superior a dos horas.  
  
 El **PollingInterval** parámetro para el motor de reglas define el tiempo en segundos para el intervalo en el que el servicio de actualización comprueba si la base de datos de motor de reglas para las actualizaciones. El valor predeterminado para la **PollingInterval** parámetro es de 60 segundos (un minuto). Si sabe que las directivas no se actualizan o lo hacen con poca frecuencia, puede incrementar este valor para mejorar el rendimiento.  
  
## <a name="sideeffects-property"></a>SideEffects (propiedad)  
 El **ClassMemberBinding**, **DatabaseColumnBinding**, y **XmlDocumentFieldBinding** las clases tienen una propiedad denominada **SideEffects**. Esta propiedad determina si el valor del campo, de la columna o del miembro enlazados se ha almacenado en caché. El valor predeterminado de la **SideEffects** propiedad en el **DatabaseColumnBinding** y **XmlDocumentFieldBinding** las clases es **false**. El valor predeterminado de la **SideEffects** propiedad en el **ClassMemberBinding** clase es **true**. Por lo tanto, cuando se obtiene acceso por segunda vez (o más tarde dentro de la directiva) a un campo de un documento XML o a una columna de una tabla de una base de datos, su valor se recupera desde la caché. Sin embargo, cuando se obtiene acceso por segunda vez (o posteriormente) a un miembro de un objeto .NET, el valor se recupera desde el objeto .NET y no desde la caché. Establecer el **SideEffects** propiedad de .NET **ClassMemberBinding** a **false** mejorará el rendimiento porque el valor del campo se recupera de la caché desde el segunda vez. Tan solo se puede hacer esto mediante programación. La herramienta de Compositor de reglas de negocio no expone el **SideEffects** propiedad.  
  
## <a name="instances-and-selectivity"></a>Instances y Selectivity  
 El **clases XmlDocumentBinding**, **ClassBinding**, y **DatabaseBinding** tienen dos propiedades: **instancias** y **Selectividad**. El valor de **instancias** es el número esperado de instancias de la clase en la memoria de trabajo. El valor de **selectividad** es el porcentaje de las instancias de clase que satisfarán las condiciones de regla. El motor de reglas usa estos valores para optimizar la evaluación de condiciones de modo que se utilice primero el menor número de instancias posible en las evaluaciones de condiciones y posteriormente se usen las instancias restantes. Si tiene un conocimiento previo del número de instancias del objeto, al establecer el **instancias** ese valor para propiedad mejoraría el rendimiento. De forma similar, si tiene un conocimiento previo del porcentaje de los objetos que satisfacen las condiciones, al establecer el **selectividad** ese valor para propiedad mejoraría el rendimiento. Tan solo se pueden establecer los valores de estos parámetros mediante programación. La herramienta Compositor de reglas de negocio no los expone.