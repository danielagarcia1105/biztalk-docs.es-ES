---
title: Nodos Continuation y ContinuationID | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- Continuation nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- BAM, correlating activities
- activities, linking
- activities, continuation tokens
- ContinuationID nodes [Tracking Profile Editor]
ms.assetid: aa050660-66f7-4084-b6bf-b9319ce625af
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa8956721d4a44b51b8d2c7776560aaa878f864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238092"
---
# <a name="continuation-and-continuationid-nodes"></a>Nodos Continuation y ContinuationID
Las continuaciones proporcionan a la infraestructura de BAM la siguiente información:  
  
-   El orden en que se espera que se produzcan los eventos  
  
-   Un medio para controlar cualquier cambio en el Id. único con el que se correlacionan los elementos de evento  
  
 Dicho de otra forma, las continuaciones definen la transferencia de esta información entre colaboradores de una actividad. Se producirá una transferencia en las situaciones siguientes:  
  
-   Si existe un cambio de ActivityID entre la hora de inicio y la hora de fin de una actividad. Por ejemplo, si existen dos mensajes relacionados, como un número de pedido y un número de pedido de venta. Cada uno de ellos tiene asignado un número exclusivo, por ejemplo 123456 para el número de pedido y 987654 para el número del pedido de venta. En este caso, se utilizará una continuación para equiparar los identificadores únicos del pedido y del pedido de venta, de modo que los eventos puedan correlacionarse con la actividad que tienen en común, independientemente del identificador único que esté asociado a los eventos entrantes.  
  
-   Existe una transición de un entorno en tiempo de ejecución a otro. Por ejemplo, en un escenario donde haya una aplicación que proporciona un pedido de compra a una canalización de mensajería de BizTalk Server, que, a continuación, se invoca una orquestación y la orquestación, a continuación, pasa el control a una aplicación que envía un aviso de envío, se tienen dos transiciones de entorno: desde una canalización de mensajería a un una orquestación y desde una orquestación a una canalización de mensajería.  
  
 Un punto importante que hay que recordar al seleccionar una propiedad para usarla en la continuación es que las propiedades deben asignarse desde el mismo contexto.  
  
 Por ejemplo, si tiene las propiedades Message.InterchangeID y servicecontext.InterchangeID será como si pudiera usar InterchangeID para crear la continuación. Si los mensajes se originan en diferentes contextos, no puede usar InterchangeID (ni otra propiedad) para crear una continuación confiable.  
  
## <a name="working-with-continuation-nodes"></a>Trabajar con nodos de continuación  
 El nodo de continuación contiene elementos de datos que indican un identificador único de instancia, también se denomina un *token de continuación*. Con el token de continuación, los programadores pueden vincular a otras actividades que usan el nodo ContinuationID.  
  
 Existen tres escenarios básicos en los que se utilizan los nodos de continuación y de ContinuationID:  
  
-   De orquestación a orquestación  
  
-   De orquestación a solución de BizTalk  
  
-   De solución de BizTalk a orquestación  
  
 En el escenario de orquestaciones, el TPE debe definir un nodo de continuación y un nodo de ContinuationID, y ambos nodos deberán tener el mismo nombre para que BAM pueda correlacionar las actividades.  
  
 El escenario de orquestación a solución de BizTalk permite utilizar el TPE para definir un nodo de continuación, y el programador crea una solución que utiliza la API de la BAM para controlar la parte de destino de la continuación.  
  
 En escenarios de solución de BizTalk a orquestación, el programador utiliza la API de BAM para proporcionar el origen del par de continuación, y el nodo de ContinuationID se define utilizando el TPE.  
  
> [!NOTE]
>  Los puertos bidireccionales pueden funcionar en cualquier dirección, lo que significa que la intercepción de los datos que pasan a través de los puertos requerirá la habilitación de una continuación, dependiendo del comportamiento de la solución de BizTalk. Por ejemplo, si la activación registra “PortEndTime” para la activación de un puerto de mensajería de BizTalk Server en cualquier dirección (si lo nombres de elemento son, por ejemplo, “MessageReceived” y “MessageSent,” en ese orden), deberá crear una continuación entre ellos. Se requerirá una continuación siempre que exista más de una secuencia de eventos que colabore en una actividad de BAM, y existen diversas secuencias de eventos por punto de implementación (como mensajería de entrada de BTS, mensajería de salida de BTS, orquestación, aplicaciones personalizadas y servicios Web).  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear una continuación](../core/how-to-create-a-continuation.md)   
 [Nodos de vista de actividad TPE](../core/tpe-activity-view-nodes.md)