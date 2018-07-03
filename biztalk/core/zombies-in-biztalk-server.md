---
title: Zombies en BizTalk Server | Microsoft Docs
description: Causas comunes de los mensajes de zombie en BizTalk Server
ms.custom: ''
ms.date: 03/23/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c684891-e984-442f-b5fd-de5f7cf32b44
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6a243e772fe5bc8408288167d3e8882a74e9a57
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976589"
---
# <a name="zombies-in-biztalk-server"></a>Zombies en BizTalk Server

## <a name="what-is-a-zombie"></a>¿Qué es un zombie?  
  
-   Un mensaje zombie es un mensaje que se ha enrutado hacia una orquestación en ejecución desde el cuadro de mensajes y estaba "en proceso" cuando finalizó la orquestación. Un mensaje "en proceso" es un mensaje que se ha enrutado hacia una instancia de servicio y, por consiguiente, se encuentra en una cola del cuadro de mensajes destinada a esa instancia de servicio. Dado que la instancia de la orquestación suscriptora ya no puede consumir el mensaje, éste último queda suspendido y se marca con el valor "Suspendido (No reanudable)" en ServiceInstance/State.  
  
-   Una instancia de servicio zombie es una instancia de una orquestación que se completó mientras un mensaje enrutado hacia la instancia de orquestación desde el cuadro de mensajes estaba aún "en proceso". Dado que la instancia de la orquestación ha finalizado, ya no puede consumir los mensajes "en proceso", por lo que queda suspendida y se marca con el valor "Suspendido (No reanudable)" en ServiceInstance/State.  
  
## <a name="typical-causes"></a>Causas típicas
Los zombies suelen corresponder a una de las siguientes categorías:  
  
1. **Mensajes de control finalizados** : el motor de orquestaciones permite el uso de los mensajes de control para cancelar todo el trabajo que se está ejecutando en una instancia de orquestación específica. Puesto que el mensaje de control detiene inmediatamente la orquestación en ejecución, cabe esperar que se produzca alguna instancia zombie. Algunos diseños, como los relacionados con el flujo de trabajo de usuarios, suelen usar este mecanismo.  
  
2. **Recepciones con escucha paralela** : en este escenario la instancia de servicio espera 1 de n mensajes y cuando recibe determinados mensajes realiza algunas tareas y finaliza. Si se reciben mensajes por una rama paralela justo mientras la instancia de servicio está finalizando, se crean zombies.  
  
3. **Convoyes secuenciales con extremos no deterministas** : en este escenario, una programación de orquestación principal está diseñada para administrar todos los mensajes de un tipo determinado con el fin de cumplir con algún tipo de requisito de diseño del sistema. Estos requisitos del sistema pueden incluir entrega ordenada, distribuidor de recursos y procesamiento por lotes. Para este escenario, la tendencia es definir un bucle while que rodea un comando listen con una rama que tenga una forma de recepción y otra rama con una forma de retraso, seguido por algún tipo de construcción que establece una variable para indicar que el bucle while debe detenerse. Se trata de un código no determinista, puesto que podría activarse el retraso y, aún así, entregarse un mensaje. Los extremos no deterministas como éste son proclives a generar zombies.  
  
   Cuando se suspende una instancia de servicio zombie, se genera el mensaje de error siguiente:  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 Puede usar el [terminador de BizTalk](https://www.microsoft.com/download/details.aspx?id=2846) para ayudar a quitar zombies.  
  
## <a name="see-also"></a>Vea también  
 **Eliminación de instancias de servicio suspendidas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]