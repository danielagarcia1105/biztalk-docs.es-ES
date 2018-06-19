---
title: Operaciones de Windows Workflow Foundation | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a048dfc0-26b2-4f20-9d2f-c52f1ab19ac3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62cb1ba3cb82a21bb573145d00057112784c89a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265628"
---
# <a name="operations-in-windows-workflow-foundation"></a>Operaciones en Windows Workflow Foundation
Esta sección contiene las operaciones personalizadas que admite el interceptor de WF de BAM.  
  
## <a name="determining-where-operations-are-allowed"></a>Determinar dónde se permiten las operaciones  
 Las operaciones personalizadas que proporciona el interceptor de WF de BAM se pueden clasificar según el tipo de punto de seguimiento asociado de Windows Workflow Foundation:  
  
-   Actividad  
  
-   Flujo de trabajo  
  
-   Usuario  
  
 El interceptor de WF de BAM utiliza las categorías para asignar un tipo de punto de seguimiento a cada **OnEvent**. Basa esta asignación de los tipos de operaciones que ve en el **OnEvent** filtro y las secciones de extracción y manipulación de datos. Por ejemplo, si la **OnEvent** contiene un **actualización** elemento que usa el **GetUserData** operación, es el proceso de tipo de punto de realizar un seguimiento de usuario porque lo hacen los eventos de actividad y flujo de trabajo no se admite esta operación. Para obtener más información acerca de los puntos de seguimiento, vea System.Workflow.Runtime.Tracking en [http://go.microsoft.com/fwlink/?LinkId=80242](http://go.microsoft.com/fwlink/?LinkId=80242).  
  
> [!NOTE]
>  Los puntos de seguimiento de flujo de trabajo no pueden extraer datos del flujo de trabajo.  
  
 Las operaciones deben ser compatibles dentro de una expresión de filtro y entre la expresión de filtro y las secciones de extracción y manipulación de datos dentro de un elemento `OnEvent`. La siguiente tabla muestra qué operaciones se pueden usar en una expresión de filtro para cada tipo de punto de seguimiento.  
  
|Operación de expresión de filtro|¿Es válida para el punto de seguimiento de la actividad?|¿Es válida para el punto de seguimiento del flujo de trabajo?|¿Es válida para el punto de seguimiento del usuario?|  
|---------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|Es igual a|Sí|Sí|Sí|  
|And|Sí|Sí|Sí|  
|Concatenate|No|No|No|  
|Constante|Sí|Sí|Sí|  
|GetActivityEvent (operación)|Sí|No|No|  
|GetActivityName|Sí|No|Sí|  
|GetActivityProperty|Sí|No|Sí|  
|GetActivityType|Sí|No|Sí|  
|GetContextProperty|No|No|No|  
|GetUserData (operación)|No|No|No|  
|GetUserDataType (operación)|No|No|Sí|  
|GetUserKey (operación)|No|No|Sí|  
|GetWorkflowEvent (operación)|No|Sí|No|  
|GetWorkflowProperty|No|No|No|  
  
 Si mezcla operaciones incompatibles, recibirá un error al implementar el archivo de configuración del interceptor. Por ejemplo, si se usan los la `GetActivityEvent` y `GetWorkflowEvent` dentro de un filtro, o en un evento de extracción o manipulación de datos y filtro (como **CorrelationID**), recibirá un error.  
  
 La tabla siguiente resume las operaciones que admite cada tipo de actividad en la extracción o la manipulación de datos.  
  
|Operación de extracción o manipulación de datos|¿Es válida para el punto de seguimiento de la actividad?|¿Es válida para el punto de seguimiento del flujo de trabajo?|¿Es válida para el punto de seguimiento del usuario?|  
|-----------------------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|Es igual a|Sí|Sí|Sí|  
|And|Sí|Sí|Sí|  
|Concatenate|Sí|Sí|Sí|  
|Constante|Sí|Sí|Sí|  
|GetActivityEvent (operación)|Sí|No|No|  
|GetActivityName|Sí|No|Sí|  
|GetActivityProperty|Sí|No|Sí|  
|GetActivityType|Sí|No|Sí|  
|GetContextProperty|Sí|Sí|Sí|  
|GetUserData (operación)|No|No|Sí|  
|GetUserDataType (operación)|No|No|Sí|  
|GetUserKey (operación)|No|No|Sí|  
|GetWorkflowEvent (operación)|No|Sí|No|  
|GetWorkflowProperty|Sí|No|Sí|  
  
> [!NOTE]
>  Hay una asignación unívoca entre un único **OnEvent** y un único punto de seguimiento.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [GetActivityEvent](../core/getactivityevent.md)  
  
-   [GetActivityName](../core/getactivityname.md)  
  
-   [GetActivityProperty](../core/getactivityproperty.md)  
  
-   [GetActivityType](../core/getactivitytype.md)  
  
-   [Getcontextproperty (operación)](../core/getcontextproperty2.md)  
  
-   [GetUserData](../core/getuserdata.md)  
  
-   [Getuserdatatype (operación)](../core/getuserdatatype.md)  
  
-   [Getuserkey (operación)](../core/getuserkey.md)  
  
-   [Getworkflowevent (operación)](../core/getworkflowevent.md)  
  
-   [GetWorkflowProperty](../core/getworkflowproperty.md)  
  
## <a name="see-also"></a>Vea también  
 [Interceptor de WF de BAM](../core/bam-wf-interceptor.md)