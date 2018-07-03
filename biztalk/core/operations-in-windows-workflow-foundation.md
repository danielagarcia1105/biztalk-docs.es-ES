---
title: Operaciones en Windows Workflow Foundation | Microsoft Docs
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
ms.openlocfilehash: 057154a2e64541b00c704be7078ef27ba596de20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007605"
---
# <a name="operations-in-windows-workflow-foundation"></a>Operaciones en Windows Workflow Foundation
Esta sección contiene las operaciones personalizadas que admite el interceptor de WF de BAM.  
  
## <a name="determining-where-operations-are-allowed"></a>Determinar dónde se permiten las operaciones  
 Las operaciones personalizadas que proporciona el interceptor de WF de BAM se pueden clasificar según el tipo de punto de seguimiento asociado de Windows Workflow Foundation:  
  
- Actividad  
  
- Flujo de trabajo  
  
- Usuario  
  
  El interceptor de WF de BAM utiliza las categorías para asignar un tipo de punto de seguimiento a cada **OnEvent**. Basa esta asignación en los tipos de operaciones que ve en el **OnEvent** filtro y las secciones de extracción y manipulación de datos. Por ejemplo, si la **OnEvent** contiene un **actualización** elemento que usa el **GetUserData** operación, es una pista de usuario tipo de punto dado que los eventos de actividad y flujo de trabajo no se admite esta operación. Para obtener más información acerca de los puntos de seguimiento, vea System.Workflow.Runtime.Tracking en [ http://go.microsoft.com/fwlink/?LinkId=80242 ](http://go.microsoft.com/fwlink/?LinkId=80242).  
  
> [!NOTE]
>  Los puntos de seguimiento de flujo de trabajo no pueden extraer datos del flujo de trabajo.  
  
 Las operaciones deben ser compatibles dentro de una expresión de filtro y entre la expresión de filtro y las secciones de extracción y manipulación de datos dentro de un elemento `OnEvent`. La siguiente tabla muestra qué operaciones se pueden usar en una expresión de filtro para cada tipo de punto de seguimiento.  
  
|Operación de expresión de filtro|¿Es válida para el punto de seguimiento de la actividad?|¿Es válida para el punto de seguimiento del flujo de trabajo?|¿Es válida para el punto de seguimiento del usuario?|  
|---------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|Es igual a|Sí|Sí|Sí|  
|And|Sí|Sí|Sí|  
|Concatenate|no|no|no|  
|Constante|Sí|Sí|Sí|  
|GetActivityEvent (operación)|Sí|no|no|  
|GetActivityName|Sí|no|Sí|  
|GetActivityProperty|Sí|no|Sí|  
|GetActivityType|Sí|no|Sí|  
|GetContextProperty|no|no|no|  
|GetUserData (operación)|no|no|no|  
|GetUserDataType (operación)|no|no|Sí|  
|GetUserKey (operación)|no|no|Sí|  
|GetWorkflowEvent (operación)|no|Sí|no|  
|GetWorkflowProperty|no|no|no|  
  
 Si mezcla operaciones incompatibles, recibirá un error al implementar el archivo de configuración del interceptor. Por ejemplo, si utiliza ambos el `GetActivityEvent` y `GetWorkflowEvent` dentro de un filtro, o en un evento de extracción o manipulación de datos y filtro (como **CorrelationID**), recibirá un error.  
  
 La tabla siguiente resume las operaciones que admite cada tipo de actividad en la extracción o la manipulación de datos.  
  
|Operación de extracción o manipulación de datos|¿Es válida para el punto de seguimiento de la actividad?|¿Es válida para el punto de seguimiento del flujo de trabajo?|¿Es válida para el punto de seguimiento del usuario?|  
|-----------------------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|Es igual a|Sí|Sí|Sí|  
|And|Sí|Sí|Sí|  
|Concatenate|Sí|Sí|Sí|  
|Constante|Sí|Sí|Sí|  
|GetActivityEvent (operación)|Sí|no|no|  
|GetActivityName|Sí|no|Sí|  
|GetActivityProperty|Sí|no|Sí|  
|GetActivityType|Sí|no|Sí|  
|GetContextProperty|Sí|Sí|Sí|  
|GetUserData (operación)|no|no|Sí|  
|GetUserDataType (operación)|no|no|Sí|  
|GetUserKey (operación)|no|no|Sí|  
|GetWorkflowEvent (operación)|no|Sí|no|  
|GetWorkflowProperty|Sí|no|Sí|  
  
> [!NOTE]
>  Hay una asignación unívoca entre un único **OnEvent** y un único punto de seguimiento.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [GetActivityEvent](../core/getactivityevent.md)  
  
-   [GetActivityName](../core/getactivityname.md)  
  
-   [GetActivityProperty](../core/getactivityproperty.md)  
  
-   [GetActivityType](../core/getactivitytype.md)  
  
-   [GetContextProperty](../core/getcontextproperty2.md)  
  
-   [GetUserData](../core/getuserdata.md)  
  
-   [GetUserDataType](../core/getuserdatatype.md)  
  
-   [GetUserKey](../core/getuserkey.md)  
  
-   [GetWorkflowEvent](../core/getworkflowevent.md)  
  
-   [GetWorkflowProperty](../core/getworkflowproperty.md)  
  
## <a name="see-also"></a>Vea también  
 [Interceptor de WF de BAM](../core/bam-wf-interceptor.md)