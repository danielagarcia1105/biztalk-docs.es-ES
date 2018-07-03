---
title: 'Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: d1cfb8b9-d4e2-4069-8db3-18f72358652b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9df587902f8b527e82d202221211b8c09cf2f418
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976989"
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a><span data-ttu-id="d6672-102">Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d6672-102">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>
<span data-ttu-id="d6672-103">Veamos un ejemplo que incluye una orquestación.</span><span class="sxs-lookup"><span data-stu-id="d6672-103">Let's look at an example that includes an orchestration.</span></span> <span data-ttu-id="d6672-104">La siguiente ilustración muestra todo el proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6672-104">The following figure displays the entire business process.</span></span> <span data-ttu-id="d6672-105">En este escenario, entra un mensaje en BizTalk Server, se envía a través de una orquestación, se cambia dentro de la orquestación y se envía a un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d6672-105">In this scenario, a message comes into BizTalk Server, is sent through an orchestration, is changed within the orchestration, and is then sent out through a send port.</span></span>  
  
 <span data-ttu-id="d6672-106">![Proceso de mensaje de BizTalk Server](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span><span class="sxs-lookup"><span data-stu-id="d6672-106">![BizTalk Server message process](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span></span>  
  
 <span data-ttu-id="d6672-107">**El proceso de mensajes de BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="d6672-107">**The BizTalk Server message process**</span></span>  
  
 <span data-ttu-id="d6672-108">Éstos son algunos de los datos utilizados en este escenario:</span><span class="sxs-lookup"><span data-stu-id="d6672-108">Here are some of the facts concerning this scenario:</span></span>  
  
- <span data-ttu-id="d6672-109">El tamaño del mensaje es 5 K.</span><span class="sxs-lookup"><span data-stu-id="d6672-109">The message size is 5K.</span></span>  
  
- <span data-ttu-id="d6672-110">No nos estamos promueven propiedades.</span><span class="sxs-lookup"><span data-stu-id="d6672-110">We are not promoting any properties.</span></span>  
  
- <span data-ttu-id="d6672-111">El número de mensajes que se reciben en un año es 3,5 millones.</span><span class="sxs-lookup"><span data-stu-id="d6672-111">The number of messages we receive in a year is 3.5 million.</span></span>  
  
- <span data-ttu-id="d6672-112">El seguimiento está activado para todos los eventos.</span><span class="sxs-lookup"><span data-stu-id="d6672-112">Tracking is turned on for all events.</span></span> <span data-ttu-id="d6672-113">Hay seis eventos en este escenario.</span><span class="sxs-lookup"><span data-stu-id="d6672-113">There are six events in this scenario:</span></span>  
  
  -   <span data-ttu-id="d6672-114">Recepción del mensaje M0</span><span class="sxs-lookup"><span data-stu-id="d6672-114">Receipt of message M0</span></span>  
  
  -   <span data-ttu-id="d6672-115">Salida del mensaje M1 del puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="d6672-115">Output of message M1 from the receive port</span></span>  
  
  -   <span data-ttu-id="d6672-116">Recepción del mensaje M1 por la orquestación</span><span class="sxs-lookup"><span data-stu-id="d6672-116">Receipt of message M1 by the orchestration</span></span>  
  
  -   <span data-ttu-id="d6672-117">Salida del mensaje M2 de la orquestación</span><span class="sxs-lookup"><span data-stu-id="d6672-117">Output of message M2 from the orchestration</span></span>  
  
  -   <span data-ttu-id="d6672-118">Recepción del mensaje M2 por el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="d6672-118">Receipt of message M2 by the send port</span></span>  
  
  -   <span data-ttu-id="d6672-119">Salida del mensaje M3 por la canalización de envío</span><span class="sxs-lookup"><span data-stu-id="d6672-119">Output of message M3 by the send pipeline</span></span>  
  
- <span data-ttu-id="d6672-120">Se crean tres mensajes adicionales en este escenario.</span><span class="sxs-lookup"><span data-stu-id="d6672-120">Three additional messages are created in this scenario.</span></span> <span data-ttu-id="d6672-121">El mensaje M0 es el mensaje entrante y, por tanto, no lo crea BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6672-121">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="d6672-122">El mensaje M1 es el mensaje saliente del puerto de recepción, M2 es el mensaje saliente de la orquestación y M3 es el mensaje saliente del puerto de transmisión.</span><span class="sxs-lookup"><span data-stu-id="d6672-122">Message M1 is the output message from the receive port, M2 is the output message from the orchestration, and M3 is the output message from the transmit port.</span></span>  
  
  <span data-ttu-id="d6672-123">En la fórmula se aplica esta información le ofrece el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="d6672-123">Applying this information to the formula gives the following result:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a><span data-ttu-id="d6672-124">Mensajes de orquestaciones con una sola propiedad promovida</span><span class="sxs-lookup"><span data-stu-id="d6672-124">Messages in orchestrations with a single promoted property</span></span>  
 <span data-ttu-id="d6672-125">Ahora vamos a promover un solo campo en este escenario, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="d6672-125">Now let's promote a single field in this scenario, as in the earlier example.</span></span> <span data-ttu-id="d6672-126">La propiedad promovida tiene un tamaño aproximado de 10 bytes.</span><span class="sxs-lookup"><span data-stu-id="d6672-126">The promoted property is approximately 10 bytes in size.</span></span> <span data-ttu-id="d6672-127">La ecuación tiene ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="d6672-127">The equation now looks like this:</span></span>  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 <span data-ttu-id="d6672-128">Si tiene que promover otra propiedad que tenga un tamaño de 20 bytes, la formula sería:</span><span class="sxs-lookup"><span data-stu-id="d6672-128">If you need to promote an additional property that is 20 bytes in size, the formula now looks like this:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a><span data-ttu-id="d6672-129">Mensajes de orquestaciones con el seguimiento del cuerpo de los mensajes activado</span><span class="sxs-lookup"><span data-stu-id="d6672-129">Messages in orchestrations with message body tracking activated</span></span>  
 <span data-ttu-id="d6672-130">Si desea utilizar seguimiento del cuerpo de los mensajes, el resultado de calcular el espacio adicional necesario es idéntico al resultado del escenario anterior, o 50,1 GB por año.</span><span class="sxs-lookup"><span data-stu-id="d6672-130">If you want to accommodate message tracking, the result from calculating the additional space needed is identical to the result in the earlier scenario, or 50.1 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6672-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6672-131">See Also</span></span>  
 <span data-ttu-id="d6672-132">[Uso de Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="d6672-132">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="d6672-133">[Ajustar el tamaño de la base de datos de seguimiento para realizar un seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="d6672-133">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="d6672-134">[Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="d6672-134">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="d6672-135">[Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="d6672-135">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="d6672-136">Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="d6672-136">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)