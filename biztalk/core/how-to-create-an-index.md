---
title: Cómo crear un índice | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Create-Index command [BAM]
- indexes [BAM], creating
- indexes [BAM], aggregations
- creating, indexes [BAM]
- aggregations [BAM], indexes
ms.assetid: 456d94e6-2e84-4d12-ad38-49f9eeb103f3
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61c0393beae4883359d71915543b629e41c5f6ec
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969290"
---
# <a name="how-to-create-an-index"></a><span data-ttu-id="9e2e8-102">Cómo crear un índice</span><span class="sxs-lookup"><span data-stu-id="9e2e8-102">How to Create an Index</span></span>
<span data-ttu-id="9e2e8-103">Los administradores utilizan el **índice crear** comando para crear un índice en la actividad especificada en los puntos de control especificados.</span><span class="sxs-lookup"><span data-stu-id="9e2e8-103">Administrators use the **create-index** command to create an index on the specified activity at the specified checkpoints.</span></span>  
  
### <a name="to-create-an-index-on-an-activity"></a><span data-ttu-id="9e2e8-104">Para crear un índice en una actividad</span><span class="sxs-lookup"><span data-stu-id="9e2e8-104">To create an index on an activity</span></span>  
  
1.  <span data-ttu-id="9e2e8-105">Desde un símbolo del sistema, vaya al directorio siguiente: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e2e8-105">From a command prompt, browse to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
2.  <span data-ttu-id="9e2e8-106">Tipo de **bm crear-index - IndexName:\<nombre del índice\> -actividad:\<nombre de la actividad\> -punto de comprobación:\<punto de Control1\>**.</span><span class="sxs-lookup"><span data-stu-id="9e2e8-106">Type **bm create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e2e8-107">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9e2e8-107">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
3.  <span data-ttu-id="9e2e8-108">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="9e2e8-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e2e8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e2e8-109">See Also</span></span>  
 <span data-ttu-id="9e2e8-110">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="9e2e8-110">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="9e2e8-111">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="9e2e8-111">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="9e2e8-112">[Cómo eliminar un índice](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="9e2e8-112">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="9e2e8-113">Cómo obtener una lista de índices en una agregación</span><span class="sxs-lookup"><span data-stu-id="9e2e8-113">How to Get a List of Indexes on an Aggregation</span></span>](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)