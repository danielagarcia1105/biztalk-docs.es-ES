---
title: "Esquema de configuración de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], scaling
- scaling, BAM
- BAM, scaling
- configuration schema [BAM]
ms.assetid: 7eeeb07f-012e-44eb-a8b5-06e374946e2d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b0d73435dc0245c3c3ce2b1574aa5a70b468c60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-configuration-schema"></a><span data-ttu-id="32c97-102">Esquema de configuración de BAM</span><span class="sxs-lookup"><span data-stu-id="32c97-102">BAM Configuration Schema</span></span>
<span data-ttu-id="32c97-103">El esquema de configuración de BAM define un documento XML que contiene información acerca de su estructura, que utiliza la utilidad de administrador de BAM para la implementación.</span><span class="sxs-lookup"><span data-stu-id="32c97-103">The BAM configuration schema defines an XML document that contains information about your infrastructure that the BAM Manager Utility uses for deployment.</span></span> <span data-ttu-id="32c97-104">Puede implementar sus bases de datos en varios servidores para obtener escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="32c97-104">You can deploy your databases to multiple servers for scalability.</span></span> <span data-ttu-id="32c97-105">Para admitir esta escalabilidad, asegúrese de que la configuración del documento XML contiene los diferentes nombres de servidores y parámetros de configuración para las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="32c97-105">To support this scalability, ensure that the BAM configuration XML document contains the different server names and configuration settings for the following databases:</span></span>  
  
-   <span data-ttu-id="32c97-106">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="32c97-106">BAMPrimaryImport</span></span>  
  
-   <span data-ttu-id="32c97-107">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="32c97-107">BAMStarSchema</span></span>  
  
-   <span data-ttu-id="32c97-108">BAMAnalysis</span><span class="sxs-lookup"><span data-stu-id="32c97-108">BAMAnalysis</span></span>  
  
-   <span data-ttu-id="32c97-109">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="32c97-109">BAMArchive</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32c97-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="32c97-110">In This Section</span></span>  
  
-   [<span data-ttu-id="32c97-111">Paquetes DTS de BAM</span><span class="sxs-lookup"><span data-stu-id="32c97-111">BAM DTS Packages</span></span>](../core/bam-dts-packages.md)  
  
## <a name="see-also"></a><span data-ttu-id="32c97-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="32c97-112">See Also</span></span>  
 [<span data-ttu-id="32c97-113">Cambiar la configuración de tiempo de ejecución BAM</span><span class="sxs-lookup"><span data-stu-id="32c97-113">Changing BAM Runtime Settings</span></span>](../core/changing-bam-runtime-settings.md)