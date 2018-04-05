---
title: 'Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para mensajes envían fuera a listas de distribución | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: bc6e0da0-46d1-42d6-8ec9-29a28719fbb3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dca1722e24e0c76c85699ea00fcf6ffc120b2e14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-3-sizing-the-tracking-database--for-messages-sent-out-to-distribution-lists"></a><span data-ttu-id="8be52-102">Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="8be52-102">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>
<span data-ttu-id="8be52-103">En la siguiente ilustración, tiene un mensaje que procede a través de una orquestación, se cambia dentro de la orquestación y se envía a varios puertos de envío a través de una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="8be52-103">In the following figure, you have a message that proceeds through an orchestration, is changed within the orchestration, and is then sent out to several different send ports through a distribution list.</span></span>  
  
 <span data-ttu-id="8be52-104">![Mensaje a través de una orquestación a varios puertos](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")</span><span class="sxs-lookup"><span data-stu-id="8be52-104">![Message through an orchestration to multiple ports](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")</span></span>  
  
 <span data-ttu-id="8be52-105">**Mensaje de BizTalk Server que se realiza a través de una orquestación y se envía a varios puertos**</span><span class="sxs-lookup"><span data-stu-id="8be52-105">**BizTalk Server message that proceeds through an orchestration and is sent out to several different ports**</span></span>  
  
 <span data-ttu-id="8be52-106">Éstos son algunos de los datos utilizados en este escenario:</span><span class="sxs-lookup"><span data-stu-id="8be52-106">Here are some of the facts concerning this scenario:</span></span>  
  
-   <span data-ttu-id="8be52-107">El tamaño del mensaje es de 10 KB.</span><span class="sxs-lookup"><span data-stu-id="8be52-107">The message size is 10K.</span></span>  
  
-   <span data-ttu-id="8be52-108">No se promueven propiedades.</span><span class="sxs-lookup"><span data-stu-id="8be52-108">You are not promoting any properties.</span></span>  
  
-   <span data-ttu-id="8be52-109">Se reciben 3,5 millones de mensajes al año.</span><span class="sxs-lookup"><span data-stu-id="8be52-109">The number of messages you receive in a year is 3.5 million.</span></span>  
  
-   <span data-ttu-id="8be52-110">El seguimiento está activado para todos los eventos.</span><span class="sxs-lookup"><span data-stu-id="8be52-110">Tracking is turned on for all events.</span></span> <span data-ttu-id="8be52-111">Hay cinco eventos en este escenario.</span><span class="sxs-lookup"><span data-stu-id="8be52-111">There are five events in this scenario:</span></span>  
  
    -   <span data-ttu-id="8be52-112">Recepción del mensaje M0</span><span class="sxs-lookup"><span data-stu-id="8be52-112">Receipt of message M0</span></span>  
  
    -   <span data-ttu-id="8be52-113">Salida del mensaje M1 del puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="8be52-113">Output of message M1 from the receive port</span></span>  
  
    -   <span data-ttu-id="8be52-114">Salida del mensaje M3 por el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="8be52-114">Output of message M3 by the send port</span></span>  
  
    -   <span data-ttu-id="8be52-115">Salida del mensaje M4 por el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="8be52-115">Output of message M4 by the send port</span></span>  
  
    -   <span data-ttu-id="8be52-116">Salida del mensaje M5 por el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="8be52-116">Output of message M5 by the send port</span></span>  
  
 <span data-ttu-id="8be52-117">Si se aplica esta información a la ecuación, se obtiene el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8be52-117">Applying this information to the equation gives the following:</span></span>  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-a-single-promoted-property"></a><span data-ttu-id="8be52-118">Mensajes de una orquestación que se envían a una lista de distribución con una sola propiedad promovida</span><span class="sxs-lookup"><span data-stu-id="8be52-118">Messages in an orchestration that are sent out to a distribution list with a single promoted property</span></span>  
 <span data-ttu-id="8be52-119">En este ejemplo, vamos a promover una sola propiedad con un tamaño aproximado de 10 bytes, como hicimos en un escenario anterior.</span><span class="sxs-lookup"><span data-stu-id="8be52-119">In this example, let's promote a single property, approximately 10 bytes in size, as we did in an earlier scenario.</span></span> <span data-ttu-id="8be52-120">La ecuación tiene ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="8be52-120">The equation now looks like this:</span></span>  
  
```  
[((5*150 bytes) + (10*230 bytes) + (1*5(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 260) * 3,500,000]/1024/1024 = 11048 MB ~ 10.79 GB per year  
```  
  
 <span data-ttu-id="8be52-121">Si promovemos otra propiedad que tenga un tamaño de 20 bytes, la ecuación sería:</span><span class="sxs-lookup"><span data-stu-id="8be52-121">If we promote an additional property that is 20 bytes in size the equation now looks like this:</span></span>  
  
```  
[((5*150 bytes) + (10*230 bytes) + ((1*5(52 bytes + 10 bytes) + (1*5(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 670) * 3,500,000]/1024/1024 = 12417 MB ~ 12.13 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-message-body-tracking-activated"></a><span data-ttu-id="8be52-122">Mensajes de una orquestación que se envían a una lista de distribución con el seguimiento del cuerpo de los mensajes activado</span><span class="sxs-lookup"><span data-stu-id="8be52-122">Messages in an orchestration that are sent out to a distribution list with message body tracking activated</span></span>  
 <span data-ttu-id="8be52-123">Si desea utilizar el seguimiento del cuerpo de los mensajes, la ecuación sería la siguiente para este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8be52-123">If you want to accommodate message tracking, the equation will look like the following for this example:</span></span>  
  
```  
[3,500,000 * 6 * 5KB]/1024 = 102539.06 MB ~ 100.14 GB per year  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="8be52-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8be52-124">See Also</span></span>  
 <span data-ttu-id="8be52-125">[Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="8be52-125">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="8be52-126">[Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="8be52-126">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="8be52-127">[Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8be52-127">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="8be52-128">[Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="8be52-128">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="8be52-129">Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes</span><span class="sxs-lookup"><span data-stu-id="8be52-129">Scenario 4: Sizing the Tracking Database for all Messages</span></span>](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)