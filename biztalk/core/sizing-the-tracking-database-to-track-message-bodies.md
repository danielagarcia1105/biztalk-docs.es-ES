---
title: "Ajustar el tamaño de la base de datos de seguimiento de cuerpos de mensaje de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
- message variables [Tracking database], MsgNum
- HAT, ports
- Tracking database, messages
- tracking, orchestrations
- tracking, messages
- HAT, orchestrations
- tracking, ports
ms.assetid: ee75e530-f15d-4ceb-ba67-0b0b24d9df6b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5abc3f2a48f2baea5d158e1a0268a7eede51c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a><span data-ttu-id="aa441-102">Ajustar el tamaño de la base de datos de seguimiento para realizar un seguimiento de los cuerpos de mensaje</span><span class="sxs-lookup"><span data-stu-id="aa441-102">Sizing the Tracking Database to Track Message Bodies</span></span>
<span data-ttu-id="aa441-103">Si planea realizar un seguimiento de los cuerpos de mensaje en la base de datos de seguimiento de BizTalk, tendrá que tener en cuenta el tamaño de éstos al realizar los cálculos.</span><span class="sxs-lookup"><span data-stu-id="aa441-103">If you plan to track the message bodies in the BizTalk Tracking database, then you will also need to account for the size of these bodies in your calculation.</span></span> <span data-ttu-id="aa441-104">Use la siguiente ecuación:</span><span class="sxs-lookup"><span data-stu-id="aa441-104">Use the following equation:</span></span>  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 <span data-ttu-id="aa441-105">Considere la posibilidad de agregar el tamaño medio del contexto de mensaje en el valor MsgSize anterior si resulta significativo en relación con el tamaño del mensaje.</span><span class="sxs-lookup"><span data-stu-id="aa441-105">Consider adding the average size of the message context to MsgSize above if it is significant compared to the message size.</span></span>  
  
 <span data-ttu-id="aa441-106">La variable MsgNum se determina al activar las características de seguimiento en el nivel de puerto o en el nivel de orquestación mediante el seguimiento de instancias de servicios y eventos de mensajes en la página Concentrador de grupo.</span><span class="sxs-lookup"><span data-stu-id="aa441-106">The MsgNum variable is determined by turning on the tracking features at the port level or at the orchestration level using the message event and service instance tracking in the Group Hub page.</span></span> <span data-ttu-id="aa441-107">Asimismo, deberá aplicar esta fórmula a cada proceso de mensaje.</span><span class="sxs-lookup"><span data-stu-id="aa441-107">You must apply this formula to each message process as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa441-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa441-108">See Also</span></span>  
 <span data-ttu-id="aa441-109">[Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="aa441-109">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="aa441-110">[Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="aa441-110">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="aa441-111">[Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="aa441-111">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="aa441-112">[Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="aa441-112">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="aa441-113">Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="aa441-113">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)