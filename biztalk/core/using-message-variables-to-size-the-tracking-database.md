---
title: Uso de Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message variables [Tracking database], CMsgs
- message variables [Tracking database], Events
- message variables [Tracking database], Properties
- Tracking database, database size
- message variables [Tracking database], Nserv
- message variables [Tracking database], Msgs
- message variables [Tracking database], PropSize
- message variables [Tracking database]
- message variables [Tracking database], MsgSize
- message variables [Tracking database], MsgNum
- Tracking database, messages
ms.assetid: 2d31ae25-3d16-4002-b5a5-dca25e764ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ef731d12155ae20d7f78aaaf4a5f990b76affba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985685"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a><span data-ttu-id="9c748-102">Usar variables de mensaje para determinar el tamaño de la base de datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9c748-102">Using Message Variables to Size the Tracking Database</span></span>
<span data-ttu-id="9c748-103">En Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede utilizar una serie de variables para determinar el tamaño que alcanzará la base de datos de seguimiento de BizTalk (BizTalkDTADb) durante un determinado período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="9c748-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use a number of variables to determine how large the BizTalk Tracking (BizTalkDTADb) database will become over a given period of time.</span></span> <span data-ttu-id="9c748-104">Estas variables son:</span><span class="sxs-lookup"><span data-stu-id="9c748-104">These variables are:</span></span>  
  
- <span data-ttu-id="9c748-105">Número de canalizaciones utilizadas</span><span class="sxs-lookup"><span data-stu-id="9c748-105">Number of pipelines used</span></span>  
  
- <span data-ttu-id="9c748-106">Número de orquestaciones empleadas</span><span class="sxs-lookup"><span data-stu-id="9c748-106">Number of orchestrations involved</span></span>  
  
- <span data-ttu-id="9c748-107">Número de eventos generados</span><span class="sxs-lookup"><span data-stu-id="9c748-107">Number of events generated</span></span>  
  
- <span data-ttu-id="9c748-108">Número de propiedades de mensaje sometidas a seguimiento</span><span class="sxs-lookup"><span data-stu-id="9c748-108">Number of message properties tracked</span></span>  
  
- <span data-ttu-id="9c748-109">Número de mensajes adicionales creados</span><span class="sxs-lookup"><span data-stu-id="9c748-109">Number of additional messages created</span></span>  
  
- <span data-ttu-id="9c748-110">Estimación del número de mensajes recibidos en el margen de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="9c748-110">Estimated number of messages received in the specified timeframe</span></span>  
  
  <span data-ttu-id="9c748-111">Aunque la ecuación que se utiliza para estimar el tamaño de la base de datos de seguimiento de BizTalk es sencilla, deberá aplicarla a todos los procesos de mensajes entrantes y salientes que utilicen la implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9c748-111">While the equation you use to estimate the size of the BizTalk Tracking database is straightforward, you must apply it to each incoming and outgoing message process that uses the BizTalk Server implementation.</span></span> <span data-ttu-id="9c748-112">Es decir, tendrá que aplicar esta ecuación a cada escenario de mensajes distinto y sumar los resultados para obtener el tamaño de base de datos final estimado.</span><span class="sxs-lookup"><span data-stu-id="9c748-112">In other words, you will need to apply this equation for every distinct message scenario and then add up the results to obtain the final estimated database size.</span></span> <span data-ttu-id="9c748-113">En este documento, analizaremos dos escenarios.</span><span class="sxs-lookup"><span data-stu-id="9c748-113">In this document we will look at two scenarios.</span></span> <span data-ttu-id="9c748-114">Estos escenarios son:</span><span class="sxs-lookup"><span data-stu-id="9c748-114">The scenarios are:</span></span>  
  
1. <span data-ttu-id="9c748-115">Recibir un mensaje, transformarlo y enviar el mensaje resultante.</span><span class="sxs-lookup"><span data-stu-id="9c748-115">Receiving a message, transforming the message, and then sending the resulting message</span></span>  
  
2. <span data-ttu-id="9c748-116">Recibir un mensaje, ejecutar un proceso empresarial usando el mensaje y enviar el mensaje resultante.</span><span class="sxs-lookup"><span data-stu-id="9c748-116">Receiving a message, running a business process using the message, and then sending the resulting message.</span></span>  
  
   <span data-ttu-id="9c748-117">Puede que ambos escenarios estén presentes en una misma instalación de BizTalk Server y que cada uno de ellos genere un volumen de datos de seguimiento diferente.</span><span class="sxs-lookup"><span data-stu-id="9c748-117">Both of these scenarios may be present in a BizTalk Server installation, and each scenario generates a different amount of tracking data.</span></span> <span data-ttu-id="9c748-118">El total de datos de seguimiento generados en la instalación de BizTalk Server es la suma de todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="9c748-118">The total tracking data generated for the BizTalk Server installation is the sum of all the scenarios.</span></span>  
  
   <span data-ttu-id="9c748-119">Éstas son algunas de las variables que se utilizan en la ecuación:</span><span class="sxs-lookup"><span data-stu-id="9c748-119">The following are some variables used in the equation:</span></span>  
  
|<span data-ttu-id="9c748-120">Variable</span><span class="sxs-lookup"><span data-stu-id="9c748-120">Variable</span></span>|<span data-ttu-id="9c748-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c748-121">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="9c748-122">**Nserv**</span><span class="sxs-lookup"><span data-stu-id="9c748-122">**Nserv**</span></span>|<span data-ttu-id="9c748-123">Número de servicios (número de canalizaciones + número de orquestaciones)</span><span class="sxs-lookup"><span data-stu-id="9c748-123">Number of services (number of pipelines + number of orchestrations)</span></span>|  
|<span data-ttu-id="9c748-124">**Eventos**</span><span class="sxs-lookup"><span data-stu-id="9c748-124">**Events**</span></span>|<span data-ttu-id="9c748-125">Número de eventos de mensaje generados</span><span class="sxs-lookup"><span data-stu-id="9c748-125">Number of generated message events</span></span>|  
|<span data-ttu-id="9c748-126">**Propiedades**</span><span class="sxs-lookup"><span data-stu-id="9c748-126">**Properties**</span></span>|<span data-ttu-id="9c748-127">Número de propiedades de mensaje sometidas a seguimiento</span><span class="sxs-lookup"><span data-stu-id="9c748-127">Number of message properties tracked</span></span>|  
|<span data-ttu-id="9c748-128">**PropSize**</span><span class="sxs-lookup"><span data-stu-id="9c748-128">**PropSize**</span></span>|<span data-ttu-id="9c748-129">Tamaño (en bytes) de la propiedad promovida (campo)</span><span class="sxs-lookup"><span data-stu-id="9c748-129">Size (in bytes) of the promoted property (field)</span></span>|  
|<span data-ttu-id="9c748-130">**CMsgs**</span><span class="sxs-lookup"><span data-stu-id="9c748-130">**CMsgs**</span></span>|<span data-ttu-id="9c748-131">Número de mensajes adicionales creados por cada mensaje entrante</span><span class="sxs-lookup"><span data-stu-id="9c748-131">Number of additional messages created per incoming message</span></span>|  
|<span data-ttu-id="9c748-132">**Mens.**</span><span class="sxs-lookup"><span data-stu-id="9c748-132">**Msgs**</span></span>|<span data-ttu-id="9c748-133">Estimación del número de mensajes entrantes en un período determinado</span><span class="sxs-lookup"><span data-stu-id="9c748-133">Number of estimated incoming messages in a given time period</span></span>|  
|<span data-ttu-id="9c748-134">**MsgSize**</span><span class="sxs-lookup"><span data-stu-id="9c748-134">**MsgSize**</span></span>|<span data-ttu-id="9c748-135">Tamaño del mensaje</span><span class="sxs-lookup"><span data-stu-id="9c748-135">Message size</span></span>|  
|<span data-ttu-id="9c748-136">**MsgNum**</span><span class="sxs-lookup"><span data-stu-id="9c748-136">**MsgNum**</span></span>|<span data-ttu-id="9c748-137">Número de mensajes sometidos a seguimiento por cada mensaje entrante</span><span class="sxs-lookup"><span data-stu-id="9c748-137">Number of messages tracked for each incoming message</span></span>|  
  
 <span data-ttu-id="9c748-138">La ecuación es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c748-138">The equation is as follows:</span></span>  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 <span data-ttu-id="9c748-139">Esta ecuación calcula únicamente los datos de seguimiento que generan los mensajes, no incluye los que se generan para el Depurador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="9c748-139">This equation calculates only the tracking data generated by the messages and does not include the tracking data generated for the Orchestration Debugger.</span></span> <span data-ttu-id="9c748-140">Debe aplicar esta fórmula a cada proceso de mensaje para estimar el tamaño de la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c748-140">You must apply this formula to each message process to estimate the size of the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c748-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c748-141">See Also</span></span>  
 <span data-ttu-id="9c748-142">[Ajustar el tamaño de la base de datos de seguimiento para realizar un seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="9c748-142">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="9c748-143">[Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9c748-143">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="9c748-144">[Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes en orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="9c748-144">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="9c748-145">[Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9c748-145">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="9c748-146">Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="9c748-146">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)