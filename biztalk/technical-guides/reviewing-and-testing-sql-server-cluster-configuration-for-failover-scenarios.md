---
title: Revisar y probar SQL Server la configuración para escenarios de conmutación por error del clúster | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dbeb383-5b38-4467-acf8-2a5b244e5fa9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981a879a5dad68bfb423a03b82e11fb646f912c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973261"
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a><span data-ttu-id="f2b72-102">Revisar y probar la configuración de clúster SQL Server para escenarios de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="f2b72-102">Reviewing and Testing SQL Server Cluster Configuration for Failover Scenarios</span></span>
<span data-ttu-id="f2b72-103">Agrupación en clústeres de Windows y SQL Server permiten ejecutar SQL Server en modo activo/activo, donde cada nodo del clúster es "activas" y en funcionamiento las instancias de SQL Server de uno o más.</span><span class="sxs-lookup"><span data-stu-id="f2b72-103">Windows Clustering and SQL Server allow you to run SQL Server in Active/Active mode where each node of the cluster is “active” and running one or more SQL Server instances.</span></span> <span data-ttu-id="f2b72-104">Esto le permitiría, por ejemplo, para que la base de datos de cuadro de mensajes en un nodo y todos los demás [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en el otro nodo.</span><span class="sxs-lookup"><span data-stu-id="f2b72-104">This would allow you, for example, to have the MessageBox database on one node and all other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases on the other node.</span></span> <span data-ttu-id="f2b72-105">Esto permite maximizar el uso de hardware de clúster.</span><span class="sxs-lookup"><span data-stu-id="f2b72-105">This allows you to maximize cluster hardware usage.</span></span>  
  
 <span data-ttu-id="f2b72-106">Sin embargo, si usa esta configuración, debe comprobar que cada nodo puede controlar al mismo tiempo la carga de todas las instancias de SQL Server durante una conmutación por error de nodo de SQL Server Cluster Server.</span><span class="sxs-lookup"><span data-stu-id="f2b72-106">If you use this configuration, however, you must verify that each node can simultaneously handle the load of all SQL Server instances during a SQL Server cluster node failover.</span></span>  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a><span data-ttu-id="f2b72-107">Evaluar la conmutación por error para un clúster activo/activo</span><span class="sxs-lookup"><span data-stu-id="f2b72-107">Evaluating Failover for an Active/Active Cluster</span></span>  
 <span data-ttu-id="f2b72-108">Consideraciones al comprobar que un nodo único puede controlar la carga de todas las instancias de SQL Server en el caso de un nodo de clúster de SQL Server conmutación por error incluyen:</span><span class="sxs-lookup"><span data-stu-id="f2b72-108">Considerations when verifying that a single node can handle the load of all SQL Server instances in the event of a SQL Server cluster node failover include:</span></span>  
  
- <span data-ttu-id="f2b72-109">¿El nodo de conmutación por error tiene suficientes recursos de CPU?</span><span class="sxs-lookup"><span data-stu-id="f2b72-109">Does the failover node have sufficient CPU resources?</span></span>  
  
- <span data-ttu-id="f2b72-110">¿El nodo de conmutación por error tiene suficiente memoria?</span><span class="sxs-lookup"><span data-stu-id="f2b72-110">Does the failover node have sufficient memory?</span></span>  
  
- <span data-ttu-id="f2b72-111">¿Hay suficiente ancho de banda de red?</span><span class="sxs-lookup"><span data-stu-id="f2b72-111">Is there sufficient network bandwidth?</span></span>  
  
- <span data-ttu-id="f2b72-112">¿El nodo de conmutación por error puede controlar la contención de E/S de disco mayor?</span><span class="sxs-lookup"><span data-stu-id="f2b72-112">Can the failover node handle the increased disk I/O contention?</span></span>  
  
  <span data-ttu-id="f2b72-113">Al probar la conmutación por error, se deben evaluar los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="f2b72-113">The following scenarios should be evaluated when testing failover:</span></span>  
  
- <span data-ttu-id="f2b72-114">Corte del suministro eléctrico en el servidor activo</span><span class="sxs-lookup"><span data-stu-id="f2b72-114">Power failure on the active server</span></span>  
  
- <span data-ttu-id="f2b72-115">Corte del suministro eléctrico en el servidor pasivo</span><span class="sxs-lookup"><span data-stu-id="f2b72-115">Power failure on the passive server</span></span>  
  
- <span data-ttu-id="f2b72-116">Pérdida de conexión del disco</span><span class="sxs-lookup"><span data-stu-id="f2b72-116">Loss of disk connection</span></span>  
  
- <span data-ttu-id="f2b72-117">Interrumpa la conexión de red pública en el nodo activo</span><span class="sxs-lookup"><span data-stu-id="f2b72-117">Broken public network connection on the Active node</span></span>  
  
- <span data-ttu-id="f2b72-118">Interrumpa la conexión de red privada en el nodo activo</span><span class="sxs-lookup"><span data-stu-id="f2b72-118">Broken private network connection on the Active node</span></span>  
  
- <span data-ttu-id="f2b72-119">Interrumpa la conexión de red pública en el nodo pasivo</span><span class="sxs-lookup"><span data-stu-id="f2b72-119">Broken public network connection on the Passive node</span></span>  
  
- <span data-ttu-id="f2b72-120">Interrumpa la conexión de red privada en el nodo pasivo</span><span class="sxs-lookup"><span data-stu-id="f2b72-120">Broken private network connection on the Passive node</span></span>  
  
- <span data-ttu-id="f2b72-121">Servicio de SQL Server con error</span><span class="sxs-lookup"><span data-stu-id="f2b72-121">Failed SQL Server service</span></span>  
  
- <span data-ttu-id="f2b72-122">Servicio Agente SQL Server con errores</span><span class="sxs-lookup"><span data-stu-id="f2b72-122">Failed SQL Server Agent service</span></span>  
  
## <a name="using-an-activeactivepassive-cluster"></a><span data-ttu-id="f2b72-123">Uso de un clúster activo/activo/pasivo</span><span class="sxs-lookup"><span data-stu-id="f2b72-123">Using an Active/Active/Passive Cluster</span></span>  
 <span data-ttu-id="f2b72-124">Si determina que un nodo no puede controlar todas las instancias de SQL Server en un escenario de conmutación por error, una alternativa es usar un modelo de agrupación en clústeres activo/activo/pasivo.</span><span class="sxs-lookup"><span data-stu-id="f2b72-124">If you determine that one node cannot handle all SQL Server instances in a failover scenario, an alternative is to use an Active/Active/Passive clustering model.</span></span> <span data-ttu-id="f2b72-125">El modelo de agrupación en clústeres activo/activo/pasivo aumenta en gran medida la probabilidad de que siempre habrá un nodo pasivo disponibles para escenarios de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="f2b72-125">The Active/Active/Passive clustering model greatly increases the likelihood that there will always be one Passive node available for failover scenarios.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b72-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2b72-126">See Also</span></span>  
 [<span data-ttu-id="f2b72-127">Lista de comprobación: configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2b72-127">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)