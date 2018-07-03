---
title: Cómo obtener una lista de índices de una agregación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- indexes [BAM], listing indexes
- aggregations [BAM], listing indexes
- Get-Index command [BAM]
ms.assetid: 46a4a2fc-10f8-499c-bf2a-d0a19bb84151
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c2d898237482550fda5304f9fd4731b6e06200
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020106"
---
# <a name="how-to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="c0acc-102">Cómo obtener una lista de índices de una agregación</span><span class="sxs-lookup"><span data-stu-id="c0acc-102">How to Get a List of Indexes on an Aggregation</span></span>
<span data-ttu-id="c0acc-103">Los administradores utilizan el **get-index** comando para obtener una lista de todos los índices de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="c0acc-103">Administrators use the **get-index** command to get a list of all the indexes on the specified activity.</span></span>  
  
### <a name="to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="c0acc-104">Para obtener una lista de índices de una agregación</span><span class="sxs-lookup"><span data-stu-id="c0acc-104">To get a list of indexes on an aggregation</span></span>  
  
1. <span data-ttu-id="c0acc-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c0acc-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="c0acc-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="c0acc-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="c0acc-107">Tipo **bm get-index-actividad:\<nombre de la actividad\>**.</span><span class="sxs-lookup"><span data-stu-id="c0acc-107">Type **bm get-index -Activity:\<activity name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c0acc-108">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="c0acc-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="c0acc-109">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="c0acc-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0acc-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0acc-110">See Also</span></span>  
 <span data-ttu-id="c0acc-111">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="c0acc-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="c0acc-112">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c0acc-112">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="c0acc-113">[Cómo eliminar un índice](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="c0acc-113">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="c0acc-114">Cómo crear un índice</span><span class="sxs-lookup"><span data-stu-id="c0acc-114">How to Create an Index</span></span>](../core/how-to-create-an-index.md)