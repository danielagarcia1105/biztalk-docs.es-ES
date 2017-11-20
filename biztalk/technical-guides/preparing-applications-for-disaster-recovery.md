---
title: "Preparar las aplicaciones para la recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ef93099-aa6b-424a-a4ce-87d855c6afe3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7028b1386f71f653dfc41b9de2522cdbd8d02126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-applications-for-disaster-recovery"></a><span data-ttu-id="e383a-102">Preparar las aplicaciones para la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="e383a-102">Preparing Applications for Disaster Recovery</span></span>
<span data-ttu-id="e383a-103">Las aplicaciones de BizTalk (archivos binarios y los artefactos de una configuración como ubicaciones de recepción y puertos de envío) se implementan en el grupo de BizTalk de producción cuando se restaura el grupo en el sitio de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="e383a-103">BizTalk applications (binaries and configuration artifacts such as receive locations and send ports) are deployed to the production BizTalk group when the group is restored at the disaster recovery site.</span></span> <span data-ttu-id="e383a-104">Esta configuración deba modificarse dependiendo de si hay ubicaciones de configuración como ubicaciones de recepción y puertos de envío que son específicas de producción.</span><span class="sxs-lookup"><span data-stu-id="e383a-104">This configuration may have to be altered depending on whether there are configuration locations such as receive locations and send ports that are production-specific.</span></span>  
  
 <span data-ttu-id="e383a-105">Para acelerar la restauración de aplicaciones en el sitio de recuperación ante desastres, un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI que instala los archivos binarios en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución deben estar actualizados en la recuperación ante desastres [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e383a-105">To speed the restoration of applications at the disaster recovery site, a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi file that installs the binaries on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers must be kept up-to-date on the disaster recovery [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers.</span></span> <span data-ttu-id="e383a-106">Cuando se restaura el grupo de BizTalk de producción en el sitio de recuperación ante desastres, puede deben instalarse con el fin de configurar la aplicación para los artefactos de específico sobre la recuperación ante desastres, como un archivo de MSI de configuración de aplicación específico sobre la recuperación ante desastres ubicaciones de recepción y puertos de envío, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e383a-106">When the production BizTalk group is restored at the disaster recovery site, a disaster recovery-specific application configuration .msi file may need to be installed in order to configure the application for disaster recovery-specific artifacts, such as receive locations and send ports, as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e383a-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e383a-107">See Also</span></span>  
 [<span data-ttu-id="e383a-108">Implementar una aplicación</span><span class="sxs-lookup"><span data-stu-id="e383a-108">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)