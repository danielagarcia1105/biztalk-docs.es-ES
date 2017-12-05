---
title: Supervisar los servidores SQL Server | Documentos de Microsoft
description: "Utilizar el módulo de administración de SQL Server para comprobar el rendimiento, espacio disponible, configuración de base de datos, los procesos bloqueados, conectividad, error SQL trabajos del agente, replicación y más información en el servidor BizTalk Server"
ms.custom: 
ms.date: 11/29/2017
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
ms.openlocfilehash: 1d0e3ea9ecb9d9d910549790568d5891b72d06de
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="monitoring-sql-servers"></a><span data-ttu-id="7926b-103">Supervisión de servidores SQL Server</span><span class="sxs-lookup"><span data-stu-id="7926b-103">Monitoring SQL Servers</span></span>

## <a name="use-sql-management-pack"></a><span data-ttu-id="7926b-104">Usar el módulo de administración de SQL</span><span class="sxs-lookup"><span data-stu-id="7926b-104">Use SQL management pack</span></span>
<span data-ttu-id="7926b-105">El módulo de administración de Microsoft SQL Server proporciona tanto proactiva como reactiva de supervisión de SQL Server en un entorno empresarial.</span><span class="sxs-lookup"><span data-stu-id="7926b-105">The Microsoft SQL Server management pack provides both proactive and reactive monitoring of SQL Server in an enterprise environment.</span></span> <span data-ttu-id="7926b-106">Disponibilidad y la supervisión de configuración, recopilación de datos de rendimiento y umbrales predeterminados se crean para la supervisión de nivel de empresa.</span><span class="sxs-lookup"><span data-stu-id="7926b-106">Availability and configuration monitoring, performance data collection, and default thresholds are built for enterprise-level monitoring.</span></span> <span data-ttu-id="7926b-107">Conectividad local y remota comprobaciones ayudan a garantizar la disponibilidad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7926b-107">Both local and remote connectivity checks help ensure database availability.</span></span>  
  
 <span data-ttu-id="7926b-108">Con los conocimientos incrustados en el módulo de administración de SQL Server, proactivamente puede administrar SQL Server e identificar problemas antes de que resulten críticos.</span><span class="sxs-lookup"><span data-stu-id="7926b-108">With the embedded expertise in the SQL Server management pack, you can proactively manage SQL Server, and identify issues before they become critical.</span></span> <span data-ttu-id="7926b-109">Este módulo de administración aumenta la seguridad, la disponibilidad y el rendimiento de la infraestructura de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7926b-109">This management pack increases the security, availability, and performance of your SQL Server infrastructure.</span></span>  
  
 <span data-ttu-id="7926b-110">La Guía del módulo de administración de Microsoft SQL Server viene con el módulo de describe el contenido del módulo de administración y cómo implementarla.</span><span class="sxs-lookup"><span data-stu-id="7926b-110">The Microsoft SQL Server management pack guide that comes with the pack describes the content of the management pack, and describes how to deploy it.</span></span> <span data-ttu-id="7926b-111">Características del módulo de administración incluyen:</span><span class="sxs-lookup"><span data-stu-id="7926b-111">Features of the management pack include:</span></span>  
  
-   <span data-ttu-id="7926b-112">Supervisión del estado de los servicios incluidos como SQL Server, Agente SQL, servidor de informes, Notification Services</span><span class="sxs-lookup"><span data-stu-id="7926b-112">Monitoring the state of the included services such as SQL Server, SQL Agent, Report Server, Notification Services</span></span>  
  
-   <span data-ttu-id="7926b-113">Supervisión del estado de las bases de datos</span><span class="sxs-lookup"><span data-stu-id="7926b-113">Monitoring the state of databases</span></span>  
  
-   <span data-ttu-id="7926b-114">Supervisar el espacio disponible en las bases de datos, puede configurables por % o MB</span><span class="sxs-lookup"><span data-stu-id="7926b-114">Monitoring the available space in databases, configurable by % or MB</span></span>  
  
-   <span data-ttu-id="7926b-115">Asegurarse de que las bases de datos están configurados correctamente</span><span class="sxs-lookup"><span data-stu-id="7926b-115">Ensuring databases are configured correctly</span></span>  
  
-   <span data-ttu-id="7926b-116">Asegúrese de que los clientes pueden conectarse a SQL Server</span><span class="sxs-lookup"><span data-stu-id="7926b-116">Ensure clients can connect to the SQL Server</span></span>  
  
-   <span data-ttu-id="7926b-117">Supervisar procesos bloqueados</span><span class="sxs-lookup"><span data-stu-id="7926b-117">Monitor blocked processes</span></span>  
  
-   <span data-ttu-id="7926b-118">Controlar errores de agente trabajos y trabajos que se tarda un tiempo excesivo para ejecutar</span><span class="sxs-lookup"><span data-stu-id="7926b-118">Watch for failed agent jobs, and jobs taking an excessive time to execute</span></span>  
  
-   <span data-ttu-id="7926b-119">Supervisar el estado de replicación y alerta cuando se produzcan errores</span><span class="sxs-lookup"><span data-stu-id="7926b-119">Monitor the health of replication and alert on failures</span></span>  
  
-   <span data-ttu-id="7926b-120">Supervisar el estado de creación de reflejo de base de datos</span><span class="sxs-lookup"><span data-stu-id="7926b-120">Monitor the state of Database Mirroring</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7926b-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7926b-121">Next steps</span></span>
  
-   [<span data-ttu-id="7926b-122">Supervisión de las bases de datos y trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="7926b-122">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)  
  
-   [<span data-ttu-id="7926b-123">Cómo marcar las bases de datos de BizTalk Server para la supervisión personalizada</span><span class="sxs-lookup"><span data-stu-id="7926b-123">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
-   [<span data-ttu-id="7926b-124">Supervisar las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7926b-124">Monitor the BizTalk Server Databases</span></span>](../technical-guides/monitor-the-biztalk-server-databases.md)