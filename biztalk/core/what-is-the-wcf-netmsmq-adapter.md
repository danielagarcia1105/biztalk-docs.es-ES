---
title: "¿Qué es el adaptador de WCF-NetMsmq? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1008cc7178c38532f1781890080eacf4b5dfb56c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a><span data-ttu-id="7abea-103">¿Qué es el adaptador de WCF-NetMsmq?</span><span class="sxs-lookup"><span data-stu-id="7abea-103">What Is the WCF-NetMsmq Adapter?</span></span>
<span data-ttu-id="7abea-104">El adaptador de WCF-NetMsmq proporciona comunicaciones entre equipos desconectados mediante tecnología de cola en un entorno donde tanto los servicios como los clientes están basados en WCF.</span><span class="sxs-lookup"><span data-stu-id="7abea-104">The WCF-NetMsmq adapter provides disconnected cross-computer communication by using queuing technology in an environment where both the services and clients are WCF based.</span></span> <span data-ttu-id="7abea-105">Utiliza el transporte de Message Queue Server (MSMQ) y los mensajes tienen codificación binaria.</span><span class="sxs-lookup"><span data-stu-id="7abea-105">It uses the Message Queuing (MSMQ) transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="7abea-106">La siguiente tabla resume las características del adaptador de WCF-NetMsmq.</span><span class="sxs-lookup"><span data-stu-id="7abea-106">The following table summarizes the characteristics for the WCF-NetMsmq adapter.</span></span>  
  
|<span data-ttu-id="7abea-107">Description</span><span class="sxs-lookup"><span data-stu-id="7abea-107">Description</span></span>|<span data-ttu-id="7abea-108">Característica</span><span class="sxs-lookup"><span data-stu-id="7abea-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="7abea-109">Nivel de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="7abea-109">Interoperability level</span></span>|<span data-ttu-id="7abea-110">Perfil de .NET</span><span class="sxs-lookup"><span data-stu-id="7abea-110">.NET-Profile</span></span>|  
|<span data-ttu-id="7abea-111">Codificación de mensaje</span><span class="sxs-lookup"><span data-stu-id="7abea-111">Message encoding</span></span>|<span data-ttu-id="7abea-112">Binario</span><span class="sxs-lookup"><span data-stu-id="7abea-112">Binary</span></span>|  
|<span data-ttu-id="7abea-113">Límite</span><span class="sxs-lookup"><span data-stu-id="7abea-113">Boundary</span></span>|<span data-ttu-id="7abea-114">Entre equipos</span><span class="sxs-lookup"><span data-stu-id="7abea-114">Cross-computer</span></span>|  
|<span data-ttu-id="7abea-115">Protocolo de transporte</span><span class="sxs-lookup"><span data-stu-id="7abea-115">Transport protocol</span></span>|<span data-ttu-id="7abea-116">MSMQ</span><span class="sxs-lookup"><span data-stu-id="7abea-116">MSMQ</span></span>|  
|<span data-ttu-id="7abea-117">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="7abea-117">Security mode</span></span>|<span data-ttu-id="7abea-118">Ninguno, Mensaje, Transporte y Ambos.</span><span class="sxs-lookup"><span data-stu-id="7abea-118">None, Message, Transport, and Both.</span></span>|  
|<span data-ttu-id="7abea-119">Mecanismo de autenticación de cliente</span><span class="sxs-lookup"><span data-stu-id="7abea-119">Client authentication mechanism</span></span>|<span data-ttu-id="7abea-120">Seguridad de transporte y seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="7abea-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="7abea-121">Compatibilidad con WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="7abea-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="7abea-122">No aplicable</span><span class="sxs-lookup"><span data-stu-id="7abea-122">Not applicable</span></span>|  
|<span data-ttu-id="7abea-123">Compatibilidad con WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="7abea-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="7abea-124">Sí</span><span class="sxs-lookup"><span data-stu-id="7abea-124">Yes</span></span>|  
|<span data-ttu-id="7abea-125">Compatibilidad con mensajería unidireccional</span><span class="sxs-lookup"><span data-stu-id="7abea-125">Support for one-way messaging</span></span>|<span data-ttu-id="7abea-126">Sí</span><span class="sxs-lookup"><span data-stu-id="7abea-126">Yes</span></span>|  
|<span data-ttu-id="7abea-127">Compatibilidad con mensajería bidireccional</span><span class="sxs-lookup"><span data-stu-id="7abea-127">Support for two-way messaging</span></span>|<span data-ttu-id="7abea-128">No</span><span class="sxs-lookup"><span data-stu-id="7abea-128">No</span></span>|  
|<span data-ttu-id="7abea-129">Tipo de host para adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="7abea-129">Host type for receive adapter</span></span>|<span data-ttu-id="7abea-130">En curso</span><span class="sxs-lookup"><span data-stu-id="7abea-130">In-process</span></span>|  
|<span data-ttu-id="7abea-131">Tipo de host para adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="7abea-131">Host type for send adapter</span></span>|<span data-ttu-id="7abea-132">En curso</span><span class="sxs-lookup"><span data-stu-id="7abea-132">In-process</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7abea-133">Se deben crear por adelantado las colas de las que el adaptador de recepción WCF-NetMsmq extrae los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7abea-133">The queues from which the WCF-NetMsmq receive adapter pulls messages must be created in advance.</span></span> <span data-ttu-id="7abea-134">Los mensajes de las colas se deben basar en WCF. De lo contrario, estos mensajes se enviarán a la cola de mensajes con problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="7abea-134">The messages in the queues must be WCF based; otherwise, these messages will be sent to the dead-letter queue.</span></span>  
  
 <span data-ttu-id="7abea-135">El adaptador de WCF-NetMsmq se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="7abea-135">The WCF-NetMsmq adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="7abea-136">**Adaptador de recepción de WCF-NetMsmq**</span><span class="sxs-lookup"><span data-stu-id="7abea-136">**WCF-NetMsmq Receive Adapter**</span></span>  
  
 <span data-ttu-id="7abea-137">Utilice el adaptador de recepción WCF-NetMsmq para recibir solicitudes de Servicio WCF mediante MSMQ.</span><span class="sxs-lookup"><span data-stu-id="7abea-137">You use the WCF-NetMsmq receive adapter to receive WCF service requests over MSMQ.</span></span> <span data-ttu-id="7abea-138">Una ubicación de recepción que utiliza el adaptador de recepción WCF-NetMsmq sólo se puede configurar como recepción unidireccional.</span><span class="sxs-lookup"><span data-stu-id="7abea-138">A receive location that uses the WCF-NetMsmq receive adapter can only be configured as one-way receive.</span></span>  
  
 <span data-ttu-id="7abea-139">**Adaptador de envío WCF-NetMsmq**</span><span class="sxs-lookup"><span data-stu-id="7abea-139">**WCF-NetMsmq Send Adapter**</span></span>  
  
 <span data-ttu-id="7abea-140">Utilice el adaptador de envío WCF-NetMsmq para llamar a un Servicio WCF a través del contrato sin tipo mediante MSMQ.</span><span class="sxs-lookup"><span data-stu-id="7abea-140">You use the WCF-NetMsmq send adapter to call a WCF service through the typeless contract over MSMQ.</span></span>  
  
 <span data-ttu-id="7abea-141">Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="7abea-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abea-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="7abea-142">See Also</span></span>  
 <span data-ttu-id="7abea-143">[Configurar el adaptador de WCF-NetMsmq](../core/configuring-the-wcf-netmsmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7abea-143">[Configuring the WCF-NetMsmq Adapter](../core/configuring-the-wcf-netmsmq-adapter.md) </span></span>  
 [<span data-ttu-id="7abea-144">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="7abea-144">WCF Adapters</span></span>](../core/wcf-adapters.md)