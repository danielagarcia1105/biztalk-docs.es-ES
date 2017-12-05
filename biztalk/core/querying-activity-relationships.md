---
title: Consultar relaciones de actividades | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, activity relationships
- queries [BAM], relationships
ms.assetid: e3d42b7c-cc11-4707-9095-cfc518902b26
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70c94644e505409f863e5104168740232d57c664
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="querying-activity-relationships"></a><span data-ttu-id="dc3ef-102">Consultar relaciones de actividades</span><span class="sxs-lookup"><span data-stu-id="dc3ef-102">Querying Activity Relationships</span></span>
<span data-ttu-id="dc3ef-103">La información sobre relaciones de actividades está disponible en una vista SQL creada dinámicamente para cada actividad.</span><span class="sxs-lookup"><span data-stu-id="dc3ef-103">The activity relationship information is available in a dynamically created SQL view for each activity.</span></span> <span data-ttu-id="dc3ef-104">El nombre de esta vista es</span><span class="sxs-lookup"><span data-stu-id="dc3ef-104">The name of this view is</span></span>  
  
 <span data-ttu-id="dc3ef-105">**bam_\<**  *actividad*  **\>_AllRelationships**</span><span class="sxs-lookup"><span data-stu-id="dc3ef-105">**bam_\<** *Activity* **\>_AllRelationships**</span></span>  
  
 <span data-ttu-id="dc3ef-106">Donde \< *actividad* \> es el atributo de nombre del elemento de actividad en la definición de BAM XML, que es el mismo que el nombre de actividad especificado con el complemento de BAM para Excel.</span><span class="sxs-lookup"><span data-stu-id="dc3ef-106">Where \<*Activity*\> is the Name attribute of the Activity element in the BAM definition XML, which is the same as the Activity name entered using the BAM Add-in for Excel.</span></span>  
  
 <span data-ttu-id="dc3ef-107">Los eventos de relación tienen lugar en el contexto de una actividad específica.</span><span class="sxs-lookup"><span data-stu-id="dc3ef-107">The relationship events occur in the context of a specific activity.</span></span> <span data-ttu-id="dc3ef-108">Por ejemplo, si la relación entre pedido de compra y el envío se produce en el contexto de la actividad de pedido de compra, el registro de relaciones se mostrará en **bam_PurchaseOrder_AllRelationships**, pero no en **bam _Shipment_AllRelationships**.</span><span class="sxs-lookup"><span data-stu-id="dc3ef-108">For example, if the relationship between Purchase Order and Shipment occurs in the context of the Purchase Order activity, the Relationship record will show up in **bam_PurchaseOrder_AllRelationships**, but not in **bam_Shipment_AllRelationships**.</span></span> <span data-ttu-id="dc3ef-109">Para obtener más información, consulte [relaciones de actividades](../core/activity-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="dc3ef-109">For more information, see [Activity Relationships](../core/activity-relationships.md).</span></span>  
  
 <span data-ttu-id="dc3ef-110">Para buscar todas las actividades relacionadas con una compra pedido que necesita consultar tanto en la vista **bam_PurchaseOrder_AllRelationships** , así como todas las vistas **bam_\<***OtherActivity*   **\>_AllRelationships**, donde \< *OtherActivity* \> es la actividad en la misma vista BAM.</span><span class="sxs-lookup"><span data-stu-id="dc3ef-110">To find all the related activities to a purchase order you need to query both the view **bam_PurchaseOrder_AllRelationships** as well as all views **bam_\<***OtherActivity***\>_AllRelationships**, where \<*OtherActivity*\> is the activity in the same BAM view.</span></span>  
  
 <span data-ttu-id="dc3ef-111">Los registros de relación forman parte de la instancia de actividad y se mantienen en la sincronización con los datos de instancia como se describe en [almacenamiento de datos de actividad](../core/activity-data-storage.md).</span><span class="sxs-lookup"><span data-stu-id="dc3ef-111">The relationship records are part of the activity instance and they are maintained in synchronization with the instance data as described in [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3ef-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc3ef-112">See Also</span></span>  
 [<span data-ttu-id="dc3ef-113">Consulta de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="dc3ef-113">Querying BAM Data</span></span>](../core/querying-bam-data.md)