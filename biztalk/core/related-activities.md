---
title: Actividades relacionadas con | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], related activities
- Query Builder [BAM portal], related activities
- queries [BAM], related activities
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
ms.assetid: 141b7943-d244-4810-aa88-12aa4a2b7658
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fea95a74a15c685f2cff202fcf7f04c86244041b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="related-activities"></a><span data-ttu-id="e2bd9-102">Actividades relacionadas</span><span class="sxs-lookup"><span data-stu-id="e2bd9-102">Related Activities</span></span>
<span data-ttu-id="e2bd9-103">El área Actividades relacionadas contiene una lista de actividades que se relacionan con la actividad en la que se basa la consulta.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-103">The Related Activities area contains a list of activities that are related to the activity on which the query is based.</span></span> <span data-ttu-id="e2bd9-104">Un ejemplo de una actividad relacionada para una actividad de pedido de compra serían varias actividades de envío, ya que los artículos de un pedido de compra se pueden entregar en varios envíos.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-104">An example of a related activity for a Purchase Order activity would be multiple Shipment activities, since items on a single purchase order can be delivered in multiple shipments.</span></span>  
  
## <a name="creating-related-activities"></a><span data-ttu-id="e2bd9-105">Crear actividades relacionadas</span><span class="sxs-lookup"><span data-stu-id="e2bd9-105">Creating related activities</span></span>  
 <span data-ttu-id="e2bd9-106">La lista de actividades relacionadas se genera de una de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2bd9-106">The list of related activities is generated in one of two ways:</span></span>  
  
-   <span data-ttu-id="e2bd9-107">Se definen dos actividades y luego se crea una vista única que incluye las dos.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-107">You define two activities and then create a single view that includes both of them.</span></span> <span data-ttu-id="e2bd9-108">El programador realiza una conexión de correlación entre las dos al implementar la clave, el campo y las relaciones de valor entre las actividades.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-108">Your developer makes a correlation connection between the two by implementing the key, field, and value relationships between the activities.</span></span>  
  
-   <span data-ttu-id="e2bd9-109">Se definen dos actividades.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-109">You define two activities.</span></span> <span data-ttu-id="e2bd9-110">El programador realiza una conexión de correlación en su aplicación personalizada llamando a AddRelationship() y definiendo la clave, el campo y las relaciones de valor entre las actividades.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-110">Your developer makes a correlation connection in your custom application by calling AddRelationship() and defining the key, field, and value relationships between the activities.</span></span>  
  
 <span data-ttu-id="e2bd9-111">Definir las relaciones de actividad en cualquiera de estas formas agrega una fila en la \<activityname > _Relationships tabla.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-111">Defining the activity relationships in either of these ways adds a row in the \<activityname>_Relationships table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2bd9-112">solo el primer método de definición de relaciones hace que las actividades relacionadas tengan vínculos activos entre ellas.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-112">Only the first method of defining relationships results in the related activities having live links to each other.</span></span> <span data-ttu-id="e2bd9-113">El segundo método no define una vista de distribución y por tanto, el portal no puede conocer la relación entre las dos actividades.</span><span class="sxs-lookup"><span data-stu-id="e2bd9-113">The second method does not define a spanning view and therefore the portal cannot know about the relationship between the two activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2bd9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2bd9-114">See Also</span></span>  
 [<span data-ttu-id="e2bd9-115">Cómo ver los resultados de una búsqueda de actividad</span><span class="sxs-lookup"><span data-stu-id="e2bd9-115">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)