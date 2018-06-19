---
title: Mantener BizTalk Server2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b9c10d1-101b-4b9d-8eab-767b853f17d8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2d1b171f0506d7855d5faf23f2ebea393d21f60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298372"
---
# <a name="maintaining-biztalk-server2"></a><span data-ttu-id="c1b26-102">Mantener BizTalk Server2</span><span class="sxs-lookup"><span data-stu-id="c1b26-102">Maintaining BizTalk Server2</span></span>
<span data-ttu-id="c1b26-103">Las actividades de mantenimiento forman parte de la función de administración de sistema (SMC) de Control y supervisión del servicio tal como se define por Microsoft Operations Framework (MOF).</span><span class="sxs-lookup"><span data-stu-id="c1b26-103">Maintenance activities are part of the Service Monitoring and Control (SMC) system management function as defined by the Microsoft Operations Framework (MOF).</span></span> <span data-ttu-id="c1b26-104">El objetivo principal de SMC es observa el estado de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.</span><span class="sxs-lookup"><span data-stu-id="c1b26-104">The primary goal of SMC is to observe the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="c1b26-105">Comprobaciones SMC pueden iniciar acciones correctoras para evitar posibles incidentes de servicio y minimizar el impacto de los incidentes de servicio cuando se producen.</span><span class="sxs-lookup"><span data-stu-id="c1b26-105">SMC checks may initiate remedial actions to avoid potential service incidents and to minimize the impact of service incidents when they do occur.</span></span>  
  
 <span data-ttu-id="c1b26-106">Para los fines de esta sección de la guía, las actividades SMC se dividen en cuatro tres amplias categorías: confiabilidad, administración, seguridad y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c1b26-106">For the purposes of this section of the guide, SMC activities are divided into four three broad categories: reliability, administration, security, and performance.</span></span> <span data-ttu-id="c1b26-107">Las listas de comprobación de mantenimiento diarias, semanales y mensuales organizan SMC comprobaciones según la frecuencia con la que se realizará cada comprobación.</span><span class="sxs-lookup"><span data-stu-id="c1b26-107">The daily, weekly, and monthly maintenance checklists organize SMC checks according to how frequently each check should be performed.</span></span> <span data-ttu-id="c1b26-108">Si las comprobaciones de SMC indican que la acción correctora es necesaria, las listas de comprobación le ayudará a fuentes de información adicional para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="c1b26-108">If SMC checks indicate that remedial action is necessary, the checklists will direct you to sources of additional information to resolve the problem.</span></span>  
  
 <span data-ttu-id="c1b26-109">Las secciones que pertenecen a la resolución de confiabilidad, problemas de administración, seguridad y rendimiento contienen información sobre cómo identificar y resolver muchos problemas comunes detectados durante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operaciones.</span><span class="sxs-lookup"><span data-stu-id="c1b26-109">The sections pertaining to resolving reliability, administration, security, and performance issues contain information about identifying and resolving many common problems encountered during [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operations.</span></span>  
  
 <span data-ttu-id="c1b26-110">Para obtener más información acerca de Microsoft Operations Framework, consulte [http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047).</span><span class="sxs-lookup"><span data-stu-id="c1b26-110">For more information about the Microsoft Operations Framework, see [http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047).</span></span> <span data-ttu-id="c1b26-111">Para obtener más información acerca de la función de Control y la supervisión, consulte [http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341).</span><span class="sxs-lookup"><span data-stu-id="c1b26-111">For more information about the Service Monitoring and Control function, see [http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1b26-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c1b26-112">In This Section</span></span>  
  
-   [<span data-ttu-id="c1b26-113">Mantenimiento de la confiabilidad</span><span class="sxs-lookup"><span data-stu-id="c1b26-113">Maintaining Reliability</span></span>](../technical-guides/maintaining-reliability.md)  
  
-   [<span data-ttu-id="c1b26-114">Mantenimiento administrativo</span><span class="sxs-lookup"><span data-stu-id="c1b26-114">Administrative Maintenance</span></span>](../technical-guides/administrative-maintenance.md)  
  
-   [<span data-ttu-id="c1b26-115">Mantener el rendimiento</span><span class="sxs-lookup"><span data-stu-id="c1b26-115">Maintaining Performance</span></span>](../technical-guides/maintaining-performance.md)  
  
-   [<span data-ttu-id="c1b26-116">Mantener bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c1b26-116">Maintaining BizTalk Server Databases</span></span>](../technical-guides/maintaining-biztalk-server-databases.md)  
  
## <a name="related-sections"></a><span data-ttu-id="c1b26-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c1b26-117">Related Sections</span></span>  
 [<span data-ttu-id="c1b26-118">Lista de comprobación: Realización de comprobaciones de mantenimiento diario</span><span class="sxs-lookup"><span data-stu-id="c1b26-118">Checklist: Performing Daily Maintenance Checks</span></span>](../technical-guides/checklist-performing-daily-maintenance-checks.md)  
  
 [<span data-ttu-id="c1b26-119">Lista de comprobación: Realización de comprobaciones de mantenimiento semanal</span><span class="sxs-lookup"><span data-stu-id="c1b26-119">Checklist: Performing Weekly Maintenance Checks</span></span>](../technical-guides/checklist-performing-weekly-maintenance-checks.md)  
  
 [<span data-ttu-id="c1b26-120">Lista de comprobación: Realización de comprobaciones de mantenimiento mensual</span><span class="sxs-lookup"><span data-stu-id="c1b26-120">Checklist: Performing Monthly Maintenance Checks</span></span>](../technical-guides/checklist-performing-monthly-maintenance-checks.md)