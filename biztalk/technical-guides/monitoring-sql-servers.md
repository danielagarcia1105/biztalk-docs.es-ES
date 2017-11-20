---
title: "Supervisión de servidores SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31871432-e13d-4ef3-b886-16c833371f6d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac37905574090fb346aeee198ea8e92a0f436f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-servers"></a><span data-ttu-id="e4553-102">Supervisión de servidores SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4553-102">Monitoring SQL Servers</span></span>
<span data-ttu-id="e4553-103">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración proporciona supervisión reactiva y proactiva de [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] en un entorno empresarial.</span><span class="sxs-lookup"><span data-stu-id="e4553-103">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack provides both proactive and reactive monitoring of [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] and [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] in an enterprise environment.</span></span> <span data-ttu-id="e4553-104">Disponibilidad y la supervisión de configuración, recopilación de datos de rendimiento y umbrales predeterminados se crean para la supervisión de nivel de empresa.</span><span class="sxs-lookup"><span data-stu-id="e4553-104">Availability and configuration monitoring, performance data collection, and default thresholds are built for enterprise-level monitoring.</span></span> <span data-ttu-id="e4553-105">Conectividad local y remota comprobaciones ayudan a garantizar la disponibilidad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e4553-105">Both local and remote connectivity checks help ensure database availability.</span></span>  
  
 <span data-ttu-id="e4553-106">Con los conocimientos incrustados en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración, pueden administrar de manera proactiva [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]e identificar problemas antes de que resulten críticos.</span><span class="sxs-lookup"><span data-stu-id="e4553-106">With the embedded expertise in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack, you can proactively manage [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and identify issues before they become critical.</span></span> <span data-ttu-id="e4553-107">Este módulo de administración aumenta la seguridad, la disponibilidad y el rendimiento de su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] infraestructura.</span><span class="sxs-lookup"><span data-stu-id="e4553-107">This management pack increases the security, availability, and performance of your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] infrastructure.</span></span>  
  
 <span data-ttu-id="e4553-108">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Guía del módulo de administración que se incluye con el módulo de describe el contenido del módulo de administración y cómo implementarla.</span><span class="sxs-lookup"><span data-stu-id="e4553-108">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack guide that comes with the pack describes the content of the management pack, and describes how to deploy it.</span></span> <span data-ttu-id="e4553-109">Características del módulo de administración incluyen:</span><span class="sxs-lookup"><span data-stu-id="e4553-109">Features of the management pack include:</span></span>  
  
-   <span data-ttu-id="e4553-110">Supervisión del estado de los servicios incluidos como [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], Agente SQL, servidor de informes, Notification Services</span><span class="sxs-lookup"><span data-stu-id="e4553-110">Monitoring the state of the included services such as [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], SQL Agent, Report Server, Notification Services</span></span>  
  
-   <span data-ttu-id="e4553-111">Supervisión del estado de las bases de datos</span><span class="sxs-lookup"><span data-stu-id="e4553-111">Monitoring the state of databases</span></span>  
  
-   <span data-ttu-id="e4553-112">Supervisar el espacio disponible en las bases de datos, puede configurables por % o MB</span><span class="sxs-lookup"><span data-stu-id="e4553-112">Monitoring the available space in databases, configurable by % or MB</span></span>  
  
-   <span data-ttu-id="e4553-113">Asegurarse de que las bases de datos están configurados correctamente</span><span class="sxs-lookup"><span data-stu-id="e4553-113">Ensuring databases are configured correctly</span></span>  
  
-   <span data-ttu-id="e4553-114">Asegúrese de que los clientes pueden conectarse a la[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4553-114">Ensure clients can connect to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="e4553-115">Supervisar procesos bloqueados</span><span class="sxs-lookup"><span data-stu-id="e4553-115">Monitor blocked processes</span></span>  
  
-   <span data-ttu-id="e4553-116">Controlar errores de agente trabajos y trabajos que se tarda un tiempo excesivo para ejecutar</span><span class="sxs-lookup"><span data-stu-id="e4553-116">Watch for failed agent jobs, and jobs taking an excessive time to execute</span></span>  
  
-   <span data-ttu-id="e4553-117">Supervisar el estado de replicación y alerta cuando se produzcan errores</span><span class="sxs-lookup"><span data-stu-id="e4553-117">Monitor the health of replication and alert on failures</span></span>  
  
-   <span data-ttu-id="e4553-118">Supervisar el estado de creación de reflejo de base de datos</span><span class="sxs-lookup"><span data-stu-id="e4553-118">Monitor the state of Database Mirroring</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4553-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e4553-119">In This Section</span></span>  
  
-   [<span data-ttu-id="e4553-120">Supervisión de trabajos del Agente SQL Server y bases de datos</span><span class="sxs-lookup"><span data-stu-id="e4553-120">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)  
  
-   [<span data-ttu-id="e4553-121">Cómo marcar bases de datos de BizTalk Server para supervisión personalizada</span><span class="sxs-lookup"><span data-stu-id="e4553-121">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
-   [<span data-ttu-id="e4553-122">Supervisar las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e4553-122">Monitor the BizTalk Server Databases</span></span>](../technical-guides/monitor-the-biztalk-server-databases.md)