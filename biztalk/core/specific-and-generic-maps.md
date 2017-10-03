---
title: "Asignaciones genéricas y específicas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, specific
- maps, generic
ms.assetid: ee26dd13-affb-47c5-961a-f2377129de22
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6ad84e23c3981730ee4cf7655a42d87c46158e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="specific-and-generic-maps"></a><span data-ttu-id="22665-102">Asignaciones genéricas y específicas</span><span class="sxs-lookup"><span data-stu-id="22665-102">Specific and Generic Maps</span></span>
<span data-ttu-id="22665-103">Cuando se crea una asignación que transforma los datos, puede crear un *específico* o un *genérico* mapa.</span><span class="sxs-lookup"><span data-stu-id="22665-103">When you create a map that transforms data, you can create either a *specific* or a *generic* map.</span></span>  
  
 <span data-ttu-id="22665-104">La asignación específica se utiliza para ajustarse a las necesidades de un socio comercial en particular.</span><span class="sxs-lookup"><span data-stu-id="22665-104">You use a specific map to meet the needs of a particular trading partner.</span></span> <span data-ttu-id="22665-105">Utilice una asignación específica cuando tenga necesidades empresariales muy específicas o acuerdos empresariales con su socio comercial.</span><span class="sxs-lookup"><span data-stu-id="22665-105">Use a specific map when you have very specific business needs or business agreements with your trading partner.</span></span> <span data-ttu-id="22665-106">La ventaja de una asignación específica es que se personaliza para adaptarse a las necesidades de las funciones empresariales que tenga con socios comerciales específicos.</span><span class="sxs-lookup"><span data-stu-id="22665-106">The advantage of a specific map is that it is customized to meet the needs of the business functions you have with specific trading partners.</span></span> <span data-ttu-id="22665-107">La desventaja de una asignación específica es que normalmente no puede utilizarse con varios socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="22665-107">The disadvantage of a specific map is that it cannot be used with multiple trading partners.</span></span> <span data-ttu-id="22665-108">Si multiplica el número de socios comerciales por el número de tipos de mensajes diferentes que intercambia con dichos socios comerciales, deberá dedicar suficiente tiempo y recursos para administrar todas las asignaciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="22665-108">If you multiply the number of trading partners by the number of different message types exchanged with those trading partners, you must allocate enough time and resources to manage all of the associated maps.</span></span>  
  
 <span data-ttu-id="22665-109">Las asignaciones genéricas, por otro lado, están diseñadas para utilizarse con varios socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="22665-109">Generic maps, on the other hand, are designed to be used with multiple trading partners.</span></span> <span data-ttu-id="22665-110">Por tanto, en lugar de desarrollar y mantener varios esquemas para un documento empresarial en concreto, crea un esquema para cada tipo de documento empresarial y los utiliza con todos sus socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="22665-110">Therefore, instead of developing and maintaining multiple schemas for a particular business document, you create one schema for each type of business document, and then use them with all of your trading partners.</span></span> <span data-ttu-id="22665-111">Aunque el utilizar una asignación con varios socios comerciales ahorra tiempo y recursos, estas asignaciones no están personalizadas y puede que no se ajusten a las necesidades en todos los casos.</span><span class="sxs-lookup"><span data-stu-id="22665-111">While using one map with multiple trading partners saves time and resources, these maps are not customized and may not be meet the needs of all cases.</span></span>  
  
 <span data-ttu-id="22665-112">Es posible que cree asignaciones específicas y genéricas, en función de la naturaleza de su empresa.</span><span class="sxs-lookup"><span data-stu-id="22665-112">It is likely that you will create both specific and generic maps, depending on the nature of your business.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22665-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="22665-113">See Also</span></span>  
 <span data-ttu-id="22665-114">[Mapas](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="22665-114">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="22665-115">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="22665-115">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)