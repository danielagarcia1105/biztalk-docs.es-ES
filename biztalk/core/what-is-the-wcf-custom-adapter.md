---
title: "¿Qué es el adaptador de WCF-Custom? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e090f82bc43d96dc14295af2fac2807cf1fd137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-custom-adapter"></a><span data-ttu-id="02b0a-103">¿Qué es el adaptador de WCF-Custom?</span><span class="sxs-lookup"><span data-stu-id="02b0a-103">What Is the WCF-Custom Adapter?</span></span>
<span data-ttu-id="02b0a-104">El adaptador de WCF-Custom se utiliza para habilitar el uso de los componentes de extensibilidad de WCF en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="02b0a-104">The WCF-Custom adapter is used to enable the use of WCF extensibility components in BizTalk Server.</span></span> <span data-ttu-id="02b0a-105">El adaptador habilita una flexibilidad completa del marco de trabajo de WCF.</span><span class="sxs-lookup"><span data-stu-id="02b0a-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="02b0a-106">Permite a los usuarios seleccionar y configurar un enlace de WCF para la ubicación de recepción y el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="02b0a-106">It allows users to select and configure a WCF binding for the receive location and send port.</span></span> <span data-ttu-id="02b0a-107">También permite a los usuarios configurar los comportamientos de los extremos y las configuraciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="02b0a-107">It also allows users to set the endpoint behaviors and security settings.</span></span>  
  
 <span data-ttu-id="02b0a-108">El adaptador de WCF-Custom se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="02b0a-108">The WCF-Custom adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="02b0a-109">**Adaptador de recepción de WCF-Custom**</span><span class="sxs-lookup"><span data-stu-id="02b0a-109">**WCF-Custom Receive Adapter**</span></span>  
  
 <span data-ttu-id="02b0a-110">El adaptador de recepción WCF-Custom se usa para recibir solicitudes de servicio de WCF a través de los enlaces, el comportamiento de servicio, el mecanismo de seguridad y el origen del cuerpo del mensaje entrante que seleccionó y configuró en el cuadro de diálogo de las propiedades de transporte de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="02b0a-110">You use the WCF-Custom receive adapter to receive WCF service requests through the bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured in the transport properties dialog in the receive location.</span></span> <span data-ttu-id="02b0a-111">Una ubicación de recepción que usa el adaptador de recepción WCF-Custom se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="02b0a-111">A receive location that uses the WCF-Custom receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="02b0a-112">**Adaptador de envío WCF-Custom**</span><span class="sxs-lookup"><span data-stu-id="02b0a-112">**WCF-Custom Send Adapter**</span></span>  
  
 <span data-ttu-id="02b0a-113">El adaptador de envío de WCF-Custom se usa para llamar a un servicio de WCF a través del contrato sin tipos con los enlaces y el comportamiento de servicio, el mecanismo de seguridad y el origen del cuerpo del mensaje saliente que seleccionó y configuró.</span><span class="sxs-lookup"><span data-stu-id="02b0a-113">You use the WCF-Custom send adapter to call a WCF service through the typeless contract with the bindings, service behavior, endpoint behavior, security mechanism, and the source of the outbound message body that you selected and configured.</span></span>  
  
 <span data-ttu-id="02b0a-114">Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="02b0a-114">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b0a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="02b0a-115">See Also</span></span>  
 <span data-ttu-id="02b0a-116">[Configurar el adaptador de WCF-Custom](../core/configuring-the-wcf-custom-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="02b0a-116">[Configuring the WCF-Custom Adapter](../core/configuring-the-wcf-custom-adapter.md) </span></span>  
 [<span data-ttu-id="02b0a-117">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="02b0a-117">WCF Adapters</span></span>](../core/wcf-adapters.md)