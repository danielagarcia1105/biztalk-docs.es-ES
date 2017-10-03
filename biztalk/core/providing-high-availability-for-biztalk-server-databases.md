---
title: Proporcionar una alta disponibilidad para bases de datos de servidor BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- databases, architecture
- SQL Server, clustering
- servers, clustering
- databases, high availability
- architecture
- databases, clustering
- BizTalk Server, architecture
- Windows clustering
- high availability, databases
- clustering, databases
- data, persistence
- SQL Server Analysis Services
ms.assetid: 47fbc402-9e46-41dd-bc12-d1cde1982576
caps.latest.revision: "41"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3648a8f6d48bbfd6cf67995e1d314511b70db7bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="providing-high-availability-for-biztalk-server-databases"></a><span data-ttu-id="0dbaf-102">Proporcionar una alta disponibilidad a las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0dbaf-102">Providing High Availability for BizTalk Server Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0dbaf-103"> depende en gran medida de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para la persistencia de datos.</span><span class="sxs-lookup"><span data-stu-id="0dbaf-103"> relies heavily on [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] for data persistence.</span></span> <span data-ttu-id="0dbaf-104">Los demás componentes y hosts de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tienen funciones específicas en el proceso de integrar aplicaciones empresariales diferentes (por ejemplo, recibir, procesar o enrutar mensajes), pero el equipo de la base de datos captura este trabajo y lo almacena en disco.</span><span class="sxs-lookup"><span data-stu-id="0dbaf-104">All other components and hosts in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] have specific roles in the process of integrating disparate business applications (for example, receiving, processing, or routing messages), but the database computer captures this work and persists it to disk.</span></span>  
  
 <span data-ttu-id="0dbaf-105">Para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, utilice clústeres de conmutación por error de Windows Server para configurar dos equipos de base de datos que ejecutan SQL Server para crear un clúster de servidores.</span><span class="sxs-lookup"><span data-stu-id="0dbaf-105">To provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, use Windows Server Failover Clustering to configure two database computers that are running SQL Server to create a server cluster.</span></span> <span data-ttu-id="0dbaf-106">La agrupación de servidores proporciona redundancia y tolerancia a errores a las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dbaf-106">Server clustering provides redundancy and fault tolerance for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="0dbaf-107">A diferencia de la agrupación con equilibrio de carga, en la que un grupo de equipos funciona conjuntamente para aumentar la disponibilidad y la escalabilidad, la agrupación de servidores suele consistir en un par de equipos de base de datos en una configuración activo/pasivo, de modo que un equipo proporciona recursos de copia de seguridad para el otro.</span><span class="sxs-lookup"><span data-stu-id="0dbaf-107">Unlike load-balanced clustering, where a group of computers functions together to increase availability and scalability, server clustering typically involves a pair of database computers in an active/passive configuration so that one computer provides backup resources for the other.</span></span>  
  
 <span data-ttu-id="0dbaf-108">La siguientes ilustración muestra un nivel de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que obtiene alta disponibilidad mediante una agrupación de servidores de tipo activo/pasivo.</span><span class="sxs-lookup"><span data-stu-id="0dbaf-108">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database tier with high availability through active/passive server clustering.</span></span>  
  
 <span data-ttu-id="0dbaf-109">![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="0dbaf-109">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="0dbaf-110">Si el equipo de base de datos activo detecta errores o deja de funcionar, el equipo pasivo se vuelve activo y asume el control de los recursos de base de datos hasta que se soluciona el problema.</span><span class="sxs-lookup"><span data-stu-id="0dbaf-110">If the active database computer encounters errors or fails, the passive computer becomes active and assumes control over the database resources until the failed computer is repaired.</span></span> <span data-ttu-id="0dbaf-111">El servicio de base de datos conmuta por error, restaura las conexiones de datos en el nuevo equipo activo y permite que la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] siga funcionando.</span><span class="sxs-lookup"><span data-stu-id="0dbaf-111">The database service fails over and restores data connections to the new active computer and enables the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application to continue functioning.</span></span>  
  
 <span data-ttu-id="0dbaf-112">Para obtener información acerca de las bases de datos que se instalan con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [bases de datos de BizTalk Server](../core/databases-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="0dbaf-112">For information about the databases that are installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="0dbaf-113">Para obtener información acerca de la copia de seguridad de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0dbaf-113">For information about backing up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0dbaf-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0dbaf-114">In This Section</span></span>  
  
-   [<span data-ttu-id="0dbaf-115">Bases de datos de escala horizontal</span><span class="sxs-lookup"><span data-stu-id="0dbaf-115">Scaled-Out Databases</span></span>](../core/scaled-out-databases.md)  
  
-   [<span data-ttu-id="0dbaf-116">Agrupación en clústeres las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0dbaf-116">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)  
  
-   [<span data-ttu-id="0dbaf-117">Comportamiento de las instancias de Host de BizTalk Server durante la conmutación por error SQL Server</span><span class="sxs-lookup"><span data-stu-id="0dbaf-117">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)  
  
-   [<span data-ttu-id="0dbaf-118">Creación de reflejo, servicio de instantáneas de volumen y AlwaysOn de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0dbaf-118">SQL Server database mirroring, Volume Shadow Copy service and AlwaysOn</span></span>](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
  
## <a name="see-also"></a><span data-ttu-id="0dbaf-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dbaf-119">See Also</span></span>  
 <span data-ttu-id="0dbaf-120">[Proporcionar alta disponibilidad de Hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="0dbaf-120">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="0dbaf-121">Escenarios de alta disponibilidad de servidor BizTalk Server de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0dbaf-121">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)