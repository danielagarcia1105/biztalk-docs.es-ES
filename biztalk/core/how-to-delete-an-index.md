---
title: "Cómo eliminar un índice | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- indexes [BAM], deleting
- Get-Index command [BAM]
- aggregations [BAM], indexes
ms.assetid: 5f9c7989-3357-451f-8565-1d4b01c1d16a
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9934c333699b853a3e10a0e5ecf212acf17fa6c6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-delete-an-index"></a><span data-ttu-id="d11a5-102">Cómo eliminar un índice</span><span class="sxs-lookup"><span data-stu-id="d11a5-102">How to Delete an Index</span></span>
<span data-ttu-id="d11a5-103">Los administradores utilizan el **delete-index** comando para eliminar un índice en la actividad especificada en los puntos de control especificados.</span><span class="sxs-lookup"><span data-stu-id="d11a5-103">Administrators use the **delete-index** command to delete an index on the specified activity at the specified checkpoints.</span></span>  
  
### <a name="to-delete-an-index-on-an-activity"></a><span data-ttu-id="d11a5-104">Para eliminar un índice de una actividad</span><span class="sxs-lookup"><span data-stu-id="d11a5-104">To delete an index on an activity</span></span>  
  
1.  <span data-ttu-id="d11a5-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d11a5-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d11a5-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d11a5-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="d11a5-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d11a5-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="d11a5-108">Tipo de **bm delete-index - IndexName:\<nombre del índice\> -actividad:\<nombre de la actividad\>**.</span><span class="sxs-lookup"><span data-stu-id="d11a5-108">Type **bm delete-index -IndexName:\<index name\> -Activity:\<activity name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d11a5-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d11a5-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="d11a5-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d11a5-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11a5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d11a5-111">See Also</span></span>  
 <span data-ttu-id="d11a5-112">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="d11a5-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="d11a5-113">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="d11a5-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="d11a5-114">[Cómo eliminar un índice](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="d11a5-114">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="d11a5-115">Cómo obtener una lista de índices en una agregación</span><span class="sxs-lookup"><span data-stu-id="d11a5-115">How to Get a List of Indexes on an Aggregation</span></span>](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)