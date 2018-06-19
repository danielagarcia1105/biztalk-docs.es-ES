---
title: Infraestructura dinámica de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, BAM
- BAM, infrastructure
ms.assetid: 88f39438-3213-4f0d-8b8d-e6426c266138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3660eeb6f85fb21ff78b7b833b21adbb3af87385
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230452"
---
# <a name="bam-dynamic-infrastructure"></a><span data-ttu-id="2ee1d-102">Infraestructura dinámica de BAM</span><span class="sxs-lookup"><span data-stu-id="2ee1d-102">BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="2ee1d-103">La infraestructura de BAM consta de tablas de SQL Server, vistas de BAM, procedimientos almacenados y paquetes de servicios de transformación de datos (DTS) en las bases de datos BAM (importación principal, archivo, esquema de estrella y análisis) como configurado y administrado mediante incremental implementaciones de definiciones de BAM.</span><span class="sxs-lookup"><span data-stu-id="2ee1d-103">The BAM infrastructure consists of SQL Server tables, BAM views, stored procedures, and Data Transformation Services (DTS) packages in the BAM databases (Primary Import, Archive, Star Schema, and Analysis) as configured and managed through incremental deployments of BAM definitions.</span></span> <span data-ttu-id="2ee1d-104">La infraestructura es donde, en tiempo de ejecución eventos se correlacionan, agregan y, a continuación, están disponibles para consultar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2ee1d-104">The infrastructure is where, at run time, events are correlated, aggregated, and then made available for querying by users.</span></span>  
  
 <span data-ttu-id="2ee1d-105">En esta sección se describen algunos de estos procesos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="2ee1d-105">This section describes some of these infrastructure processes.</span></span> <span data-ttu-id="2ee1d-106">Por ejemplo, una vez que extraiga los datos de interés de sus aplicaciones (la definición de BAM), los puede almacenar para que estén disponibles para consultas.</span><span class="sxs-lookup"><span data-stu-id="2ee1d-106">For example, once you extract the data of interest from your applications (the BAM definition), you can store it so that it is available for queries.</span></span> <span data-ttu-id="2ee1d-107">Asimismo, puede mantener ciertas agregaciones creadas previamente de los datos para realizar consultas agregadas más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="2ee1d-107">Additionally, you can maintain certain pre-created aggregations of the data for faster aggregated queries.</span></span>  
  
 <span data-ttu-id="2ee1d-108">Normalmente, dicha funcionalidad se logra mediante un gran esfuerzo de desarrollo para implementar un almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="2ee1d-108">Typically, you achieve such functionality by an extensive development effort to implement a data warehouse.</span></span> <span data-ttu-id="2ee1d-109">Sin embargo, BAM en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] simplifica este proceso en gran medida al generar de forma automática la infraestructura de SQL y OLAP basada en sus definiciones de actividad y vista.</span><span class="sxs-lookup"><span data-stu-id="2ee1d-109">BAM in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] greatly simplifies this process, however, by automatically generating the SQL and OLAP infrastructure based on your activity and view definitions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ee1d-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ee1d-110">In This Section</span></span>  
  
-   [<span data-ttu-id="2ee1d-111">¿Qué es una definición de BAM?</span><span class="sxs-lookup"><span data-stu-id="2ee1d-111">What Is a BAM Definition?</span></span>](../core/what-is-a-bam-definition.md)  
  
-   [<span data-ttu-id="2ee1d-112">¿Qué es un esquema de definición de BAM?</span><span class="sxs-lookup"><span data-stu-id="2ee1d-112">What Is a BAM Definition Schema?</span></span>](../core/what-is-a-bam-definition-schema.md)  
  
-   [<span data-ttu-id="2ee1d-113">Almacenamiento de datos de actividad</span><span class="sxs-lookup"><span data-stu-id="2ee1d-113">Activity Data Storage</span></span>](../core/activity-data-storage.md)  
  
-   [<span data-ttu-id="2ee1d-114">¿Qué es una agregación?</span><span class="sxs-lookup"><span data-stu-id="2ee1d-114">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)  
  
-   [<span data-ttu-id="2ee1d-115">Consultar datos de BAM</span><span class="sxs-lookup"><span data-stu-id="2ee1d-115">Querying BAM Data</span></span>](../core/querying-bam-data.md)  
  
-   [<span data-ttu-id="2ee1d-116">Limitaciones de la infraestructura BAM</span><span class="sxs-lookup"><span data-stu-id="2ee1d-116">BAM Infrastructure Limitations</span></span>](../core/bam-infrastructure-limitations.md)  
  
-   [<span data-ttu-id="2ee1d-117">Cómo definir alertas fuera de intervalo numérico dimensión en instalaciones que no sean en inglés</span><span class="sxs-lookup"><span data-stu-id="2ee1d-117">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)