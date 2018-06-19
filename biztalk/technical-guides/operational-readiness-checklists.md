---
title: Listas de comprobación de preparación operativa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9e9297e5539fd95f316ebbf6239a5d017ec4ecf
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "23450229"
---
# <a name="operational-readiness-checklists"></a><span data-ttu-id="94b97-102">Listas de comprobación de preparación operativa</span><span class="sxs-lookup"><span data-stu-id="94b97-102">Operational Readiness Checklists</span></span>
<span data-ttu-id="94b97-103">Las listas de comprobación de preparación operativa contienen recomendaciones que debe tener en cuenta y las tareas que se deben realizar antes de implementar una solución de BizTalk en producción.</span><span class="sxs-lookup"><span data-stu-id="94b97-103">The Operational Readiness checklists contain recommendations that you should consider and tasks that you should perform before deploying a BizTalk solution into production.</span></span> <span data-ttu-id="94b97-104">Estas listas de comprobación incluyen información para configurar el software de requisito previo, aumentar la disponibilidad, supervisión de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno y procedimientos para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="94b97-104">These checklists include information for configuring prerequisite software, increasing availability, monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, and procedures for testing.</span></span>  
  
 <span data-ttu-id="94b97-105">Dado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mantiene las dependencias en muchas otras tecnologías de Microsoft, debe completar las tareas para cada tecnología dependiente ayudar a garantizar que su producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno se ejecuta sin problemas.</span><span class="sxs-lookup"><span data-stu-id="94b97-105">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] maintains dependencies on so many other Microsoft technologies, you should complete the tasks for each dependent technology to help ensure that your production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment runs smoothly.</span></span>  
  
## <a name="typical-prerequisite-software"></a><span data-ttu-id="94b97-106">Requisitos previos de Software normal</span><span class="sxs-lookup"><span data-stu-id="94b97-106">Typical Prerequisite Software</span></span>  
 <span data-ttu-id="94b97-107">Software requerido para la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma de aplicaciones suele incluir los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="94b97-107">Prerequisite software for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform typically includes the following products:</span></span>  
  
-   <span data-ttu-id="94b97-108">El sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="94b97-108">The Windows operating system</span></span>  
  
-   <span data-ttu-id="94b97-109">SQL Server</span><span class="sxs-lookup"><span data-stu-id="94b97-109">SQL Server</span></span> 
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   <span data-ttu-id="94b97-110">Visual Studio (para fines de desarrollo, no en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="94b97-110">Visual Studio (for development purposes, not at run time)</span></span>  
  
## <a name="additional-components"></a><span data-ttu-id="94b97-111">Componentes adicionales</span><span class="sxs-lookup"><span data-stu-id="94b97-111">Additional Components</span></span>  
 <span data-ttu-id="94b97-112">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma de aplicaciones también puede necesitar varios de los siguientes componentes de software:</span><span class="sxs-lookup"><span data-stu-id="94b97-112">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform may also require several of the following software components:</span></span>  
  
-   <span data-ttu-id="94b97-113">Servicios de Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="94b97-113">Internet Information Services (IIS)</span></span>  
  
-   <span data-ttu-id="94b97-114">SharePoint</span><span class="sxs-lookup"><span data-stu-id="94b97-114">SharePoint</span></span>
  
-   <span data-ttu-id="94b97-115">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="94b97-115">Microsoft Office Excel</span></span> 
  
    > [!NOTE]  
    >  <span data-ttu-id="94b97-116">BizTalk Server admite solo la versión de 32 bits de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="94b97-116">BizTalk Server supports only the 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="94b97-117">SQL Server</span><span class="sxs-lookup"><span data-stu-id="94b97-117">SQL Server</span></span>
  
-   <span data-ttu-id="94b97-118">SQLXML</span><span class="sxs-lookup"><span data-stu-id="94b97-118">SQLXML</span></span> 
  
-   <span data-ttu-id="94b97-119">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="94b97-119">.NET Framework</span></span> 
  
-   <span data-ttu-id="94b97-120">Los componentes no son de Microsoft para habilitar la funcionalidad para determinados [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores.</span><span class="sxs-lookup"><span data-stu-id="94b97-120">Non-Microsoft components to enable functionality for certain [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
 <span data-ttu-id="94b97-121">Para obtener más información acerca del software de dependencia que se requiere para características específicas de la plataforma de aplicaciones de BizTalk para las distintas versiones de sistema operativo de Windows, vea [¿qué es nuevo, instalación, configuración y actualización](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="94b97-121">For more information about the dependency software that is required for specific features of the BizTalk application platform for various Windows operating system versions, see [What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
- 
  
## <a name="next-steps"></a><span data-ttu-id="94b97-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="94b97-122">Next steps</span></span>
  
-   [<span data-ttu-id="94b97-123">Lista de comprobación: introducción a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="94b97-123">Checklist: Getting Started with BizTalk Server</span></span>](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [<span data-ttu-id="94b97-124">Lista de comprobación: configuración de Windows Server</span><span class="sxs-lookup"><span data-stu-id="94b97-124">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [<span data-ttu-id="94b97-125">Lista de comprobación: configuración de Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="94b97-125">Checklist: Configuring Internet Information Services</span></span>](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [<span data-ttu-id="94b97-126">Lista de comprobación: configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="94b97-126">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [<span data-ttu-id="94b97-127">Lista de comprobación: configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="94b97-127">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [<span data-ttu-id="94b97-128">Lista de comprobación: proporcionar una alta disponibilidad con la tolerancia a errores o el equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="94b97-128">Checklist: Providing High Availability with Fault Tolerance or Load Balancing</span></span>](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [<span data-ttu-id="94b97-129">Lista de comprobación: aumento de la disponibilidad con la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="94b97-129">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [<span data-ttu-id="94b97-130">Lista de comprobación: supervisión de la preparación operativa</span><span class="sxs-lookup"><span data-stu-id="94b97-130">Checklist: Monitoring Operational Readiness</span></span>](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [<span data-ttu-id="94b97-131">Lista de comprobación: mantenimiento y solución de problemas de las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="94b97-131">Checklist: Maintaining and Troubleshooting BizTalk Server Databases</span></span>](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="94b97-132">Lista de comprobación: probar la preparación operativa</span><span class="sxs-lookup"><span data-stu-id="94b97-132">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)