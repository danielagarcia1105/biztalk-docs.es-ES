---
title: Zombies en BizTalk Server | Documentos de Microsoft
description: Causas comunes de mensajes zombies en BizTalk Server
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
ms.openlocfilehash: 9764522d2ff5265b6f28f2f125cb33b2982a7605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290548"
---
# <a name="zombies-in-biztalk-server"></a>Zombies en BizTalk Server

## <a name="what-is-a-zombie"></a>¿Qué es un zombie?  
  
-   Un mensaje zombie es un mensaje que se ha enrutado hacia una orquestación en ejecución desde el cuadro de mensajes y estaba "en proceso" cuando finalizó la orquestación. Un mensaje "en proceso" es un mensaje que se ha enrutado hacia una instancia de servicio y, por consiguiente, se encuentra en una cola del cuadro de mensajes destinada a esa instancia de servicio. Dado que la instancia de la orquestación suscriptora ya no puede consumir el mensaje, éste último queda suspendido y se marca con el valor "Suspendido (No reanudable)" en ServiceInstance/State.  
  
-   Una instancia de servicio zombie es una instancia de una orquestación que se completó mientras un mensaje enrutado hacia la instancia de orquestación desde el cuadro de mensajes estaba aún "en proceso". Dado que la instancia de la orquestación ha finalizado, ya no puede consumir los mensajes "en proceso", por lo que queda suspendida y se marca con el valor "Suspendido (No reanudable)" en ServiceInstance/State.  
  
## <a name="typical-causes"></a>Causas habituales
Los zombies suelen corresponder a una de las siguientes categorías:  
  
1.  **Mensajes de control finalizados** : el motor de orquestaciones permite el uso de mensajes de control para cancelar todo el trabajo que se está ejecutando en una instancia de orquestación específica. Puesto que el mensaje de control detiene inmediatamente la orquestación en ejecución, cabe esperar que se produzca alguna instancia zombie. Algunos diseños, como los relacionados con el flujo de trabajo de usuarios, suelen usar este mecanismo.  
  
2.  **Recepciones con escucha paralela** : en este escenario la instancia de servicio espera 1 de n mensajes y cuando recibe ese mensaje realiza algunas tareas y finaliza. Si se reciben mensajes por una rama paralela justo mientras la instancia de servicio está finalizando, se crean zombies.  
  
3.  **Convoyes secuenciales con extremos no deterministas** : en este escenario, una programación de orquestación principal está diseñada para controlar todos los mensajes de un tipo determinado para cumplir con algún tipo de requisito de diseño del sistema. Estos requisitos del sistema pueden incluir entrega ordenada, distribuidor de recursos y procesamiento por lotes. Para este escenario, la tendencia es definir un bucle while que rodea un comando listen con una rama que tenga una forma de recepción y otra rama con una forma de retraso, seguido por algún tipo de construcción que establece una variable para indicar que el bucle while debe detenerse. Se trata de un código no determinista, puesto que podría activarse el retraso y, aún así, entregarse un mensaje. Los extremos no deterministas como éste son proclives a generar zombies.  
  
 Cuando se suspende una instancia de servicio zombie, se genera el siguiente mensaje de error:  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 Puede usar el [terminador de BizTalk](https://www.microsoft.com/download/details.aspx?id=2846) para ayudar a quitar zombies.  
  
## <a name="see-also"></a>Vea también  
 **Quitar instancias de servicio suspendidas**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]