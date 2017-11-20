---
title: "Administración de la infraestructura dinámica de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- infrastructure, managing [BAM]
- managing [BAM], infrastructure
ms.assetid: af8a76b5-407a-484d-aff4-0d911f88313e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 631a6bb3bab613004e11410a382687147e4adad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-the-bam-dynamic-infrastructure"></a><span data-ttu-id="e6e35-102">Administrar la infraestructura dinámica de BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-102">Managing the BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="e6e35-103">Las características de Supervisión de la actividad económica (BAM) utilizan una infraestructura de generación dinámica de SQL y de procesamiento analítico en línea (OLAP).</span><span class="sxs-lookup"><span data-stu-id="e6e35-103">Business Activity Monitoring (BAM) features use a dynamically generated SQL and online analytical processing (OLAP) infrastructure.</span></span> <span data-ttu-id="e6e35-104">Los administradores usan la utilidad de administración de BAM para implementar el libro de definiciones de BAM o archivo XML, que se encargará de desarrollar el analista de negocios.</span><span class="sxs-lookup"><span data-stu-id="e6e35-104">Administrators use the BAM Management utility to deploy the BAM definition workbook or XML file, which the business analyst develops.</span></span>  
  
 <span data-ttu-id="e6e35-105">La infraestructura dinámica de BAM consiste en vistas de libro de BAM, implementaciones de BAM, paquetes de Servicios de transformación de datos (DTS) de BAM y bases de datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="e6e35-105">The BAM dynamic infrastructure consists of the BAM workbook views, BAM deployments, the BAM Data Transformation Services (DTS) packages, and the BAM databases.</span></span> <span data-ttu-id="e6e35-106">Para obtener más información acerca de la infraestructura dinámica de BAM, consulte [infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="e6e35-106">For more information about the BAM dynamic infrastructure, see [BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md).</span></span>  
  
 <span data-ttu-id="e6e35-107">BizTalk Server crea las siguientes bases de datos BAM al configurar [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e6e35-107">BizTalk Server creates the following BAM databases when you configure [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]:</span></span>  
  
-   <span data-ttu-id="e6e35-108">Base de datos de importación principal de BAM BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="e6e35-108">BAM Primary Import (BAMPrimaryImport) database</span></span>  
  
-   <span data-ttu-id="e6e35-109">Base de datos de esquema de estrella BAMStarSchema (opcional)</span><span class="sxs-lookup"><span data-stu-id="e6e35-109">BAM Star Schema (BAMStarSchema) database (optional)</span></span>  
  
-   <span data-ttu-id="e6e35-110">Base de datos de análisis de BAM BAMAnalysis (opcional)</span><span class="sxs-lookup"><span data-stu-id="e6e35-110">BAM Analysis (BAMAnalysis) database (optional)</span></span>  
  
-   <span data-ttu-id="e6e35-111">Base de datos de archivo de BAM (BAMArchive)</span><span class="sxs-lookup"><span data-stu-id="e6e35-111">BAM Archive (BAMArchive) database</span></span>  
  
 <span data-ttu-id="e6e35-112">Para obtener información acerca de las bases de datos BAM, consulte [administrar bases de datos de BAM](../core/managing-bam-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e6e35-112">For information about the BAM databases, see [Managing BAM Databases](../core/managing-bam-databases.md).</span></span>  
  
 <span data-ttu-id="e6e35-113">En esta sección se describen las tareas que llevan a cabo los administradores para la administración de la infraestructura de BAM:</span><span class="sxs-lookup"><span data-stu-id="e6e35-113">Administrators perform the following management tasks for the BAM infrastructure, which are described in this section:</span></span>  
  
-   <span data-ttu-id="e6e35-114">Implementar y anular la implementación de definiciones y vistas de BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-114">Deploy and undeploy BAM definitions and views</span></span>  
  
-   <span data-ttu-id="e6e35-115">Administrar el acceso de los usuarios a las vistas de BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-115">Manage user access to BAM views</span></span>  
  
-   <span data-ttu-id="e6e35-116">Ejecutar los paquetes DTS de BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-116">Run the BAM DTS packages</span></span>  
  
-   <span data-ttu-id="e6e35-117">Realizar copias de seguridad de las bases de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-117">Back up the BAM databases</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6e35-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e6e35-118">In This Section</span></span>  
  
-   [<span data-ttu-id="e6e35-119">Administrar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-119">Managing BAM Definitions</span></span>](../core/managing-bam-definitions.md)
  
-   [<span data-ttu-id="e6e35-120">Administrar la seguridad BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-120">Managing BAM Security</span></span>](../core/managing-bam-security.md)  
  
-   [<span data-ttu-id="e6e35-121">Administrar agregaciones</span><span class="sxs-lookup"><span data-stu-id="e6e35-121">Managing Aggregations</span></span>](../core/managing-aggregations.md) 
  
-   [<span data-ttu-id="e6e35-122">Administrar bases de datos BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-122">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
  
## <a name="see-also"></a><span data-ttu-id="e6e35-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6e35-123">See Also</span></span>  
 [<span data-ttu-id="e6e35-124">Administración de BAM</span><span class="sxs-lookup"><span data-stu-id="e6e35-124">Managing BAM</span></span>](../core/managing-bam.md)