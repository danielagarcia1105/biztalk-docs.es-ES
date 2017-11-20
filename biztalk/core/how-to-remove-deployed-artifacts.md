---
title: "Cómo quitar artefactos implementados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2a134e41c8f94c875498db03866d16a45bb9bc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-deployed-artifacts"></a><span data-ttu-id="c4292-102">Cómo quitar artefactos implementados</span><span class="sxs-lookup"><span data-stu-id="c4292-102">How to Remove Deployed Artifacts</span></span>
<span data-ttu-id="c4292-103">Los administradores utilizan el **remove-all** comando para quitar artefactos implementados en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c4292-103">Administrators use the **remove-all** command to remove artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="c4292-104">La definición de BAM proporcionada es un archivo XML o un libro de Excel con información relativa a los artefactos que deben quitarse.</span><span class="sxs-lookup"><span data-stu-id="c4292-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be removed.</span></span>  
  
### <a name="to-remove-deployed-artifacts"></a><span data-ttu-id="c4292-105">Para quitar artefactos implementados</span><span class="sxs-lookup"><span data-stu-id="c4292-105">To remove deployed artifacts</span></span>  
  
1.  <span data-ttu-id="c4292-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c4292-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="c4292-107">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="c4292-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="c4292-108">Tipo de **bm remove-all - DefinitionFile:\<archivo def >**.</span><span class="sxs-lookup"><span data-stu-id="c4292-108">Type **bm remove-all -DefinitionFile:\<def file>**.</span></span>  
  
4.  <span data-ttu-id="c4292-109">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="c4292-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4292-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4292-110">See Also</span></span>  
 <span data-ttu-id="c4292-111">[Cómo agregar un artefacto de BAM a una aplicación](../core/how-to-add-a-bam-artifact-to-an-application.md) </span><span class="sxs-lookup"><span data-stu-id="c4292-111">[How to Add a BAM Artifact to an Application](../core/how-to-add-a-bam-artifact-to-an-application.md) </span></span>  
 <span data-ttu-id="c4292-112">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="c4292-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="c4292-113">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="c4292-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="c4292-114">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="c4292-114">BAM Management Utility</span></span>](../core/bam-management-utility.md)