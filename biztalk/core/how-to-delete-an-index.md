---
title: Cómo eliminar un índice | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- indexes [BAM], deleting
- Get-Index command [BAM]
- aggregations [BAM], indexes
ms.assetid: 5f9c7989-3357-451f-8565-1d4b01c1d16a
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaafdf9515849fb84d569fb50a3e7117f30969b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978333"
---
# <a name="how-to-delete-an-index"></a><span data-ttu-id="c8256-102">Cómo eliminar un índice</span><span class="sxs-lookup"><span data-stu-id="c8256-102">How to Delete an Index</span></span>
<span data-ttu-id="c8256-103">Los administradores utilizan el **delete-index** comando para eliminar un índice en la actividad especificada en los puntos de control especificados.</span><span class="sxs-lookup"><span data-stu-id="c8256-103">Administrators use the **delete-index** command to delete an index on the specified activity at the specified checkpoints.</span></span>  
  
### <a name="to-delete-an-index-on-an-activity"></a><span data-ttu-id="c8256-104">Para eliminar un índice de una actividad</span><span class="sxs-lookup"><span data-stu-id="c8256-104">To delete an index on an activity</span></span>  
  
1. <span data-ttu-id="c8256-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8256-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="c8256-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c8256-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="c8256-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="c8256-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="c8256-108">Tipo **bm delete-index - IndexName:\<nombreDeÍndice\> -actividad:\<nombre de la actividad\>**.</span><span class="sxs-lookup"><span data-stu-id="c8256-108">Type **bm delete-index -IndexName:\<index name\> -Activity:\<activity name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c8256-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="c8256-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="c8256-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="c8256-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8256-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8256-111">See Also</span></span>  
 <span data-ttu-id="c8256-112">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="c8256-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="c8256-113">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c8256-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="c8256-114">[Cómo eliminar un índice](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="c8256-114">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="c8256-115">Cómo obtener una lista de índices de una agregación</span><span class="sxs-lookup"><span data-stu-id="c8256-115">How to Get a List of Indexes on an Aggregation</span></span>](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)