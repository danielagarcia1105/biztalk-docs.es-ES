---
title: "Búsquedas de actividad en el Portal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], searching
- queries [BAM], field descriptions
- Query Builder [BAM portal], creating queries
- queries [BAM], activity searches
- Query Builder [BAM portal], about Query Builder
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal]
- Query Builder [BAM portal], field descriptions
- BAM portal, Query Builder
- BAM portal, activity searches
ms.assetid: 60ab8deb-ebe2-4959-97fd-261ff64d500c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 617461b104f3188c14bb7c5b6eb5eb0bd329693f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="activity-searches-in-the-bam-portal"></a>Búsquedas de actividad del portal de BAM
La búsqueda de actividad le permite realizar búsquedas de datos de BAM para encontrar actividades que coincidan con el criterio que determinó en función de los elementos y valores de seguimiento que están disponibles en la vista de BAM, y para mostrar estas actividades para que las pueda editar y crear alertas en función de las actividades.  
  
## <a name="parts-of-the-query-builder"></a>Partes del Generador de consultas  
 Las consultas para su búsqueda de actividad se generan al seleccionar los elementos de los datos económicos para los que creará comparaciones Boolean para extraer los datos de interés. Primero debe seleccionar una vista BAM desde el **Mis vistas** marco del portal. Desde la vista seleccionada, seleccione una actividad en la que se va a crear la consulta.  
  
 ![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")  
  
 Cuando haya seleccionado la actividad, el marco de contenido del portal muestra los cuadros Generador de consultas, Selector de columnas y Resultados. Puede abrir una consulta existente o generar una nueva.  
  
 ![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")  
  
 Para crear una consulta nueva, empiece por seleccionar un elemento de datos de negocio de la **datos económicos** lista desplegable.  
  
 ![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")  
  
 A continuación, seleccione el operador de comparación en la lista desplegable Operador. El operador de comparación le permite restringir los resultados de la consulta.  
  
 ![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")  
  
 La lista desplegable Valor es contextual y se basa en el tipo de datos representados por el elemento de datos económicos. La interfaz de usuario se cambia de acuerdo con el tipo de datos permitidos.  
  
 Se pueden unir cláusulas de la consulta con y o los operadores OR para formar consultas más complejas, haga clic en el **agregar** botón.  
  
 ![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")  
  
> [!NOTE]
>  No puede agrupar cláusulas. Una consulta es una cadena sencilla de cláusulas individuales combinadas por operadores AND/OR.  
  
 En la tabla siguiente se describen los campos de fecha y hora.  
  
|Operador|Description|  
|--------------|-----------------|  
|**AT**|Especifica una coincidencia exacta. Equivalente a una operación Boolean igual a (=). **Nota:** si selecciona el **en** operador y especifique una fecha sin ninguna parte del tiempo del portal utiliza la medianoche como valor predeterminado. Si esto no es su intención, use la **en o antes de** o **en o después de** operadores para obtener los resultados deseados.|  
|**En o antes de**|Especifica que solo coinciden las transacciones en o antes de los datos determinados. Igual a una operación Boolean menor o igual que (≤).|  
|**En o después de**|Especifica que solo coinciden las transacciones en o después de los datos determinados. Igual a una operación Boolean mayor o igual que (≥).|  
|**Antes del**|Especifica que solo coinciden las transacciones antes de los datos determinados. Equivalente a un valor booleano menor que (\<) operación.|  
|**Después**|Especifica que solo coinciden las transacciones después de los datos determinados. Equivalente a una operación booleana mayor que (>).|  
|**En los últimos**|Especifica que solo coinciden las transacciones que se llevaron a cabo en el período de tiempo anterior que se ha especificado. El período de tiempo se puede especificar en segundos, minutos, horas o días.|  
|**Antes de que la última**|Especifica que solo coinciden las transacciones que se llevaron a cabo con anterioridad al período de tiempo anterior que se ha especificado. El período de tiempo se puede especificar en segundos, minutos, horas o días.|  
|**Está vacío**|Especifica que solo se devuelven las transacciones para las que el elemento de datos económicos no contiene datos (el valor de campo de datos es nulo).|  
|**No está vacío**|Especifica que solo se devuelven las transacciones para las que el elemento de datos económicos no contiene datos (el valor de campo de datos no es nulo).|  
  
 En la tabla siguiente se describen los campos numéricos y los campos de duración. Los campos numéricos contienen datos tales como cantidades o importes de moneda. Los campos de duración especifican un período de tiempo.  
  
|Operador|Description|  
|--------------|-----------------|  
|**Es igual a**|Especifica una coincidencia exacta. Equivalente a una operación Boolean igual a (=).|  
|**Mayor que**|Especifica una coincidencia exacta. Equivalente a una operación Boolean mayor que (>).|  
|**Mayor que o igual a**|Especifica una coincidencia exacta. Equivalente a una operación Boolean mayor que o igual a (≥).|  
|**Menor que**|Especifica una coincidencia exacta. Equivalente a una operación Boolean menor (<).|  
|**Menor que o igual a**|Especifica una coincidencia exacta. Equivalente a una menor que u operación es igual a (≤).|  
|**No igual**|Especifica una coincidencia exacta. Equivalente a una operación no igual (≠).|  
|**Está vacío**|Especifica que solo se devuelven las transacciones para las que el elemento de datos económicos no contiene datos (el valor de campo de datos es nulo).|  
|**No está vacío**|Especifica que solo se devuelven las transacciones para las que el elemento de datos económicos no contiene datos (el valor de campo de datos no es nulo).|  
  
 En la siguiente tabla se describen los campos de texto.  
  
|Operador|Description|  
|--------------|-----------------|  
|**Es exactamente**|Especifica una coincidencia exacta. Equivalente a una operación Boolean igual a (=).|  
|**Contiene**|Especifica que el texto del elemento de datos económicos contiene el valor especificado. Esto le permite realizar coincidencias parciales en los datos.|  
|**No contiene**|Especifica que el texto del elemento de datos económicos no contiene el valor especificado.|  
|**Está vacío**|Especifica que solo se devuelven las transacciones para las que el elemento de datos económicos no contiene datos (el valor de campo de datos es nulo).|  
|**No está vacío**|Especifica que solo se devuelven las transacciones para las que el elemento de datos económicos no contiene datos (el valor de campo de datos no es nulo).|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo crear una consulta de búsqueda de actividad](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [Cómo establecer una alerta](../core/how-to-set-an-alert.md)  
  
-   [Cómo ver los resultados de una búsqueda de actividad](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a>Vea también  
 [Portal de BAM](../core/bam-portal.md)