---
title: "¿Qué es el adaptador de WCF-WSHttp? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-WSHttp adapters, about WCF-WSHttp adapters
ms.assetid: 183a19e3-10b1-403f-b274-34a441e774d1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5d244dcfe26cf10bc4ae10c63374eef0824444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-wshttp-adapter"></a><span data-ttu-id="f37f5-103">¿Qué es el adaptador de WCF-WSHttp?</span><span class="sxs-lookup"><span data-stu-id="f37f5-103">What Is the WCF-WSHttp Adapter?</span></span>
<span data-ttu-id="f37f5-104">Puede usar el adaptador de WCF-WSHttp para realizar una comunicación entre equipos con servicios y clientes que puedan comprender los estándares de servicios Web de próxima generación mediante los transportes HTTP o HTTPS con texto o la codificación Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="f37f5-104">You can use the WCF-WSHttp adapter to do cross-computer communication with services and clients that can understand the next-generation Web service standards, using either the HTTP or HTTPS transport with text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="f37f5-105">El adaptador de WCF-WSHtt proporciona acceso completo a características de confiabilidad, seguridad y transacciones de SOAP.</span><span class="sxs-lookup"><span data-stu-id="f37f5-105">The WCF-WSHttp adapter provides full access to the SOAP security, reliability, and transaction features.</span></span>  
  
 <span data-ttu-id="f37f5-106">La siguiente tabla resume las características del adaptador de WCF-WSHttp.</span><span class="sxs-lookup"><span data-stu-id="f37f5-106">The following table summarizes the characteristics of the WCF-WSHttp adapter.</span></span>  
  
|<span data-ttu-id="f37f5-107">Description</span><span class="sxs-lookup"><span data-stu-id="f37f5-107">Description</span></span>|<span data-ttu-id="f37f5-108">Característica</span><span class="sxs-lookup"><span data-stu-id="f37f5-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="f37f5-109">Nivel de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="f37f5-109">Interoperability level</span></span>|<span data-ttu-id="f37f5-110">Perfil de servicios Web WS</span><span class="sxs-lookup"><span data-stu-id="f37f5-110">WS-Profile</span></span>|  
|<span data-ttu-id="f37f5-111">Codificación de mensaje</span><span class="sxs-lookup"><span data-stu-id="f37f5-111">Message encoding</span></span>|<span data-ttu-id="f37f5-112">Texto o MTOM</span><span class="sxs-lookup"><span data-stu-id="f37f5-112">Text or MTOM</span></span>|  
|<span data-ttu-id="f37f5-113">Límite</span><span class="sxs-lookup"><span data-stu-id="f37f5-113">Boundary</span></span>|<span data-ttu-id="f37f5-114">Entre equipos</span><span class="sxs-lookup"><span data-stu-id="f37f5-114">Cross-computer</span></span>|  
|<span data-ttu-id="f37f5-115">Protocolo de transporte</span><span class="sxs-lookup"><span data-stu-id="f37f5-115">Transport protocol</span></span>|<span data-ttu-id="f37f5-116">HTTP o HTTPS</span><span class="sxs-lookup"><span data-stu-id="f37f5-116">HTTP or HTTPS</span></span>|  
|<span data-ttu-id="f37f5-117">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="f37f5-117">Security mode</span></span>|<span data-ttu-id="f37f5-118">Ninguno, Mensaje, Transporte y TransportWithMessageCredential.</span><span class="sxs-lookup"><span data-stu-id="f37f5-118">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="f37f5-119">Mecanismo de autenticación de cliente</span><span class="sxs-lookup"><span data-stu-id="f37f5-119">Client authentication mechanism</span></span>|<span data-ttu-id="f37f5-120">Seguridad de transporte y seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="f37f5-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="f37f5-121">Compatibilidad con WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="f37f5-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="f37f5-122">No</span><span class="sxs-lookup"><span data-stu-id="f37f5-122">No</span></span>|  
|<span data-ttu-id="f37f5-123">Compatibilidad con WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="f37f5-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="f37f5-124">Sí</span><span class="sxs-lookup"><span data-stu-id="f37f5-124">Yes</span></span>|  
|<span data-ttu-id="f37f5-125">Compatibilidad con mensajería unidireccional</span><span class="sxs-lookup"><span data-stu-id="f37f5-125">Support for one-way messaging</span></span>|<span data-ttu-id="f37f5-126">Sí</span><span class="sxs-lookup"><span data-stu-id="f37f5-126">Yes</span></span>|  
|<span data-ttu-id="f37f5-127">Compatibilidad con mensajería bidireccional</span><span class="sxs-lookup"><span data-stu-id="f37f5-127">Support for two-way messaging</span></span>|<span data-ttu-id="f37f5-128">Sí</span><span class="sxs-lookup"><span data-stu-id="f37f5-128">Yes</span></span>|  
|<span data-ttu-id="f37f5-129">Tipo de host para adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="f37f5-129">Host type for receive adapter</span></span>|<span data-ttu-id="f37f5-130">Aislado</span><span class="sxs-lookup"><span data-stu-id="f37f5-130">Isolated</span></span>|  
|<span data-ttu-id="f37f5-131">Tipo de host para adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="f37f5-131">Host type for send adapter</span></span>|<span data-ttu-id="f37f5-132">En curso</span><span class="sxs-lookup"><span data-stu-id="f37f5-132">In-process</span></span>|  
  
 <span data-ttu-id="f37f5-133">El adaptador de WCF-WSHttp se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="f37f5-133">The WCF-WSHttp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="f37f5-134">**Adaptador de recepción de WCF-WSHttp**</span><span class="sxs-lookup"><span data-stu-id="f37f5-134">**WCF-WSHttp Receive Adapter**</span></span>  
  
 <span data-ttu-id="f37f5-135">Utilice el adaptador de recepción WCF-WSHttp para recibir solicitudes de Servicio WCF a través del protocolo HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f37f5-135">You use the WCF-WSHttp receive adapter to receive WCF service requests through the HTTP or HTTPS protocol.</span></span> <span data-ttu-id="f37f5-136">Una ubicación de recepción que usa el adaptador de recepción WCF-WSHttp se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="f37f5-136">A receive location that uses the WCF-WSHttp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="f37f5-137">**Adaptador de envío WCF-WSHttp**</span><span class="sxs-lookup"><span data-stu-id="f37f5-137">**WCF-WSHttp Send Adapter**</span></span>  
  
 <span data-ttu-id="f37f5-138">Utilice el adaptador de envío WCF-WSHttp para llamar a un Servicio WCF a través del contrato sin tipo mediante el protocolo HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f37f5-138">You use the WCF-WSHttp send adapter to call a WCF service through the typeless contract by using the HTTP or HTTPS protocol.</span></span>  
  
 <span data-ttu-id="f37f5-139">Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="f37f5-139">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f37f5-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f37f5-140">See Also</span></span>  
 <span data-ttu-id="f37f5-141">[Configurar el adaptador de WCF-WSHttp](../core/configuring-the-wcf-wshttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f37f5-141">[Configuring the WCF-WSHttp Adapter](../core/configuring-the-wcf-wshttp-adapter.md) </span></span>  
 [<span data-ttu-id="f37f5-142">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="f37f5-142">WCF Adapters</span></span>](../core/wcf-adapters.md)