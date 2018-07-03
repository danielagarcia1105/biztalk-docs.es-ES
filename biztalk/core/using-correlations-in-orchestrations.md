---
title: Uso de correlaciones en orquestaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, orchestrations
- messages, correlation sets
- correlation sets
- orchestrations, messages
- messages, validating
ms.assetid: d919afa9-bada-406a-bf4b-7b46c831c6d5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbd81b40006842bc17344b4b39aced80fec4e602
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973909"
---
# <a name="using-correlations-in-orchestrations"></a>Usar correlaciones en orquestaciones
La correlación es el proceso de hacer coincidir un mensaje entrante con la instancia apropiada de una orquestación. Por ejemplo, la orquestación envía un mensaje y recibe la respuesta o respuestas en la misma orquestación. Hay tres patrones de intercambio de mensajes correlacionados:  
  
- Protocolo de enlace tradicional  
  
- Convoy secuencial  
  
- Convoy paralelo  
  
  En el patrón de protocolo de enlace tradicional, existen protocolos de enlace entre los intercambios de los mensajes entre las orquestaciones o los procesos empresariales, y el protocolo de enlace se puede conseguir mediante la definición de conjuntos de correlaciones en las orquestaciones, donde un conjunto de correlaciones es una lista de propiedades promocionadas con valores específicos que se utiliza para enrutar mensajes a una instancia de orquestación específica.  
  
  Por ejemplo, si la orquestación está diseñada para emitir un pedido, recibir una factura y realizar el pago, debe asegurarse de que el mensaje de la factura se reciba en la misma instancia de orquestación desde la que se envió el correspondiente pedido, dado que se pueden procesar varios pedidos simultáneamente. En este ejemplo, el número de identificación del pedido se puede usar como un parámetro del conjunto de correlaciones que permita correlacionar el mensaje del pedido y el mensaje de la factura. El siguiente escenario sigue este ejemplo:  
  
1. La Orquestación A envía el mensaje del pedido a la Orquestación B. El conjunto de correlaciones se inicializa antes de enviar el mensaje del pedido.  
  
2. En la Orquestación B, donde se procesa el pedido y se genera y devuelve la factura, la primera forma Recepción sigue el mismo conjunto de correlaciones para recibir el mensaje del pedido.  
  
3. Después de procesar el mensaje del pedido, también se sigue el mismo conjunto de correlaciones para devolver el mensaje de la factura.  
  
4. En la forma Recepción de la Orquestación A que recibe el mensaje de la factura de la orquestación B también se sigue el mismo conjunto de correlaciones con el fin de garantizar que se recibe el mensaje de factura correlacionado basado en el conjunto de correlaciones predefinido.  
  
   Los patrones de convoy secuencial y de convoy paralelo surgen cada vez que es necesario relacionar varios elementos individuales para lograr algo que el elemento individual por sí solo no puede. Para obtener más información, consulte [trabajar con escenarios de convoyes](../core/working-with-convoy-scenarios.md).  
  
   Además de los patrones de intercambio de mensajes correlacionados, en la orquestación existen dos tipos de correlaciones:  
  
- Correlación manual  
  
- Correlación automática  
  
  En el escenario de la correlación manual, configurará las orquestaciones manualmente para inicializar y seguir el conjunto de correlaciones que asociará los mensajes con las instancias adecuadas. En el escenario de la correlación automática, el motor de mensajería correlacionará los mensajes y las instancias automáticamente, por ejemplo, al configurar el puerto Solicitud-respuesta o el puerto de autocorrelación en las orquestaciones.  
  
  Deberá usar la correlación siempre que la orquestación no disponga de una forma explícita de asociar un mensaje con una instancia, como en el caso de una recepción de activación, un puerto de solicitud-respuesta o un puerto de autocorrelación.  
  
## <a name="examples-of-using-correlations"></a>Ejemplos de uso de correlaciones  
  
-   [PartyResolution (ejemplo de BizTalk Server)](../core/partyresolution-biztalk-server-sample.md)  
  
-   Descargue el ejemplo SDK "Correlacionar Messages with Orchestration Instances" de [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
-   Descargue el ejemplo SDK "Parallel Convoy" de [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Conjuntos de correlaciones](../core/correlation-sets.md) 
  
-   [Tipos de correlaciones](../core/correlation-types.md) 
  
-   [Cómo agregar y quitar conjuntos de correlaciones](../core/how-to-add-and-remove-correlation-sets.md) 
  
-   [Cómo configurar conjuntos de correlaciones](../core/how-to-configure-correlation-sets.md)  
  
-   [Cómo configurar tipos de correlaciones](../core/how-to-configure-correlation-types.md)  
  
-   [Trabajar con escenarios de convoyes](../core/working-with-convoy-scenarios.md)  
  
## <a name="see-also"></a>Vea también  
 [Puertos de enlace de uso directo de autocorrelación](../core/how-to-use-self-correlating-direct-bound-ports.md)