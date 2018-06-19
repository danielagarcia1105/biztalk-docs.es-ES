---
title: ¿Qué es el adaptador de WCF-NetTcp? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, about WCF-NetTcp adapters
ms.assetid: 94dc24df-19a1-4701-9012-59d05b0c8abd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741d3a4d7b7bcc80405d0fc25e37a31860523b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289412"
---
# <a name="what-is-the-wcf-nettcp-adapter"></a><span data-ttu-id="5b750-103">¿Qué es el adaptador de WCF-NetTcp?</span><span class="sxs-lookup"><span data-stu-id="5b750-103">What Is the WCF-NetTcp Adapter?</span></span>
<span data-ttu-id="5b750-104">El adaptador de WCF-NetTcp proporciona comunicación entre procesos o entre equipos conectados en el mismo equipo en un entorno en el que servicios y clientes se basan en WCF.</span><span class="sxs-lookup"><span data-stu-id="5b750-104">The WCF-NetTcp adapter provides connected cross-computer or cross-process communication in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="5b750-105">Proporciona acceso completo a características de confiabilidad, seguridad y transacciones de SOAP.</span><span class="sxs-lookup"><span data-stu-id="5b750-105">It provides full access to SOAP security, reliability, and transaction features.</span></span> <span data-ttu-id="5b750-106">Este adaptador usa el transporte TCP y los mensajes tienen una codificación binaria.</span><span class="sxs-lookup"><span data-stu-id="5b750-106">This adapter uses the TCP transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="5b750-107">La siguiente tabla resume las características del adaptador de WCF-NetTcp.</span><span class="sxs-lookup"><span data-stu-id="5b750-107">The following table summarizes the characteristics of the WCF-NetTcp adapter.</span></span>  
  
|<span data-ttu-id="5b750-108">Description</span><span class="sxs-lookup"><span data-stu-id="5b750-108">Description</span></span>|<span data-ttu-id="5b750-109">Característica</span><span class="sxs-lookup"><span data-stu-id="5b750-109">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="5b750-110">Nivel de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="5b750-110">Interoperability level</span></span>|<span data-ttu-id="5b750-111">Perfil de .NET</span><span class="sxs-lookup"><span data-stu-id="5b750-111">.NET-Profile</span></span>|  
|<span data-ttu-id="5b750-112">Codificación de mensaje</span><span class="sxs-lookup"><span data-stu-id="5b750-112">Message encoding</span></span>|<span data-ttu-id="5b750-113">Binario</span><span class="sxs-lookup"><span data-stu-id="5b750-113">Binary</span></span>|  
|<span data-ttu-id="5b750-114">Límite</span><span class="sxs-lookup"><span data-stu-id="5b750-114">Boundary</span></span>|<span data-ttu-id="5b750-115">Entre equipos o entre procesos</span><span class="sxs-lookup"><span data-stu-id="5b750-115">Cross-computer or cross-process</span></span>|  
|<span data-ttu-id="5b750-116">Protocolo de transporte</span><span class="sxs-lookup"><span data-stu-id="5b750-116">Transport protocol</span></span>|<span data-ttu-id="5b750-117">TCP</span><span class="sxs-lookup"><span data-stu-id="5b750-117">TCP</span></span>|  
|<span data-ttu-id="5b750-118">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="5b750-118">Security mode</span></span>|<span data-ttu-id="5b750-119">Ninguno, Mensaje, Transporte y TransportWithMessageCredential.</span><span class="sxs-lookup"><span data-stu-id="5b750-119">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="5b750-120">Mecanismo de autenticación de cliente</span><span class="sxs-lookup"><span data-stu-id="5b750-120">Client authentication mechanism</span></span>|<span data-ttu-id="5b750-121">Seguridad de transporte y seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="5b750-121">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="5b750-122">Compatibilidad con WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="5b750-122">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="5b750-123">No</span><span class="sxs-lookup"><span data-stu-id="5b750-123">No</span></span>|  
|<span data-ttu-id="5b750-124">Compatibilidad con WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="5b750-124">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="5b750-125">Sí</span><span class="sxs-lookup"><span data-stu-id="5b750-125">Yes</span></span>|  
|<span data-ttu-id="5b750-126">Compatibilidad con mensajería unidireccional</span><span class="sxs-lookup"><span data-stu-id="5b750-126">Support for one-way messaging</span></span>|<span data-ttu-id="5b750-127">Sí</span><span class="sxs-lookup"><span data-stu-id="5b750-127">Yes</span></span>|  
|<span data-ttu-id="5b750-128">Compatibilidad con mensajería bidireccional</span><span class="sxs-lookup"><span data-stu-id="5b750-128">Support for two-way messaging</span></span>|<span data-ttu-id="5b750-129">Sí</span><span class="sxs-lookup"><span data-stu-id="5b750-129">Yes</span></span>|  
|<span data-ttu-id="5b750-130">Tipo de host para adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="5b750-130">Host type for receive adapter</span></span>|<span data-ttu-id="5b750-131">En curso</span><span class="sxs-lookup"><span data-stu-id="5b750-131">In-process</span></span>|  
|<span data-ttu-id="5b750-132">Tipo de host para adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="5b750-132">Host type for send adapter</span></span>|<span data-ttu-id="5b750-133">En curso</span><span class="sxs-lookup"><span data-stu-id="5b750-133">In-process</span></span>|  
  
 <span data-ttu-id="5b750-134">El adaptador de WCF-NetTcp se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="5b750-134">The WCF-NetTcp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="5b750-135">**Adaptador de recepción de WCF-NetTcp**</span><span class="sxs-lookup"><span data-stu-id="5b750-135">**WCF-NetTcp Receive Adapter**</span></span>  
  
 <span data-ttu-id="5b750-136">Utilice el adaptador de recepción WCF-NetTcp para recibir solicitudes de servicio a través del protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="5b750-136">You use the WCF-NetTcp receive adapter to receive WCF service requests through the TCP protocol.</span></span> <span data-ttu-id="5b750-137">Una ubicación de recepción que usa el adaptador de recepción WCF-NetTcp se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="5b750-137">A receive location that uses the WCF-NetTcp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="5b750-138">**Adaptador de envío WCF-NetTcp**</span><span class="sxs-lookup"><span data-stu-id="5b750-138">**WCF-NetTcp Send Adapter**</span></span>  
  
 <span data-ttu-id="5b750-139">Utilice el adaptador de envío WCF-NetTcp para llamar a un Servicio WCF a través del contrato sin tipo mediante el protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="5b750-139">You use the WCF-NetTcp send adapter to call a WCF service through the typeless contract by using the TCP protocol.</span></span>  
  
 <span data-ttu-id="5b750-140">Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="5b750-140">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b750-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b750-141">See Also</span></span>  
 <span data-ttu-id="5b750-142">[Configurar el adaptador de WCF-NetTcp](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5b750-142">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="5b750-143">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="5b750-143">WCF Adapters</span></span>](../core/wcf-adapters.md)