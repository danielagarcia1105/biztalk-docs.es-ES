---
title: Acerca de la sesión 2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3ecdb4f-d384-42ac-9776-e7ad14d5f151
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9d34038acceb0bd52dc598ca48cf5e914d70d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225612"
---
# <a name="about-session-management"></a>Administración de sesiones
El adaptador de Microsoft BizTalk para J.D. Edwards EnterpriseOne crea una sesión de conexión para enviar una llamada al servidor J.D. Edwards EnterpriseOne. Cuando la llamada termina, la sesión se coloca en un grupo para que pueda ser utilizada por una llamada posterior. El adaptador crea varias sesiones de conexión para controlar las llamadas concurrentes al servidor J.D. Edwards EnterpriseOne. El grupo se limpia regularmente para quitar sesiones que ya no son necesarias.  
  
 El adaptador de Microsoft BizTalk para J.D. Edwards EnterpriseOne proporciona dos propiedades de contexto de mensaje para controlar el momento en que deben tener lugar las llamadas dentro de la misma sesión.  
  
|Nombre|Tipo|Predeterminado|  
|----------|----------|-------------|  
|JDE.SessionID|int|0|  
|JDE.ReserveSession|boolean|false|  
  
 La administración de sesiones es innecesaria si la función empresarial requiere una única llamada al servidor J.D. Edwards EnterpriseOne. El adaptador puede seleccionar cualquier sesión disponible y la sesión permanece disponible para las llamadas siguientes. En este escenario, se pueden omitir las propiedades de contexto de mensaje, ya que los valores predeterminados resultan adecuados.  
  
 Alguna funcionalidad de J.D. Edwards EnterpriseOne requiere varias llamadas al servidor J.D. Edwards EnterpriseOne; por ejemplo, la creación de SalesOrder. La primera llamada a BeginDoc crea un SalesOrder en blanco. Cada llamada posterior a EditLine agrega un elemento de línea a SalesOrder. Por último, la llamada a EndDoc cierra SalesOrder.  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 Para que no haya errores, todas las llamadas a una SalesOrder deben enviarse en la misma sesión. Para ello, asigne propiedades de contexto de mensaje para indicar al adaptador qué hacer con la sesión. Para el ejemplo de SalesOrder, éstos son los valores que se asignarían a las propiedades de contexto de mensaje para controlar la sesión de J.D. Edwards EnterpriseOne:  
  
|Función|SessionID|ReserveSession|  
|--------------|---------------|--------------------|  
|BeginDoc|0|true|  
|EditLine|Se copia de la respuesta BeginDoc|true|  
|EditLine|Se copia de la respuesta BeginDoc|true|  
|EndDoc|Copia de la respuesta BeginDoc|false|  
  
-   Para la primera llamada, el adaptador puede elegir cualquier sesión disponible (porque el valor de SessionID es cero).  
  
-   El adaptador devuelve el valor de SessionID usado en la respuesta BeginDoc.  
  
-   La propiedad ReserveSession indica al adaptador que reserve esta sesión para las llamadas siguientes que soliciten de forma explícita esta sesión. Ninguna otra llamada puede reutilizar accidentalmente la sesión porque está reservada.  
  
-   Las llamadas posteriores solicitan la sesión al establecer SessionID con el valor devuelto en BeginDoc.  
  
-   La propiedad ReserveSession está establecida como True, al menos hasta la última llamada de la serie.  
  
-   La última llamada establece ReserveSession como False para que la sesión esté disponible para cualquier llamada siguiente. No obstante, la orquestación puede optar por conservar la sesión para más llamadas.  
  
 Si la sesión no se usa durante un tiempo, el grupo la eliminará aunque la sesión siga reservada por error.  
  
 Para obtener información detallada sobre las propiedades de contexto de mensaje, vea la documentación de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Usar propiedades de contexto de mensaje](../core/using-message-context-properties1.md)