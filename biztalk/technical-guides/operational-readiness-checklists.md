---
title: "Listas de comprobación de preparación operativa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87da295129a4cb90ecf643cd06eb18ac3e6aa18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operational-readiness-checklists"></a><span data-ttu-id="f050a-102">Listas de comprobación de preparación operativa</span><span class="sxs-lookup"><span data-stu-id="f050a-102">Operational Readiness Checklists</span></span>
<span data-ttu-id="f050a-103">Las listas de comprobación de preparación operativa contienen recomendaciones que debe tener en cuenta y las tareas que se deben realizar antes de implementar una solución de BizTalk en producción.</span><span class="sxs-lookup"><span data-stu-id="f050a-103">The Operational Readiness checklists contain recommendations that you should consider and tasks that you should perform before deploying a BizTalk solution into production.</span></span> <span data-ttu-id="f050a-104">Estas listas de comprobación incluyen información para configurar el software de requisito previo, aumentar la disponibilidad, supervisión de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno y procedimientos para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="f050a-104">These checklists include information for configuring prerequisite software, increasing availability, monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, and procedures for testing.</span></span>  
  
 <span data-ttu-id="f050a-105">Dado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mantiene las dependencias en muchas otras tecnologías de Microsoft, debe completar las tareas para cada tecnología dependiente ayudar a garantizar que su producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno se ejecuta sin problemas.</span><span class="sxs-lookup"><span data-stu-id="f050a-105">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] maintains dependencies on so many other Microsoft technologies, you should complete the tasks for each dependent technology to help ensure that your production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment runs smoothly.</span></span>  
  
## <a name="typical-prerequisite-software"></a><span data-ttu-id="f050a-106">Requisitos previos de Software normal</span><span class="sxs-lookup"><span data-stu-id="f050a-106">Typical Prerequisite Software</span></span>  
 <span data-ttu-id="f050a-107">Software requerido para la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma de aplicaciones suele incluir los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="f050a-107">Prerequisite software for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform typically includes the following products:</span></span>  
  
-   <span data-ttu-id="f050a-108">El sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="f050a-108">The Windows operating system</span></span>  
  
-   [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]<span data-ttu-id="f050a-109">SP1 o[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f050a-109"> SP1 or [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]<span data-ttu-id="f050a-110">(para fines de desarrollo, no en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="f050a-110"> (for development purposes, not at run time)</span></span>  
  
## <a name="additional-components"></a><span data-ttu-id="f050a-111">Componentes adicionales</span><span class="sxs-lookup"><span data-stu-id="f050a-111">Additional Components</span></span>  
 <span data-ttu-id="f050a-112">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma de aplicaciones también puede necesitar varios de los siguientes componentes de software:</span><span class="sxs-lookup"><span data-stu-id="f050a-112">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform may also require several of the following software components:</span></span>  
  
-   <span data-ttu-id="f050a-113">Servicios de Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="f050a-113">Internet Information Services (IIS)</span></span>  
  
-   <span data-ttu-id="f050a-114">Windows SharePoint® Services 2010</span><span class="sxs-lookup"><span data-stu-id="f050a-114">Windows SharePoint® Services 2010</span></span>  
  
-   <span data-ttu-id="f050a-115">SharePoint Foundation 2010</span><span class="sxs-lookup"><span data-stu-id="f050a-115">SharePoint Foundation 2010</span></span>  
  
-   <span data-ttu-id="f050a-116">Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)</span><span class="sxs-lookup"><span data-stu-id="f050a-116">Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)</span></span>  
  
-   <span data-ttu-id="f050a-117">Windows SharePoint Services 3.0 con SP1 o SP2</span><span class="sxs-lookup"><span data-stu-id="f050a-117">Windows SharePoint Services 3.0 with SP1 or SP2</span></span>  
  
-   <span data-ttu-id="f050a-118">Microsoft Office Excel 2010 o 2007</span><span class="sxs-lookup"><span data-stu-id="f050a-118">Microsoft Office Excel 2010 or 2007</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="f050a-119">admite solo la versión de 32 bits de Microsoft Office 2010.</span><span class="sxs-lookup"><span data-stu-id="f050a-119"> supports only the 32-bit version of Microsoft Office 2010.</span></span>  
  
-   <span data-ttu-id="f050a-120">SQL Server 2005 Notification Services</span><span class="sxs-lookup"><span data-stu-id="f050a-120">SQL Server 2005 Notification Services</span></span>  
  
-   <span data-ttu-id="f050a-121">SQLXML 4.0 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="f050a-121">SQLXML 4.0 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="f050a-122">.NET framework 1.0</span><span class="sxs-lookup"><span data-stu-id="f050a-122">.NET Framework 1.0</span></span>  
  
-   <span data-ttu-id="f050a-123">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="f050a-123">.NET Framework 2.0</span></span>  
  
-   <span data-ttu-id="f050a-124">.NET framework 3.0</span><span class="sxs-lookup"><span data-stu-id="f050a-124">.NET Framework 3.0</span></span>  
  
-   <span data-ttu-id="f050a-125">Microsoft .NET Framework 4 y .net Framework 3.5 con Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f050a-125">Microsoft .NET Framework 4 and .Net Framework 3.5 with Service Pack 1 (SP1)</span></span>  
  
-   <span data-ttu-id="f050a-126">Los componentes no son de Microsoft para habilitar la funcionalidad para determinados [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores.</span><span class="sxs-lookup"><span data-stu-id="f050a-126">Non-Microsoft components to enable functionality for certain [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
 <span data-ttu-id="f050a-127">Para obtener más información acerca del software de dependencia que se requiere para características específicas de la plataforma de aplicaciones de BizTalk para las distintas versiones de sistema operativo de Windows, vea la sección "Matriz de dependencia de características" en el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] instalación y Guía de actualización de la versión de sistema operativo de Windows específica.</span><span class="sxs-lookup"><span data-stu-id="f050a-127">For more information about the dependency software that is required for specific features of the BizTalk application platform for various Windows operating system versions, see the "Feature Dependency Matrix" section in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installation and upgrade guide for the specific Windows operating system version.</span></span> <span data-ttu-id="f050a-128">El [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] están disponibles en las guías de instalación y actualización [http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913).</span><span class="sxs-lookup"><span data-stu-id="f050a-128">The [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installation and upgrade guides are available at [http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f050a-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f050a-129">In This Section</span></span>  
  
-   [<span data-ttu-id="f050a-130">Lista de comprobación: Introducción a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f050a-130">Checklist: Getting Started with BizTalk Server</span></span>](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [<span data-ttu-id="f050a-131">Lista de comprobación: Configurar Windows Server</span><span class="sxs-lookup"><span data-stu-id="f050a-131">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [<span data-ttu-id="f050a-132">Lista de comprobación: Configurar Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="f050a-132">Checklist: Configuring Internet Information Services</span></span>](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [<span data-ttu-id="f050a-133">Lista de comprobación: Configurar SQL Server</span><span class="sxs-lookup"><span data-stu-id="f050a-133">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [<span data-ttu-id="f050a-134">Lista de comprobación: Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f050a-134">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [<span data-ttu-id="f050a-135">Lista de comprobación: Proporcionar una alta disponibilidad con tolerancia a errores o equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="f050a-135">Checklist: Providing High Availability with Fault Tolerance or Load Balancing</span></span>](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [<span data-ttu-id="f050a-136">Lista de comprobación: Aumentar la disponibilidad con recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="f050a-136">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [<span data-ttu-id="f050a-137">Lista de comprobación: Supervisión preparación operativa</span><span class="sxs-lookup"><span data-stu-id="f050a-137">Checklist: Monitoring Operational Readiness</span></span>](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [<span data-ttu-id="f050a-138">Lista de comprobación: Mantenimiento y solución de problemas de las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f050a-138">Checklist: Maintaining and Troubleshooting BizTalk Server Databases</span></span>](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="f050a-139">Lista de comprobación: Probar la preparación operativa</span><span class="sxs-lookup"><span data-stu-id="f050a-139">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)