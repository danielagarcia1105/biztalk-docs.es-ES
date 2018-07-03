---
title: Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2 | Microsoft Docs
ms.custom: ''
ms.date: 2016-01-04
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Passive configuration [Master Secret server]
- Active configuration [Master Secret server]
- clustering, about clustering
- high availability
- Windows Server cluster, warnings
- installation, high availibility planning
- Master Secret server
- installation, configuring
- Master Secret server, configuring
- installation, Windows Server cluster
- clustering
ms.assetid: 4d7f0842-561e-49e0-ab08-504256b9294f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8893bcd043ca046c310ee52276eb28476be4ea9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001181"
---
# <a name="using-windows-server-cluster-to-provide-high-availability-for-biztalk-server-hosts2"></a><span data-ttu-id="247a7-102">Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2</span><span class="sxs-lookup"><span data-stu-id="247a7-102">Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="247a7-103"> Proporciona funcionalidad que le permite configurar un host de BizTalk como un recurso agrupado dentro de un grupo de clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="247a7-103"> provides functionality that allows you to configure a BizTalk host as a clustered resource within a  Windows Server failover cluster group.</span></span> <span data-ttu-id="247a7-104">La compatibilidad con clústeres de hosts se proporciona para lograr alta disponibilidad en los adaptadores integrados de BizTalk que no se deben ejecutar en varias instancias de host simultáneamente, como el controlador de recepción FTP o, en determinadas circunstancias, el controlador de recepción POP3.</span><span class="sxs-lookup"><span data-stu-id="247a7-104">Host cluster support is provided to support high availability for integrated BizTalk adapters that should not be run in multiple host instances simultaneously, such as the FTP receive handler or, under certain circumstances, the POP3 receive handler.</span></span> <span data-ttu-id="247a7-105">También se proporciona la funcionalidad de agrupación de hosts para garantizar la coherencia transaccional de los mensajes enviados o recibidos por el adaptador de MSMQ en escenarios que requieren que el servicio MSMQ esté agrupado.</span><span class="sxs-lookup"><span data-stu-id="247a7-105">Host cluster support is also provided to ensure transactional consistency for messages sent or received by the MSMQ adapter in scenarios that require that the MSMQ service is clustered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="247a7-106">La agrupación de hosts en clúster está disponible únicamente en la edición empresarial de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="247a7-106">Host clustering is only available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise Edition.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="247a7-107">Para agrupar un host de BizTalk, debe haber configurado al menos dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo como miembros de un clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="247a7-107">Before you can cluster a BizTalk host, you must have configured at least two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group as members of a Windows Server Failover cluster.</span></span> <span data-ttu-id="247a7-108">Para obtener más información acerca de cómo configurar un clúster de conmutación por error de Windows Server, consulte la Ayuda en pantalla de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="247a7-108">For more information about configuring a Windows Server Failover cluster, please see the Windows Server online help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="247a7-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="247a7-109">In This Section</span></span>  
  
-   [<span data-ttu-id="247a7-110">Consideraciones para instalar BizTalk Server en un clúster de servidores Windows Server</span><span class="sxs-lookup"><span data-stu-id="247a7-110">Considerations for Installing BizTalk Server on a Windows Server Cluster</span></span>](../core/considerations-for-installing-biztalk-server-on-a-windows-server-cluster2.md)  
  
-   [<span data-ttu-id="247a7-111">Cómo configurar un Host de BizTalk como un recurso de clúster</span><span class="sxs-lookup"><span data-stu-id="247a7-111">How to Configure a BizTalk Host as a Cluster Resource</span></span>](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)  
  
-   [<span data-ttu-id="247a7-112">Consideraciones para ejecutar controladores de adaptador en un host agrupado</span><span class="sxs-lookup"><span data-stu-id="247a7-112">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)