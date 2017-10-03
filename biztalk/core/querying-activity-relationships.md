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
ms.openlocfilehash: 11570bbf42001ac11b5be61ff7b76d06f3df0889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="querying-activity-relationships"></a><span data-ttu-id="53e12-102">Consultar relaciones de actividades</span><span class="sxs-lookup"><span data-stu-id="53e12-102">Querying Activity Relationships</span></span>
<span data-ttu-id="53e12-103">La información sobre relaciones de actividades está disponible en una vista SQL creada dinámicamente para cada actividad.</span><span class="sxs-lookup"><span data-stu-id="53e12-103">The activity relationship information is available in a dynamically created SQL view for each activity.</span></span> <span data-ttu-id="53e12-104">El nombre de esta vista es</span><span class="sxs-lookup"><span data-stu-id="53e12-104">The name of this view is</span></span>  
  
 <span data-ttu-id="53e12-105">**bam_\<**  *actividad* **> _AllRelationships**</span><span class="sxs-lookup"><span data-stu-id="53e12-105">**bam_\<** *Activity* **>_AllRelationships**</span></span>  
  
 <span data-ttu-id="53e12-106">Donde \< *actividad*> es el atributo de nombre del elemento de actividad en la definición de BAM XML, que es el mismo que el nombre de actividad especificado con el complemento de BAM para Excel.</span><span class="sxs-lookup"><span data-stu-id="53e12-106">Where \<*Activity*> is the Name attribute of the Activity element in the BAM definition XML, which is the same as the Activity name entered using the BAM Add-in for Excel.</span></span>  
  
 <span data-ttu-id="53e12-107">Los eventos de relación tienen lugar en el contexto de una actividad específica.</span><span class="sxs-lookup"><span data-stu-id="53e12-107">The relationship events occur in the context of a specific activity.</span></span> <span data-ttu-id="53e12-108">Por ejemplo, si la relación entre pedido de compra y el envío se produce en el contexto de la actividad de pedido de compra, el registro de relaciones se mostrará en **bam_PurchaseOrder_AllRelationships**, pero no en **bam _Shipment_AllRelationships**.</span><span class="sxs-lookup"><span data-stu-id="53e12-108">For example, if the relationship between Purchase Order and Shipment occurs in the context of the Purchase Order activity, the Relationship record will show up in **bam_PurchaseOrder_AllRelationships**, but not in **bam_Shipment_AllRelationships**.</span></span> <span data-ttu-id="53e12-109">Para obtener más información, consulte [relaciones de actividades](../core/activity-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="53e12-109">For more information, see [Activity Relationships](../core/activity-relationships.md).</span></span>  
  
 <span data-ttu-id="53e12-110">Para buscar todas las actividades relacionadas con una compra pedido que necesita consultar tanto en la vista **bam_PurchaseOrder_AllRelationships** , así como todas las vistas **bam_\<***OtherActivity*  **> _AllRelationships**, donde \< *OtherActivity*> es la actividad en la misma vista BAM.</span><span class="sxs-lookup"><span data-stu-id="53e12-110">To find all the related activities to a purchase order you need to query both the view **bam_PurchaseOrder_AllRelationships** as well as all views **bam_\<***OtherActivity***>_AllRelationships**, where \<*OtherActivity*> is the activity in the same BAM view.</span></span>  
  
 <span data-ttu-id="53e12-111">Los registros de relación forman parte de la instancia de actividad y se mantienen en la sincronización con los datos de instancia como se describe en [almacenamiento de datos de actividad](../core/activity-data-storage.md).</span><span class="sxs-lookup"><span data-stu-id="53e12-111">The relationship records are part of the activity instance and they are maintained in synchronization with the instance data as described in [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e12-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="53e12-112">See Also</span></span>  
 [<span data-ttu-id="53e12-113">Consultar datos de BAM</span><span class="sxs-lookup"><span data-stu-id="53e12-113">Querying BAM Data</span></span>](../core/querying-bam-data.md)