---
title: ¿Qué es el adaptador de WCF-NetNamedPipe? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, about WCF-NetNamedPipe adapters
ms.assetid: b9f84256-e49d-4ee2-b0fa-d3f692ade1d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c73a670139690c4a27d4784c6ad23225492f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289252"
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a><span data-ttu-id="b12a6-103">¿Qué es el adaptador de WCF-NetNamedPipe?</span><span class="sxs-lookup"><span data-stu-id="b12a6-103">What Is the WCF-NetNamedPipe Adapter?</span></span>
<span data-ttu-id="b12a6-104">El adaptador de WCF-NetNamedPipe proporciona comunicación entre procesos en el mismo equipo en un entorno en el que servicios y clientes se basan en WCF.</span><span class="sxs-lookup"><span data-stu-id="b12a6-104">The WCF-NetNamedPipe adapter provides cross-process communication on the same computer in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="b12a6-105">Proporciona acceso completo a características de confiabilidad y transacciones de SOAP.</span><span class="sxs-lookup"><span data-stu-id="b12a6-105">It provides full access to SOAP reliability and transaction features.</span></span> <span data-ttu-id="b12a6-106">El adaptador usa el transporte de canalización mencionado y los mensajes tienen una codificación binaria.</span><span class="sxs-lookup"><span data-stu-id="b12a6-106">The adapter uses the named pipe transport, and messages have binary encoding.</span></span> <span data-ttu-id="b12a6-107">Este adaptador no se puede usar en comunicaciones entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b12a6-107">This adapter cannot be used in cross-computer communication.</span></span>  
  
 <span data-ttu-id="b12a6-108">La siguiente tabla resume las características del adaptador de WCF-NetNamedPipe.</span><span class="sxs-lookup"><span data-stu-id="b12a6-108">The following table summarizes the characteristics for the WCF-NetNamedPipe adapter.</span></span>  
  
|<span data-ttu-id="b12a6-109">Description</span><span class="sxs-lookup"><span data-stu-id="b12a6-109">Description</span></span>|<span data-ttu-id="b12a6-110">Característica</span><span class="sxs-lookup"><span data-stu-id="b12a6-110">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="b12a6-111">Nivel de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="b12a6-111">Interoperability level</span></span>|<span data-ttu-id="b12a6-112">Perfil de .NET</span><span class="sxs-lookup"><span data-stu-id="b12a6-112">.NET-Profile</span></span>|  
|<span data-ttu-id="b12a6-113">Codificación de mensaje</span><span class="sxs-lookup"><span data-stu-id="b12a6-113">Message encoding</span></span>|<span data-ttu-id="b12a6-114">Binario</span><span class="sxs-lookup"><span data-stu-id="b12a6-114">Binary</span></span>|  
|<span data-ttu-id="b12a6-115">Límite</span><span class="sxs-lookup"><span data-stu-id="b12a6-115">Boundary</span></span>|<span data-ttu-id="b12a6-116">Entre procesos</span><span class="sxs-lookup"><span data-stu-id="b12a6-116">Cross-process</span></span>|  
|<span data-ttu-id="b12a6-117">Protocolo de transporte</span><span class="sxs-lookup"><span data-stu-id="b12a6-117">Transport protocol</span></span>|<span data-ttu-id="b12a6-118">Canalización con nombre</span><span class="sxs-lookup"><span data-stu-id="b12a6-118">Named pipe</span></span>|  
|<span data-ttu-id="b12a6-119">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="b12a6-119">Security mode</span></span>|<span data-ttu-id="b12a6-120">Ninguno y Transporte</span><span class="sxs-lookup"><span data-stu-id="b12a6-120">None and Transport</span></span>|  
|<span data-ttu-id="b12a6-121">Mecanismo de autenticación de cliente</span><span class="sxs-lookup"><span data-stu-id="b12a6-121">Client authentication mechanism</span></span>|<span data-ttu-id="b12a6-122">Seguridad de transporte y seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="b12a6-122">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="b12a6-123">Compatibilidad con WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="b12a6-123">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="b12a6-124">No</span><span class="sxs-lookup"><span data-stu-id="b12a6-124">No</span></span>|  
|<span data-ttu-id="b12a6-125">Compatibilidad con WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="b12a6-125">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="b12a6-126">Sí</span><span class="sxs-lookup"><span data-stu-id="b12a6-126">Yes</span></span>|  
|<span data-ttu-id="b12a6-127">Compatibilidad con mensajería unidireccional</span><span class="sxs-lookup"><span data-stu-id="b12a6-127">Support for one-way messaging</span></span>|<span data-ttu-id="b12a6-128">Sí</span><span class="sxs-lookup"><span data-stu-id="b12a6-128">Yes</span></span>|  
|<span data-ttu-id="b12a6-129">Compatibilidad con mensajería bidireccional</span><span class="sxs-lookup"><span data-stu-id="b12a6-129">Support for two-way messaging</span></span>|<span data-ttu-id="b12a6-130">Sí</span><span class="sxs-lookup"><span data-stu-id="b12a6-130">Yes</span></span>|  
|<span data-ttu-id="b12a6-131">Tipo de host para adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="b12a6-131">Host type for receive adapter</span></span>|<span data-ttu-id="b12a6-132">En curso</span><span class="sxs-lookup"><span data-stu-id="b12a6-132">In-process</span></span>|  
|<span data-ttu-id="b12a6-133">Tipo de host para adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="b12a6-133">Host type for send adapter</span></span>|<span data-ttu-id="b12a6-134">En curso</span><span class="sxs-lookup"><span data-stu-id="b12a6-134">In-process</span></span>|  
  
 <span data-ttu-id="b12a6-135">El adaptador de WCF-NetNamedPipe se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="b12a6-135">The WCF-NetNamedPipe adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="b12a6-136">**Adaptador de recepción de WCF-NetNamedPipe**</span><span class="sxs-lookup"><span data-stu-id="b12a6-136">**WCF-NetNamedPipe Receive Adapter**</span></span>  
  
 <span data-ttu-id="b12a6-137">Utilice el adaptador de recepción WCF-NetNamedPipe para recibir solicitudes de Servicio WCF a través del transporte de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="b12a6-137">You use the WCF-NetNamedPipe receive adapter to receive WCF service requests over the named pipe transport.</span></span> <span data-ttu-id="b12a6-138">Una ubicación de recepción que usa el adaptador de recepción WCF-NetNamedPipe se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="b12a6-138">A receive location that uses the WCF-NetNamedPipe receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="b12a6-139">**Adaptador de envío WCF-NetNamedPipe**</span><span class="sxs-lookup"><span data-stu-id="b12a6-139">**WCF-NetNamedPipe Send Adapter**</span></span>  
  
 <span data-ttu-id="b12a6-140">Utilice el adaptador de envío WCF-NetNamedPipe para llamar a un Servicio WCF mediante el contrato sin tipo a través del transporte de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="b12a6-140">You use the WCF-NetNamedPipe send adapter to call a WCF service through the typeless contract over the named pipe transport.</span></span>  
  
 <span data-ttu-id="b12a6-141">Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="b12a6-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12a6-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="b12a6-142">See Also</span></span>  
 <span data-ttu-id="b12a6-143">[Configurar el adaptador de WCF-NetNamedPipe](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b12a6-143">[Configuring the WCF-NetNamedPipe Adapter](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span></span>  
 [<span data-ttu-id="b12a6-144">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="b12a6-144">WCF Adapters</span></span>](../core/wcf-adapters.md)