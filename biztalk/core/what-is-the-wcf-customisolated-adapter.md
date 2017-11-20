---
title: "¿Qué es el adaptador de WCF-CustomIsolated? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-CustomIsolated adapters, about WCF-CustomIsolated adapters
ms.assetid: 872fe97a-8a96-4b2a-8cc1-2db9b315c44f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fdf5a646f586030df6c9492fc6fb2999e49527a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-customisolated-adapter"></a><span data-ttu-id="49fb6-103">¿Qué es el adaptador de WCF-CustomIsolated?</span><span class="sxs-lookup"><span data-stu-id="49fb6-103">What Is the WCF-CustomIsolated Adapter?</span></span>
<span data-ttu-id="49fb6-104">El adaptador de WCF-CustomIsolated se utiliza para habilitar el uso de los componentes de extensibilidad de WCF en BizTalk Server con un host aislado.</span><span class="sxs-lookup"><span data-stu-id="49fb6-104">The WCF-CustomIsolated adapter is used to enable the use of WCF extensibility components in BizTalk Server with an isolated host.</span></span> <span data-ttu-id="49fb6-105">El adaptador habilita una flexibilidad completa del marco de trabajo de WCF.</span><span class="sxs-lookup"><span data-stu-id="49fb6-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="49fb6-106">Permite a los usuarios seleccionar y configurar un enlace de WCF para la ubicación de recepción y especificar los comportamientos del extremo y la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="49fb6-106">It allows users to select and configure a WCF binding for the receive location, and to specify the endpoint behaviors and security settings.</span></span> <span data-ttu-id="49fb6-107">Este adaptador sólo pueden utilizarlo los transportes que estén alojados en Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="49fb6-107">This adapter can only be used by transports that are hosted in Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="49fb6-108">El adaptador de WCF-CustomIsolated se compone únicamente de un adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="49fb6-108">The WCF-CustomIsolated adapter consists of a receive adapter only.</span></span> <span data-ttu-id="49fb6-109">Utilice el adaptador de recepción WCF-CustomIsolated para recibir solicitudes de Servicio WCF a través de enlaces WCF, comportamiento de servicio, comportamiento de extremo, mecanismo de seguridad y el origen del cuerpo del mensaje entrante que haya seleccionado y configurado para la ubicación de recepción que se ejecuta en un host aislado.</span><span class="sxs-lookup"><span data-stu-id="49fb6-109">You use the WCF-CustomIsolated receive adapter to receive WCF service requests through WCF bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured for the receive location running in an isolated host.</span></span> <span data-ttu-id="49fb6-110">Una ubicación de recepción que usa el adaptador de recepción WCF-CustomIsolated se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="49fb6-110">A receive location that uses the WCF-CustomIsolated receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="49fb6-111">Para obtener más información acerca de WCF adaptadores de recepción, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="49fb6-111">For more information about WCF receive adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fb6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="49fb6-112">See Also</span></span>  
 <span data-ttu-id="49fb6-113">[Configurar el adaptador de WCF-CustomIsolated](../core/configuring-the-wcf-customisolated-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="49fb6-113">[Configuring the WCF-CustomIsolated Adapter](../core/configuring-the-wcf-customisolated-adapter.md) </span></span>  
 [<span data-ttu-id="49fb6-114">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="49fb6-114">WCF Adapters</span></span>](../core/wcf-adapters.md)