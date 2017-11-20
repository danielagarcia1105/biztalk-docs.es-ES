---
title: "Lista de comprobación: Supervisión preparación operativa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef77ccc2-1d39-4e78-8fea-5c17d05c8174
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 913ed00da2bda4126ba298bbb9bce2980efa4366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-monitoring-operational-readiness"></a><span data-ttu-id="2535a-102">Lista de comprobación: Supervisión preparación operativa</span><span class="sxs-lookup"><span data-stu-id="2535a-102">Checklist: Monitoring Operational Readiness</span></span>
<span data-ttu-id="2535a-103">En este tema se enumera los pasos que debe seguir al supervisar una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="2535a-103">This topic lists the steps that you should follow when monitoring a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
|<span data-ttu-id="2535a-104">Pasos</span><span class="sxs-lookup"><span data-stu-id="2535a-104">Steps</span></span>|<span data-ttu-id="2535a-105">Referencia</span><span class="sxs-lookup"><span data-stu-id="2535a-105">Reference</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="2535a-106">Seleccionar e implementar una estrategia de supervisión para la infraestructura y las aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2535a-106">Select and implement a monitoring strategy for your BizTalk applications and infrastructure.</span></span>|[<span data-ttu-id="2535a-107">Supervisar el entorno de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2535a-107">Monitoring the BizTalk Server Environment</span></span>](../technical-guides/monitoring-the-biztalk-server-environment.md)|  
|<span data-ttu-id="2535a-108">Supervisar el uso de espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="2535a-108">Monitor disk space usage.</span></span>|[<span data-ttu-id="2535a-109">Supervisar el uso de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="2535a-109">Monitoring Disk Space Usage</span></span>](../technical-guides/monitoring-disk-space-usage.md)|  
|<span data-ttu-id="2535a-110">Supervisar SQL Server:</span><span class="sxs-lookup"><span data-stu-id="2535a-110">Monitor SQL Server:</span></span><br /><br /> <span data-ttu-id="2535a-111">-Compruebe que los equipos de alojamiento de SQL Server el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos que se están supervisando.</span><span class="sxs-lookup"><span data-stu-id="2535a-111">-   Verify that computers running SQL Server housing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are being monitored.</span></span><br /><span data-ttu-id="2535a-112">-Compruebe que la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajos que se están supervisando.</span><span class="sxs-lookup"><span data-stu-id="2535a-112">-   Verify that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] jobs are being monitored.</span></span>|<span data-ttu-id="2535a-113">-   [Supervisión de servidores SQL Server](../technical-guides/monitoring-sql-servers.md)</span><span class="sxs-lookup"><span data-stu-id="2535a-113">-   [Monitoring SQL Servers](../technical-guides/monitoring-sql-servers.md)</span></span><br /><span data-ttu-id="2535a-114">-   [Supervisión de las bases de datos de servidor BizTalk Server](../technical-guides/monitoring-biztalk-server-databases.md)</span><span class="sxs-lookup"><span data-stu-id="2535a-114">-   [Monitoring BizTalk Server Databases](../technical-guides/monitoring-biztalk-server-databases.md)</span></span>|  
|<span data-ttu-id="2535a-115">Supervisar las aplicaciones de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="2535a-115">Monitor BizTalk applications:</span></span><br /><br /> <span data-ttu-id="2535a-116">-Modificar las reglas existentes o copiar reglas en un módulo de administración personalizado para supervisar una aplicación personalizada de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2535a-116">-   Modify existing rules and/or copy rules to a custom management pack to monitor a custom BizTalk application.</span></span><br /><span data-ttu-id="2535a-117">-Crear acciones para cada regla definida.</span><span class="sxs-lookup"><span data-stu-id="2535a-117">-   Create actions for each defined rule.</span></span><br /><span data-ttu-id="2535a-118">-Crear procesos iterativos para automatizar las tareas manuales.</span><span class="sxs-lookup"><span data-stu-id="2535a-118">-   Create iterative processes to automate manual tasks.</span></span><br /><span data-ttu-id="2535a-119">-Usar reglas de umbral para automatizar las tareas manuales.</span><span class="sxs-lookup"><span data-stu-id="2535a-119">-   Use threshold rules to automate manual tasks.</span></span>|<span data-ttu-id="2535a-120">-   [Supervisión de aplicaciones e instancias de Host](../technical-guides/monitoring-applications-and-host-instances.md)</span><span class="sxs-lookup"><span data-stu-id="2535a-120">-   [Monitoring Applications and Host Instances](../technical-guides/monitoring-applications-and-host-instances.md)</span></span><br /><span data-ttu-id="2535a-121">-   [Supervisión de BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md)</span><span class="sxs-lookup"><span data-stu-id="2535a-121">-   [Monitoring BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md)</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="2535a-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2535a-122">In This Section</span></span>  
  
-   [<span data-ttu-id="2535a-123">Supervisar el uso de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="2535a-123">Monitoring Disk Space Usage</span></span>](../technical-guides/monitoring-disk-space-usage.md)