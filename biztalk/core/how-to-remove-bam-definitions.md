---
title: Cómo quitar definiciones de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], deleting
- deleting, definitions [BAM]
- managing [BAM definitions], deleting definitions
- Remove-All command
ms.assetid: a905f54b-7c55-49b8-809b-030ad65f3e46
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa02b24ed7d0c7ac09162f486df629bf027d13b9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972570"
---
# <a name="how-to-remove-bam-definitions"></a><span data-ttu-id="b0dc8-102">Cómo quitar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="b0dc8-102">How to Remove BAM Definitions</span></span>
<span data-ttu-id="b0dc8-103">Los administradores utilizan el **remove-all** comando de la utilidad de administración de BAM para quitar todas las vistas y tablas de actividad subyacentes para un determinado archivo de definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="b0dc8-103">Administrators use the **remove-all** command of the BAM Management utility to remove all views and underlying activity tables for a particular BAM definition file.</span></span>  
  
### <a name="to-remove-bam-definitions"></a><span data-ttu-id="b0dc8-104">Para quitar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="b0dc8-104">To Remove BAM definitions</span></span>  
  
1.  <span data-ttu-id="b0dc8-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0dc8-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b0dc8-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="b0dc8-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="b0dc8-107">Tipo de **bm remove-all DefinitionFile:\<archivo def\>**.</span><span class="sxs-lookup"><span data-stu-id="b0dc8-107">Type **bm remove-all DefinitionFile:\<def file\>**.</span></span>  
  
4.  <span data-ttu-id="b0dc8-108">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b0dc8-108">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0dc8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0dc8-109">See Also</span></span>  
 <span data-ttu-id="b0dc8-110">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="b0dc8-110">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="b0dc8-111">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="b0dc8-111">BAM Management Utility</span></span>](../core/bam-management-utility.md)