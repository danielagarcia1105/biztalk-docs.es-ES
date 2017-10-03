---
title: "Cómo actualizar artefactos de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Update-All command [BAM]
- managing [BAM definitions], updating artifacts
- updating, artifacts
- artifacts, updating
ms.assetid: bc28159e-df51-499b-bd51-7b682b849891
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e377a455089127c9dc219846ec3f66e3322924cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-bam-artifacts"></a><span data-ttu-id="97f3c-102">Cómo actualizar artefactos de BAM</span><span class="sxs-lookup"><span data-stu-id="97f3c-102">How to Update BAM Artifacts</span></span>
<span data-ttu-id="97f3c-103">Los administradores utilizan el **update-all** comando para actualizar artefactos implementados en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="97f3c-103">Administrators use the **update-all** command to update artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="97f3c-104">La definición de BAM proporcionada es un archivo XML o un libro de Excel con información relativa a los artefactos que deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="97f3c-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be updated.</span></span>  
  
### <a name="to-update-bam-artifacts"></a><span data-ttu-id="97f3c-105">Para actualizar artefactos de BAM</span><span class="sxs-lookup"><span data-stu-id="97f3c-105">To update BAM Artifacts</span></span>  
  
1.  <span data-ttu-id="97f3c-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97f3c-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="97f3c-107">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="97f3c-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="97f3c-108">Tipo de **bm update-all - DefinitionFile:\<archivo def >**.</span><span class="sxs-lookup"><span data-stu-id="97f3c-108">Type **bm update-all -DefinitionFile:\<def file>**.</span></span>  
  
4.  <span data-ttu-id="97f3c-109">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="97f3c-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f3c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="97f3c-110">See Also</span></span>  
 <span data-ttu-id="97f3c-111">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="97f3c-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="97f3c-112">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="97f3c-112">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="97f3c-113">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="97f3c-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)