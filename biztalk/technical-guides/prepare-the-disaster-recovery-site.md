---
title: "Preparar el sitio de recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b66f3c8-afe0-4ac0-b925-8f780d14bd4b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2119de8d5f8625943374d262b063491d2dafa6d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-the-disaster-recovery-site"></a><span data-ttu-id="5d81a-102">Preparar el sitio de recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="5d81a-102">Prepare the Disaster Recovery Site</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="5d81a-103">trasvase de registros tiene dos escenarios admitidos.</span><span class="sxs-lookup"><span data-stu-id="5d81a-103"> log shipping has two supported scenarios.</span></span> <span data-ttu-id="5d81a-104">Uno es donde inician sesión envío para todas las bases de datos en todas las instancias de producción de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se aplica a una instancia de la recuperación ante desastres única de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d81a-104">One is where log shipping for all databases on all production instances of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a single disaster recovery instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="5d81a-105">El otro escenario es donde trasvase de registros de las bases de datos para cada instancia de producción de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se aplica a una instancia correspondiente de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en el sitio de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="5d81a-105">The other scenario is where log shipping for the databases for each production instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a corresponding instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] at the disaster recovery site.</span></span> <span data-ttu-id="5d81a-106">Tenga en cuenta que es totalmente compatible para que tenga el mismo número de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias en el sitio de recuperación ante desastres de bases de datos porque hay en producción, pero en menos servidores físicos.</span><span class="sxs-lookup"><span data-stu-id="5d81a-106">Note that it is fully supported to have the same number of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances in the disaster recovery site as there is in production but on fewer physical servers.</span></span> <span data-ttu-id="5d81a-107">Esta sección proporciona instrucciones sobre estos preparativos.</span><span class="sxs-lookup"><span data-stu-id="5d81a-107">This section provides guidance on these preparations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d81a-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5d81a-108">In This Section</span></span>  
  
-   [<span data-ttu-id="5d81a-109">Preparar los servidores SQL de recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="5d81a-109">Preparing the Disaster Recovery SQL Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [<span data-ttu-id="5d81a-110">Copia de seguridad el análisis BAM y las bases de datos del servidor de análisis de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5d81a-110">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [<span data-ttu-id="5d81a-111">Preparar los servidores de BizTalk de recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="5d81a-111">Preparing the Disaster Recovery BizTalk Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [<span data-ttu-id="5d81a-112">Preparar las aplicaciones para la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="5d81a-112">Preparing Applications for Disaster Recovery</span></span>](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [<span data-ttu-id="5d81a-113">Cómo restaurar el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="5d81a-113">How to Restore the Master Secret Server</span></span>](../technical-guides/how-to-restore-the-master-secret-server.md)