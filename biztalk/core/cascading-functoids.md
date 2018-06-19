---
title: Functoids en cascada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Cascading
- Cascading functoids
ms.assetid: 03c46e7b-be1c-475e-b68b-f9d1d7732fce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5e9cfcad2432eb83c8a251147bac76b20db0bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231012"
---
# <a name="cascading-functoids"></a><span data-ttu-id="dd799-102">Functoids en cascada</span><span class="sxs-lookup"><span data-stu-id="dd799-102">Cascading Functoids</span></span>
<span data-ttu-id="dd799-103">Se dice que los functoids están en cascada cuando un functoid está vinculado a otro functoid antes de estar vinculado a un registro o campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="dd799-103">Functoids are said to be cascaded when one functoid is linked to another functoid before it is linked to a record or field in the destination schema.</span></span> <span data-ttu-id="dd799-104">Por ejemplo, puede crear functoids en cascada en los que dos cadenas concatenadas produzcan una tercera cadena engarzada en un campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="dd799-104">For example, you can create cascading functoids in which two concatenated strings produce a third string fed into a field in the destination schema.</span></span>  
  
 <span data-ttu-id="dd799-105">Cuando cree functoids en cascada, puede hacer múltiples transformaciones consecutivas en la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="dd799-105">When you cascade functoids, you can create multiple, consecutive transformations in the grid page.</span></span> <span data-ttu-id="dd799-106">Aunque no existe límite en el número de functoids que pueden crearse en cascada en una página, utilice esta posibilidad con prudencia.</span><span class="sxs-lookup"><span data-stu-id="dd799-106">While there is no limit to the number of functoids that you can cascade in a page, use cascading wisely.</span></span> <span data-ttu-id="dd799-107">Las cascadas complejas pueden aumentar el tiempo necesario para transformar un mensaje de instancia de entrada en un mensaje de instancia de salida, lo que reduce significativamente el rendimiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd799-107">Complex cascading can increase the time to transform an input instance message into an output instance message, significantly reducing run time performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd799-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd799-108">See Also</span></span>  
 <span data-ttu-id="dd799-109">[Functoids en asignaciones](../core/functoids-in-maps.md) </span><span class="sxs-lookup"><span data-stu-id="dd799-109">[Functoids in Maps](../core/functoids-in-maps.md) </span></span>  
 [<span data-ttu-id="dd799-110">Utilizar Functoids para crear asignaciones más complejas.</span><span class="sxs-lookup"><span data-stu-id="dd799-110">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)