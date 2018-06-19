---
title: Cómo quitar artefactos implementados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1d3e395223840dd4caa534130061fac33e89b78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970194"
---
# <a name="how-to-remove-deployed-artifacts"></a><span data-ttu-id="1d62d-102">Cómo quitar artefactos implementados</span><span class="sxs-lookup"><span data-stu-id="1d62d-102">How to Remove Deployed Artifacts</span></span>
<span data-ttu-id="1d62d-103">Los administradores utilizan el **remove-all** comando para quitar artefactos implementados en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="1d62d-103">Administrators use the **remove-all** command to remove artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="1d62d-104">La definición de BAM proporcionada es un archivo XML o un libro de Excel con información relativa a los artefactos que deben quitarse.</span><span class="sxs-lookup"><span data-stu-id="1d62d-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be removed.</span></span>  
  
### <a name="to-remove-deployed-artifacts"></a><span data-ttu-id="1d62d-105">Para quitar artefactos implementados</span><span class="sxs-lookup"><span data-stu-id="1d62d-105">To remove deployed artifacts</span></span>  
  
1.  <span data-ttu-id="1d62d-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d62d-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="1d62d-107">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="1d62d-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="1d62d-108">Tipo de **bm remove-all - DefinitionFile:\<archivo def\>**.</span><span class="sxs-lookup"><span data-stu-id="1d62d-108">Type **bm remove-all -DefinitionFile:\<def file\>**.</span></span>  
  
4.  <span data-ttu-id="1d62d-109">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1d62d-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d62d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d62d-110">See Also</span></span>  
 <span data-ttu-id="1d62d-111">[Cómo agregar un artefacto de BAM a una aplicación](../core/how-to-add-a-bam-artifact-to-an-application.md) </span><span class="sxs-lookup"><span data-stu-id="1d62d-111">[How to Add a BAM Artifact to an Application](../core/how-to-add-a-bam-artifact-to-an-application.md) </span></span>  
 <span data-ttu-id="1d62d-112">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="1d62d-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="1d62d-113">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="1d62d-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="1d62d-114">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="1d62d-114">BAM Management Utility</span></span>](../core/bam-management-utility.md)