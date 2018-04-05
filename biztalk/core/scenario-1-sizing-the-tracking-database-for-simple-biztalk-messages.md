---
title: 'Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: 5b8fed48-d9c9-4d1f-a320-d3e23b8b1ec9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9c99c99485e34f95c6f6a75b86170d73678518
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a><span data-ttu-id="8a42b-102">Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8a42b-102">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>
<span data-ttu-id="8a42b-103">En la ilustración siguiente, un mensaje sencillo del servidor BizTalk Server entra y sale de éste sin sufrir ninguna transformación.</span><span class="sxs-lookup"><span data-stu-id="8a42b-103">In the following figure, a simple BizTalk Server message passes in and out of BizTalk Server without undergoing any message transformation.</span></span>  
  
 <span data-ttu-id="8a42b-104">![Mensaje de BizTalk Server simple &#45; ninguna transformación](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span><span class="sxs-lookup"><span data-stu-id="8a42b-104">![Simple BizTalk Server message &#45; no transformation](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span></span>  
  
 <span data-ttu-id="8a42b-105">**Un simple mensaje de BizTalk Server: sin transformación**</span><span class="sxs-lookup"><span data-stu-id="8a42b-105">**A simple BizTalk Server message - no transformation**</span></span>  
  
 <span data-ttu-id="8a42b-106">Antes de aplicar la fórmula de la sección anterior, necesitará algunos datos acerca de este escenario.</span><span class="sxs-lookup"><span data-stu-id="8a42b-106">Before you apply the formula in the previous section, you will need to gather some facts about this scenario.</span></span> <span data-ttu-id="8a42b-107">En este ejemplo, se usan los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="8a42b-107">In this example, we use the following:</span></span>  
  
-   <span data-ttu-id="8a42b-108">El tamaño del mensaje es 5 K.</span><span class="sxs-lookup"><span data-stu-id="8a42b-108">The message size is 5K.</span></span>  
  
-   <span data-ttu-id="8a42b-109">No se promoverá ninguna propiedad.</span><span class="sxs-lookup"><span data-stu-id="8a42b-109">No properties will be promoted.</span></span>  
  
-   <span data-ttu-id="8a42b-110">Se reciben 3,5 millones de mensajes al año.</span><span class="sxs-lookup"><span data-stu-id="8a42b-110">The number of messages you receive in a year is 3.5 million.</span></span>  
  
-   <span data-ttu-id="8a42b-111">El seguimiento está activado para todos los eventos.</span><span class="sxs-lookup"><span data-stu-id="8a42b-111">Tracking is turned on for all events.</span></span> <span data-ttu-id="8a42b-112">Hay cuatro eventos en este escenario.</span><span class="sxs-lookup"><span data-stu-id="8a42b-112">There are four events in this scenario.</span></span> <span data-ttu-id="8a42b-113">Estos eventos son:</span><span class="sxs-lookup"><span data-stu-id="8a42b-113">The events are:</span></span>  
  
    -   <span data-ttu-id="8a42b-114">Recepción del mensaje M0</span><span class="sxs-lookup"><span data-stu-id="8a42b-114">Receipt of message M0</span></span>  
  
    -   <span data-ttu-id="8a42b-115">Salida del mensaje M1 del puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="8a42b-115">Output of message M1 from the receive port</span></span>  
  
    -   <span data-ttu-id="8a42b-116">Recepción del mensaje M1 por la canalización de transmisión</span><span class="sxs-lookup"><span data-stu-id="8a42b-116">Receipt of message M1 by the transmit pipeline</span></span>  
  
    -   <span data-ttu-id="8a42b-117">Salida del mensaje M2 por la canalización de envío</span><span class="sxs-lookup"><span data-stu-id="8a42b-117">Output of message M2 by the send pipeline</span></span>  
  
-   <span data-ttu-id="8a42b-118">Se crean dos mensajes adicionales en este escenario.</span><span class="sxs-lookup"><span data-stu-id="8a42b-118">Two additional messages are created in this scenario.</span></span> <span data-ttu-id="8a42b-119">El mensaje M0 es el mensaje entrante y, por tanto, no lo crea BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8a42b-119">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="8a42b-120">M1 es el mensaje de salida del puerto de recepción y M2 es el mensaje de salida del puerto de transmisión.</span><span class="sxs-lookup"><span data-stu-id="8a42b-120">Message M1 is the output message from the receive port and M2 is the output from the transmit port.</span></span> <span data-ttu-id="8a42b-121">BizTalk Server crea los mensajes M1 y M2.</span><span class="sxs-lookup"><span data-stu-id="8a42b-121">M1 and M2 are created by BizTalk Server.</span></span>  
  
 <span data-ttu-id="8a42b-122">Si se aplica esta información a la fórmula, se obtiene el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8a42b-122">Applying this information to the formula gives the following:</span></span>  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a><span data-ttu-id="8a42b-123">Mensajes con una única propiedad promovida</span><span class="sxs-lookup"><span data-stu-id="8a42b-123">Messages with a single promoted property</span></span>  
 <span data-ttu-id="8a42b-124">Volvamos al ejemplo y agreguemos un dato adicional al escenario.</span><span class="sxs-lookup"><span data-stu-id="8a42b-124">Let's take another look at this example and add one additional fact to the scenario.</span></span> <span data-ttu-id="8a42b-125">Desea promover un único campo, con un tamaño aproximado de 10 bytes, del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="8a42b-125">You want to promote a single field, approximately 10 bytes in size, from the original message.</span></span> <span data-ttu-id="8a42b-126">El tamaño máximo de un campo promovido es 256 caracteres, o aproximadamente 256 bytes (516 bytes si los caracteres son Unicode).</span><span class="sxs-lookup"><span data-stu-id="8a42b-126">The maximum size of a promoted field is 256 characters, or approximately 256 bytes (512 bytes if the characters are Unicode).</span></span>  
  
 <span data-ttu-id="8a42b-127">Con este dato adicional, la ecuación produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8a42b-127">With this additional fact, the equation now appears as follows:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 <span data-ttu-id="8a42b-128">Si quisiera promover un campo adicional cuyo tamaño fuese superior a 10 bytes, la ecuación sería la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a42b-128">If you wanted to promote an additional field that is 10 bytes in size, the equation would be:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 <span data-ttu-id="8a42b-129">Como puede ver, si promociona una sola propiedad de 10 bytes en este escenario, agregará 333,79 MB (0,33 GB) adicionales por año al tamaño de la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8a42b-129">As you can see, if you promote a single 10-byte property in this scenario, it will add an additional 333.79 MB ~ 0.33 GB per year to the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="8a42b-130">Promocionar dos propiedades de 10 bytes agregará 667,58 MB (0,65 GB) de espacio adicional por año al tamaño de la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8a42b-130">Promoting two 10-byte properties will add an additional 667.58 MB ~ 0.65 GB of additional space per year to the size of the BizTalk Tracking database.</span></span>  
  
## <a name="messages-with-message-body-tracking-activated"></a><span data-ttu-id="8a42b-131">Mensajes con seguimiento del cuerpo de los mensajes activado</span><span class="sxs-lookup"><span data-stu-id="8a42b-131">Messages with message body tracking activated</span></span>  
 <span data-ttu-id="8a42b-132">En este ejemplo, supongamos además que planeamos activar el seguimiento del cuerpo de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8a42b-132">In this example, let us also assume that we are planning on activating message body tracking.</span></span> <span data-ttu-id="8a42b-133">Tendremos que agregar la segunda ecuación para el seguimiento de mensajes de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="8a42b-133">We will need to add the second equation for message tracking, shown in the previous section.</span></span> <span data-ttu-id="8a42b-134">Para este ejemplo, la ecuación tendrá el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="8a42b-134">The equation will look like the following for this example:</span></span>  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 <span data-ttu-id="8a42b-135">Sumar los resultados de las dos ecuaciones permite estimar que la base de datos de seguimiento de BizTalk aumentará, aproximadamente, de 54,48 GB a 54,88 GB por año.</span><span class="sxs-lookup"><span data-stu-id="8a42b-135">By adding the results of the two equations, we can estimate that the BizTalk Tracking database will grow approximately 54.48 GB to 54.88 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a42b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a42b-136">See Also</span></span>  
 <span data-ttu-id="8a42b-137">[Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="8a42b-137">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="8a42b-138">[Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="8a42b-138">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="8a42b-139">[Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="8a42b-139">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="8a42b-140">[Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8a42b-140">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="8a42b-141">Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="8a42b-141">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)