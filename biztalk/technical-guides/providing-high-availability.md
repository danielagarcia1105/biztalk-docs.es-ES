---
title: Proporcionar una alta disponibilidad | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9240e776-555c-4c38-8b59-8fef1ba6a567
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4521981bc3df67553c244a55c91c1eb045c8e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="providing-high-availability"></a><span data-ttu-id="89475-102">Proporcionar una alta disponibilidad</span><span class="sxs-lookup"><span data-stu-id="89475-102">Providing High Availability</span></span>
<span data-ttu-id="89475-103">Se proporciona alta disponibilidad para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la implementación de redundancia para todos los componentes funcionales en el entorno.</span><span class="sxs-lookup"><span data-stu-id="89475-103">High availability is provided for a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by implementing redundancy for each functional component in the environment.</span></span> <span data-ttu-id="89475-104">Redundancia de un Host de BizTalk puede realizarse mediante la instalación de varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un grupo de BizTalk y, a continuación, configurar instancias del host para que se ejecute en más de uno de los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el grupo.</span><span class="sxs-lookup"><span data-stu-id="89475-104">Redundancy for a BizTalk Host can be accomplished by installing multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a BizTalk group and then configuring instances of the host to run on more than one of the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="89475-105">Redundancia de otros componentes de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno puede realizarse mediante la configuración de los componentes como recursos en un [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] clúster.</span><span class="sxs-lookup"><span data-stu-id="89475-105">Redundancy for other components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment can be accomplished by configuring the components as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="89475-106">incorpora también configurando los Hosts de BizTalk como recursos en un [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] clúster, lo que se recomienda para proporcionar alta disponibilidad de ciertos adaptadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="89475-106"> also accommodates configuring BizTalk Hosts as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster, which is recommended to provide high availability for certain BizTalk adapters.</span></span>  
  
 <span data-ttu-id="89475-107">Esta sección describe cómo proporcionar alta disponibilidad para los componentes funcionales en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="89475-107">This section describes how to provide high availability for the functional components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89475-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="89475-108">In This Section</span></span>  
  
-   [<span data-ttu-id="89475-109">Planeación de alta disponibilidad2</span><span class="sxs-lookup"><span data-stu-id="89475-109">Planning for High Availability2</span></span>](../technical-guides/planning-for-high-availability2.md)  
  
-   [<span data-ttu-id="89475-110">Alta disponibilidad para los Hosts de BizTalk</span><span class="sxs-lookup"><span data-stu-id="89475-110">High Availability for BizTalk Hosts</span></span>](../technical-guides/high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="89475-111">Alta disponibilidad para bases de datos</span><span class="sxs-lookup"><span data-stu-id="89475-111">High Availability for Databases</span></span>](../technical-guides/high-availability-for-databases.md)  
  
-   [<span data-ttu-id="89475-112">Alta disponibilidad para el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="89475-112">High Availability for the Master Secret Server</span></span>](../technical-guides/high-availability-for-the-master-secret-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="89475-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="89475-113">See Also</span></span>  
 [<span data-ttu-id="89475-114">Recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="89475-114">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)