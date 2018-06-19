---
title: Optimizar el rendimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bafa119b-187e-4595-a673-358dc0a109b7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e79c318d7cd12d799459535914046da98819561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299100"
---
# <a name="optimizing-performance"></a><span data-ttu-id="2adb5-102">Optimizar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="2adb5-102">Optimizing Performance</span></span>
<span data-ttu-id="2adb5-103">Una instalación predeterminada del sistema operativo Windows, SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y se pueden optimizar significativamente IIS para proporcionar un rendimiento óptimo de una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="2adb5-103">A default installation of the Windows operating system, SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and IIS can be significantly optimized to provide optimal performance for a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="2adb5-104">Parámetros de configuración de WCF también se puede ajustar la configuración predeterminada para proporcionar una mejora significativa del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2adb5-104">WCF configuration parameters can also be tuned from the default settings to provide significantly improved performance.</span></span> <span data-ttu-id="2adb5-105">Esta sección proporciona optimizaciones de rendimiento de específicas que se deben seguir al implementar una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="2adb5-105">This section provides specific performance optimizations that should be followed when deploying a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2adb5-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2adb5-106">In This Section</span></span>  
  
-   [<span data-ttu-id="2adb5-107">Optimizar el rendimiento del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="2adb5-107">Optimizing Operating System Performance</span></span>](../technical-guides/optimizing-operating-system-performance.md)  
  
-   [<span data-ttu-id="2adb5-108">Optimizar el rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="2adb5-108">Optimizing Network Performance</span></span>](../technical-guides/optimizing-network-performance.md)  
  
-   [<span data-ttu-id="2adb5-109">Optimizar el rendimiento de IIS</span><span class="sxs-lookup"><span data-stu-id="2adb5-109">Optimizing IIS Performance</span></span>](../technical-guides/optimizing-iis-performance.md)  
  
-   [<span data-ttu-id="2adb5-110">Optimizar el rendimiento de la base de datos</span><span class="sxs-lookup"><span data-stu-id="2adb5-110">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)  
  
-   [<span data-ttu-id="2adb5-111">Optimizar el rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2adb5-111">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)  
  
-   [<span data-ttu-id="2adb5-112">Optimizar el rendimiento de la orquestación</span><span class="sxs-lookup"><span data-stu-id="2adb5-112">Optimizing Orchestration Performance</span></span>](../technical-guides/optimizing-orchestration-performance.md)  
  
-   [<span data-ttu-id="2adb5-113">Optimizar el rendimiento del servicio Web WCF</span><span class="sxs-lookup"><span data-stu-id="2adb5-113">Optimizing WCF Web Service Performance</span></span>](../technical-guides/optimizing-wcf-web-service-performance.md)  
  
-   [<span data-ttu-id="2adb5-114">Optimizar las aplicaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2adb5-114">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)  
  
-   [<span data-ttu-id="2adb5-115">Scripts de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2adb5-115">Windows PowerShell Scripts</span></span>](../technical-guides/windows-powershell-scripts.md)