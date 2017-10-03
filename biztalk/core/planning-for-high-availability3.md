---
title: "Planeación de alta Availability3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- high availability
- planning, high availability
- high availability, architecture
ms.assetid: 16feada0-b0b1-4e58-9477-fbd1aae2f51e
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a6a8a69af5fd1ff59a4e69e02a52124d89db1ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-high-availability"></a><span data-ttu-id="c125c-102">Planear la alta disponibilidad</span><span class="sxs-lookup"><span data-stu-id="c125c-102">Planning for High Availability</span></span>
<span data-ttu-id="c125c-103">Muchas compañías usan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para procesar los datos de los que depende su actividad.</span><span class="sxs-lookup"><span data-stu-id="c125c-103">Many companies use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process data that their business depends on.</span></span> <span data-ttu-id="c125c-104">Para estas compañías, las consecuencias de un período de inactividad prolongado a causa de una avería del hardware pueden suponer la disminución de la productividad y la rentabilidad.</span><span class="sxs-lookup"><span data-stu-id="c125c-104">For these companies, the consequences of a prolonged downtime because of a hardware outage can mean diminished productivity and profitability.</span></span> <span data-ttu-id="c125c-105">En esta sección se proporcionan directrices para aumentar la disponibilidad de su entorno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con el fin de maximizar el tiempo de uso de la solución [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c125c-105">This section provides guidance for increasing availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment in order to maximize uptime of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c125c-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c125c-106">In This Section</span></span>  
-   [<span data-ttu-id="c125c-107">Alta disponibilidad mediante SQL Server grupos de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c125c-107">High Availability using SQL Server Always On Availability Groups</span></span>](../core/high-availability-using-sql-server-always-on-availability-groups.md)
  
-   [<span data-ttu-id="c125c-108">Planear la plataforma para tolerancia a errores</span><span class="sxs-lookup"><span data-stu-id="c125c-108">Planning Your Platform for Fault Tolerance</span></span>](../core/planning-your-platform-for-fault-tolerance.md)  
  
-   [<span data-ttu-id="c125c-109">Crear un entorno de alta disponibilidad de servidor de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c125c-109">Creating a Highly Available BizTalk Server Environment</span></span>](../core/creating-a-highly-available-biztalk-server-environment.md)  
  
-   [<span data-ttu-id="c125c-110">Escenarios de alta disponibilidad de servidor BizTalk Server de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c125c-110">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)  
  
-   [<span data-ttu-id="c125c-111">Alta disponibilidad para el inicio de sesión único empresarial</span><span class="sxs-lookup"><span data-stu-id="c125c-111">High Availability for Enterprise Single Sign-On</span></span>](../core/high-availability-for-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="c125c-112">Alta disponibilidad y Microsoft Operations Framework</span><span class="sxs-lookup"><span data-stu-id="c125c-112">High Availability and the Microsoft Operations Framework</span></span>](../core/high-availability-and-the-microsoft-operations-framework.md)  
  
## <a name="reference"></a><span data-ttu-id="c125c-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="c125c-113">Reference</span></span>  
  
-   <span data-ttu-id="c125c-114">[Introducción a los clústeres de conmutación por error SQL Server 2008](http://go.microsoft.com/fwlink/?LinkId=130375) (http://go.microsoft.com/fwlink/?LinkId=130375)</span><span class="sxs-lookup"><span data-stu-id="c125c-114">[Getting Started with SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=130375) (http://go.microsoft.com/fwlink/?LinkId=130375)</span></span>  
  
-   <span data-ttu-id="c125c-115">[Notas del producto: SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=189522) (http://go.microsoft.com/fwlink/?LinkId=189522)</span><span class="sxs-lookup"><span data-stu-id="c125c-115">[White Paper: SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=189522) (http://go.microsoft.com/fwlink/?LinkId=189522)</span></span>  
  
-   <span data-ttu-id="c125c-116">[Guías paso a paso de Windows Server 2008](http://go.microsoft.com/fwlink/?LinkId=189545) (http://go.microsoft.com/fwlink/?LinkId=189545)</span><span class="sxs-lookup"><span data-stu-id="c125c-116">[Windows Server 2008 Step-by-Step Guides](http://go.microsoft.com/fwlink/?LinkId=189545) (http://go.microsoft.com/fwlink/?LinkId=189545)</span></span>