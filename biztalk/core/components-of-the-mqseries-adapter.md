---
title: Componentes del adaptador de MQSeries | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, BizTalk component
- MQSeries adapters, components
- MQSeries components, MQSeries adapters
- BizTalk components
- MQSeries adapters, MQSeries component
ms.assetid: 923974cb-371d-47dc-99a7-2f7b93f60ada
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afeac0dda1d42c244eeeac124632ed68aa2e90d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990333"
---
# <a name="components-of-the-mqseries-adapter"></a><span data-ttu-id="40f63-102">Componentes del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="40f63-102">Components of the MQSeries Adapter</span></span>
<span data-ttu-id="40f63-103">El adaptador de MQSeries utiliza dos componentes para facilitar la transferencia de documentos entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y MQSeries Server para Windows.</span><span class="sxs-lookup"><span data-stu-id="40f63-103">The MQSeries adapter uses two components to facilitate document transfer between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and MQSeries Server for Windows.</span></span>  
  
- <span data-ttu-id="40f63-104">**Componente de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="40f63-104">**BizTalk component.**</span></span> <span data-ttu-id="40f63-105">Instale este componente en el mismo equipo que Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40f63-105">Install this component on the same computer as Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="40f63-106">Este componente se comunica con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="40f63-106">This component communicates with BizTalk Server.</span></span>  
  
- <span data-ttu-id="40f63-107">**Componente de MQSeries.**</span><span class="sxs-lookup"><span data-stu-id="40f63-107">**MQSeries component.**</span></span> <span data-ttu-id="40f63-108">Instale este componente en MQSeries Server para Windows.</span><span class="sxs-lookup"><span data-stu-id="40f63-108">Install this component on the MQSeries Server for Windows.</span></span> <span data-ttu-id="40f63-109">MQSeries Server para Windows se ejecuta en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40f63-109">MQSeries Server for Windows runs on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span> <span data-ttu-id="40f63-110">Este componente (conocido como MQSAgent) se comunica con IBM MQSeries Server.</span><span class="sxs-lookup"><span data-stu-id="40f63-110">This component (referred to as MQSAgent) communicates with IBM MQSeries Server.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="40f63-111">El componente MQSAgent del adaptador de MQSeries es compatible si se ejecuta con MQSeries Server 5.3, CSD10 o posterior, y WebSphere MQSeries Server 6.0 en Windows.</span><span class="sxs-lookup"><span data-stu-id="40f63-111">The MQSAgent component of the MQSeries Adapter is supported running against MQSeries Server 5.3, CSD10 or above, and WebSphere MQSeries Server 6.0 on Windows.</span></span>  
  
  <span data-ttu-id="40f63-112">La siguiente ilustración muestra un uso típico del adaptador.</span><span class="sxs-lookup"><span data-stu-id="40f63-112">The following figure outlines a typical use of the adapter.</span></span>  
  
  <span data-ttu-id="40f63-113">![Documentar el flujo entre MQSeries Server y BizTalk](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span><span class="sxs-lookup"><span data-stu-id="40f63-113">![Document flow between MQSeries Server and BizTalk](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span></span>  
  
  <span data-ttu-id="40f63-114">El adaptador de MQSeries es una solución de conectividad que permite usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una empresa con MQSeries como estándar de mensajería.</span><span class="sxs-lookup"><span data-stu-id="40f63-114">The MQSeries adapter is a connectivity solution that lets you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an enterprise with MQSeries as the chosen messaging standard.</span></span> <span data-ttu-id="40f63-115">El desarrollo de esta solución estuvo motivado en parte por los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="40f63-115">Developing this solution was motivated, in part, by the following issues:</span></span>  
  
- <span data-ttu-id="40f63-116">Clientes que solicitaban una instalación y una configuración sencillas, y una solución de conectividad de MQSeries</span><span class="sxs-lookup"><span data-stu-id="40f63-116">Accommodating customer requests for simple installation and configuration, and an MQSeries connectivity solution</span></span>  
  
- <span data-ttu-id="40f63-117">Admitir tamaños de mensaje de hasta 100 MB</span><span class="sxs-lookup"><span data-stu-id="40f63-117">Supporting message sizes up to 100 MB</span></span>  
  
- <span data-ttu-id="40f63-118">Proporcionar compatibilidad con MQSeries</span><span class="sxs-lookup"><span data-stu-id="40f63-118">Providing MQSeries support</span></span>  
  
- <span data-ttu-id="40f63-119">Proporcionar una solución de conectividad Plug and Play para mensajes de MQSeries a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40f63-119">Providing a Plug and Play connectivity solution for MQSeries messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
  <span data-ttu-id="40f63-120">El adaptador de MQSeries es una adición clave al conjunto de servicios de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que proporcionan una serie de agentes de escucha para varios estándares de protocolo de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="40f63-120">The MQSeries adapter is a key addition to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suite of receive services that provide a set of listeners for various communication protocol standards.</span></span> <span data-ttu-id="40f63-121">Los agentes de escucha adjuntan un protocolo, por ejemplo HTTP, FTP o MQSeries, a una relación comercial de integración de aplicaciones empresariales (EAI), de negocio a negocio o de aplicación a aplicación.</span><span class="sxs-lookup"><span data-stu-id="40f63-121">The listeners attach a protocol, for example HTTP, FTP, or MQSeries, to an enterprise application integration (EAI), business-to-business, or application-to-application integration trading relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f63-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="40f63-122">See Also</span></span>  
 <span data-ttu-id="40f63-123">[Arquitectura del adaptador de MQSeries](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="40f63-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="40f63-124">¿Qué es el adaptador de MQSeries?</span><span class="sxs-lookup"><span data-stu-id="40f63-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)