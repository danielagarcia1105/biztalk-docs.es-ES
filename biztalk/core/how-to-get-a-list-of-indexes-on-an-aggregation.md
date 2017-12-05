---
title: "Cómo obtener una lista de índices en una agregación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- indexes [BAM], listing indexes
- aggregations [BAM], listing indexes
- Get-Index command [BAM]
ms.assetid: 46a4a2fc-10f8-499c-bf2a-d0a19bb84151
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad7eabf54dc410ebed143641602599438f376a30
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="64e65-102">Cómo obtener una lista de índices de una agregación</span><span class="sxs-lookup"><span data-stu-id="64e65-102">How to Get a List of Indexes on an Aggregation</span></span>
<span data-ttu-id="64e65-103">Los administradores utilizan el **get-index** comando para obtener una lista de todos los índices de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="64e65-103">Administrators use the **get-index** command to get a list of all the indexes on the specified activity.</span></span>  
  
### <a name="to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="64e65-104">Para obtener una lista de índices de una agregación</span><span class="sxs-lookup"><span data-stu-id="64e65-104">To get a list of indexes on an aggregation</span></span>  
  
1.  <span data-ttu-id="64e65-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="64e65-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="64e65-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="64e65-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="64e65-107">Tipo de **bm get-index-actividad:\<nombre de la actividad\>**.</span><span class="sxs-lookup"><span data-stu-id="64e65-107">Type **bm get-index -Activity:\<activity name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64e65-108">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="64e65-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="64e65-109">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="64e65-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e65-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="64e65-110">See Also</span></span>  
 <span data-ttu-id="64e65-111">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="64e65-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="64e65-112">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="64e65-112">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="64e65-113">[Cómo eliminar un índice](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="64e65-113">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="64e65-114">Cómo crear un índice</span><span class="sxs-lookup"><span data-stu-id="64e65-114">How to Create an Index</span></span>](../core/how-to-create-an-index.md)