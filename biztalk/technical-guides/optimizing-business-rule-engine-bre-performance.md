---
title: Optimizar el rendimiento del motor (BRE) de regla de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c271b059-174d-4e8b-88b5-c3f408a97f1f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14c3adf32ac06d80c1aab8f870d82156470097a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298932"
---
# <a name="optimizing-business-rule-engine-bre-performance"></a>Optimizar el rendimiento del motor (BRE) de regla de negocios
Al implementar el motor de reglas de negocios (BRE) en una solución de BizTalk Server, deben tener en cuenta los siguientes factores:  
  
## <a name="fact-types"></a>Tipos de hechos  
 El motor de reglas tarda menos tiempo en hechos de .NET de un acceso en comparación con el tiempo que se tarda en hechos XML y la base de datos de access. Si tiene una opción de usar hechos .NET o XML o base de datos en una directiva, considere la posibilidad de usar hechos .NET para mejorar el rendimiento.  
  
## <a name="data-table-vs-data-connection"></a>Tabla de datos frente a conexión de datos  
 Cuando el tamaño del conjunto de datos es pequeño (< 10 o lo), el **TypedDataTable** enlace proporciona un mejor rendimiento que la **DataConnection** enlace. Sin embargo, el **DataConnection** enlace proporciona mejor rendimiento que la **TypedDataTable** enlace cuando el conjunto de datos es grande (mayor o igual a 10 filas aproximadamente). Por lo tanto, debe decidir si desea utilizar el **DataConnection** enlace o **TypedDataTable** enlace en función del tamaño estimado del conjunto de datos.  
  
## <a name="fact-retrievers"></a>Almacenes de datos  
 Un administrador de almacenes implementa métodos estándar que se usan normalmente para proporcionar los hechos a largo plazo y que cambian lentamente al motor de reglas antes de ejecutar una directiva. El motor almacena estos datos en caché y los utiliza en varios ciclos de ejecución. En lugar de enviar un hecho estático o relativamente estático cada vez que se invoca el motor de reglas, debe crear un administrador de almacenes que envíe el hecho por primera vez y, a continuación, actualiza los hechos en memoria solo cuando sea necesario.  
  
## <a name="rule-priority"></a>Prioridad de la regla  
 El valor de prioridad de una regla puede oscilar a ambos lados de **0**, con los números más grandes significan una mayor prioridad. Las acciones se ejecutan en orden de prioridad más alta a prioridad más baja. Cuando la directiva implementa un comportamiento de encadenamiento directo mediante el uso de **Assert/Update** llamadas, el encadenamiento se pueden optimizar mediante el uso de la configuración de prioridad. Por ejemplo, supongamos que **Rule2** tiene una dependencia en un valor establecido por **Rule1**. Dando **Rule1** una prioridad más alta significa que **Rule2** sólo se ejecutarán después de **Regla1** se activa y actualiza el valor. Por el contrario, si **Rule2** estaban tiene una prioridad más alta, podría activarse una vez y, a continuación, se activan después de volver a **Rule1** se activa y actualice el hecho de que **Rule2** está usando una condición. Aunque esto puede proporcionar un resultado correcto, lo que proporciona **Rule1** una prioridad más alta en este escenario le proporcionará un mejor rendimiento.  
  
## <a name="update-calls"></a>Llamadas de actualización  
 La función de actualización hace que todas las reglas mediante los hechos actualizados para volver a evaluar. Llamadas a funciones de actualización pueden resultar costosas, especialmente si se vuelve a evaluar en un gran conjunto de reglas al actualizar los hechos. Hay situaciones en las que se puede evitar este comportamiento. Por ejemplo, considere las siguientes reglas.  
  
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
  
 El resto de reglas de la directiva, utilice **StatusObj.Flag** en sus condiciones. Por lo tanto, cuando **actualización** se llama en el **StatusObj** de objeto, se volverá a evaluar todas las reglas. Independientemente del valor de la **cantidad** campo es, todas las reglas excepto **Rule1** o **Rule2** se evalúan dos veces, una vez antes de la **actualización** llamar a y una vez después de la **actualización** llamar.  
  
 Para mitigar asociado sobrecarga, podría establecer el valor de la **marca** campo **false** antes de invocar la directiva y, a continuación, use solo **Rule1** en la directiva para establecer la marca . En este caso, **actualización** se denominaría sólo si el valor de la **cantidad** campo es mayor que 5 y el **actualización** función no se invoca si el valor de  **Cantidad** es menor o igual que 5. Por lo tanto, todas las reglas excepto **Rule1** o **Rule2** se evalúan dos veces solo si el valor de la **cantidad** campo es mayor que 5.  
  
## <a name="usage-of-logical-or-operators"></a>Uso de operadores lógicos o  
 El uso de un número cada vez mayor de operadores lógicos O en las condiciones crea permutaciones adicionales que expanden la red de análisis del motor de reglas. Desde el punto de vista del rendimiento, será mejor dividir las condiciones en reglas atómicas que no contengan operadores lógicos O .  
  
## <a name="caching-settings"></a>Configuración de almacenamiento en caché  
 El motor de reglas usa dos cachés. La primera de ellas es utilizada por el servicio de actualización y la otra se usa por cada proceso de BizTalk. La primera vez que se usa una directiva, el proceso de BizTalk solicita la información de directiva desde el servicio de actualización. El servicio de actualización recupera la información de directiva de la base de datos de motor de reglas, lo almacena en caché y devuelve la información para el proceso de BizTalk. El proceso de BizTalk crea un objeto de directiva basado en esa información y almacena el objeto de directiva en una memoria caché cuando la instancia de motor de reglas asociado completa la ejecución de la directiva. Cuando se vuelve a invocar la misma directiva, el proceso de BizTalk vuelve a utilizar el objeto de directiva de la memoria caché si está disponible. De forma similar, si el proceso de BizTalk solicita información acerca de una directiva de servicio de actualización, el servicio de actualización busca la información de directiva en su caché si está disponible. Cada 60 segundos, el servicio de actualización también comprueba si se han producido las actualizaciones de la directiva en la base de datos. Si hay actualizaciones, el servicio de actualización recupera la información y almacena en caché la información actualizada.  
  
 Hay tres parámetros de ajuste del motor de reglas relacionadas con estas cachés: **CacheEntries**, **Tiempodeesperadecaché**, y **PollingInterval**. Se pueden especificar los valores de estos parámetros tanto en el Registro como en un archivo de configuración. El valor de la **CacheEntries** parámetro es el número máximo de entradas en la caché y se establece en un valor de 32 de forma predeterminada. Puede que desee aumentar el valor de la **CacheEntries** parámetro para mejorar el rendimiento en ciertos escenarios. Por ejemplo, suponga que está usando 40 directivas repetidamente; se puede realizar para aumentar el valor de la **CacheEntries** parámetro hasta 40 para mejorar el rendimiento. Esto permitiría que el servicio de actualización mantener los detalles de la memoria caché de hasta 40 directivas en la memoria.  
  
 El valor de **CacheTimeout** es el tiempo en segundos que se mantiene una entrada en la caché del servicio de actualización. En otras palabras, el **CacheTimeout** valor hace referencia a cuánto tiempo una entrada de caché para una directiva se mantiene en la memoria caché sin que se hace referencia. El valor predeterminado de **CacheTimeout** parámetro es 3600 segundos, o 1 hora. Significa que si la entrada de caché no se hace referencia en una hora, se elimina la entrada. En algunos casos, puede ser beneficioso aumentar el valor de la **CacheTimeout** parámetro para mejorar el rendimiento. Por ejemplo, si una directiva se invoca cada dos horas, de la ejecución de la directiva se puede mejorar el rendimiento aumentando el **CacheTimeout** parámetro con un valor superior a dos horas.  
  
 El **PollingInterval** parámetro del motor de reglas define el tiempo en segundos para el servicio de actualización para comprobar la base de datos de motor de reglas para las actualizaciones. El valor predeterminado para la **PollingInterval** parámetro es de 60 segundos. Si sabe que las directivas no se actualizan en absoluto o se actualizan con poca frecuencia, puede cambiar este parámetro en un valor mayor para mejorar el rendimiento.  
  
## <a name="sideeffects-property"></a>Propiedad SideEffects  
 El **ClassMemberBinding**, **DatabaseColumnBinding**, y **XmlDocumentFieldBinding** las clases tienen una propiedad denominada **SideEffects**. Esta propiedad determina si el valor del campo, de la columna o del miembro enlazados se ha almacenado en caché. El valor predeterminado de la **SideEffects** propiedad en el **DatabaseColumnBinding** y **XmlDocumentFieldBinding** las clases es **false**. El valor predeterminado de la **SideEffects** propiedad en el **ClassMemberBinding** clase es **true**. Por lo tanto, cuando se obtiene acceso por segunda vez (o más tarde dentro de la directiva) a un campo de un documento XML o a una columna de una tabla de una base de datos, su valor se recupera desde la caché. Sin embargo, cuando se obtiene acceso por segunda vez (o posteriormente) a un miembro de un objeto .NET, el valor se recupera desde el objeto .NET y no desde la caché. Establecer el **SideEffects** propiedad de .NET **ClassMemberBinding** a **false** mejorará el rendimiento porque el valor del campo se recupera de la caché desde el segunda vez. Tan solo se puede hacer esto mediante programación. La herramienta de Compositor de reglas de negocio no expone el **SideEffects** propiedad.  
  
## <a name="instances-and-selectivity"></a>Instances y selectivity  
 El **clases XmlDocumentBinding**, **ClassBinding**, y **DatabaseBinding** tienen dos propiedades: **instancias** y **Selectividad**. El valor de Instances corresponde al número esperado de instancias de la clase en la memoria de trabajo. El valor de **selectividad** es el porcentaje de las instancias de clase que satisfarán las condiciones de regla. El motor de reglas usa estos valores para optimizar la evaluación de condiciones de modo que se utilice primero el menor número de instancias posible en las evaluaciones de condiciones y posteriormente se usen las instancias restantes. Si tiene un conocimiento previo del número de instancias del objeto, al establecer el **instancias** ese valor para propiedad mejoraría el rendimiento. De forma similar, si tiene un conocimiento previo del porcentaje de los objetos que satisfacen las condiciones, al establecer el **selectividad** ese valor para propiedad mejoraría el rendimiento. Tan solo se pueden establecer los valores de estos parámetros mediante programación. La herramienta Compositor de reglas de negocio no los expone.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento de BizTalk Server](../technical-guides/optimizing-biztalk-server-performance.md)