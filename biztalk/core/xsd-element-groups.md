---
title: Grupos de elementos XSD | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XSLT, XSLT variations
- BizTalk Mapper, XSLT variations
- maps, groups
- Choice Group node
- XSD element groups
- XSLT, warnings
ms.assetid: a6ea22cb-6066-480e-8a2a-75fade3e5970
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80b6fdd65067599ed14c37ff00507279ce9b2f47
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006693"
---
# <a name="xsd-element-groups"></a><span data-ttu-id="da22d-102">Grupos de elementos XSD</span><span class="sxs-lookup"><span data-stu-id="da22d-102">XSD Element Groups</span></span>
<span data-ttu-id="da22d-103">La utilización de determinadas estructuras en un esquema puede crear variaciones en la transformación de lenguaje de hojas de estilo extensible (XSLT) que genera el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="da22d-103">The use of certain structures in a schema may create variations in the Extensible Stylesheet Language Transformations (XSLT) that BizTalk Mapper generates.</span></span>  
  
 <span data-ttu-id="da22d-104">Esto puede ocurrir al incluir un esquema en la asignación que defina grupos de secuencias, de elecciones o de todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="da22d-104">This can occur when you include a schema in your map that defines sequence, choice, or all element groups.</span></span> <span data-ttu-id="da22d-105">Por ejemplo, si usa un esquema que incluya un **grupo de elecciones** nodo, es posible crear un mapa que requiere dos o más de los elementos secundarios de la **grupo de elecciones** nodo aparezca en una instancia de salida Mensaje.</span><span class="sxs-lookup"><span data-stu-id="da22d-105">For example, if you use a schema that includes a **Choice Group** node, it is possible for you to create a map that requires two or more of the children of the **Choice Group** node to appear in an output instance message.</span></span> <span data-ttu-id="da22d-106">En este caso, el Asignador de BizTalk muestra una advertencia al compilar la asignación.</span><span class="sxs-lookup"><span data-stu-id="da22d-106">In this case, BizTalk Mapper displays a warning when you compile the map.</span></span> <span data-ttu-id="da22d-107">La advertencia le indica que solo uno de los campos requeridos que ha asignado puede llenarse en la misma iteración del bucle primario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="da22d-107">The warning tells you that only one of the required fields you have mapped may be populated in the same iteration of the parent loop at run time.</span></span> <span data-ttu-id="da22d-108">El Asignador de BizTalk no le mostrará un error para indicarle que la lógica de asignación es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="da22d-108">BizTalk Mapper does not give you an error message stating that your mapping logic is incorrect.</span></span>  
  
 <span data-ttu-id="da22d-109">Otra situación en la que podría generar variaciones en la XSLT es cuando se cumplen las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="da22d-109">Another situation in which you might generate variations in the XSLT is when the following conditions are met:</span></span>  
  
- <span data-ttu-id="da22d-110">**El registro A** tiene un elemento secundario **B de elemento de campo**.</span><span class="sxs-lookup"><span data-stu-id="da22d-110">**Record A** has a child **Field Element B**.</span></span>  
  
- <span data-ttu-id="da22d-111">**Grabar un** y secundarios **B de elemento de campo** producirse una sola vez.</span><span class="sxs-lookup"><span data-stu-id="da22d-111">**Record A** and child **Field Element B** occur once.</span></span>  
  
- <span data-ttu-id="da22d-112">**El registro A** forma parte de un **grupo de elecciones** que se repite.</span><span class="sxs-lookup"><span data-stu-id="da22d-112">**Record A** is part of a **Choice Group** that repeats.</span></span>  
  
  <span data-ttu-id="da22d-113">En esta situación, el Asignador de BizTalk genera XSLT que contenga lógica de iteración para controlar las muchas variaciones de los registros de origen que podrían producirse.</span><span class="sxs-lookup"><span data-stu-id="da22d-113">In this situation, BizTalk Mapper generates XSLT that contains iteration logic to handle the possibility of the many variations of the source records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da22d-114">Deberá ser explícito con respecto a las asignaciones que impliquen a grupos.</span><span class="sxs-lookup"><span data-stu-id="da22d-114">You must be explicit with respect to mappings involving groups.</span></span> <span data-ttu-id="da22d-115">Por ejemplo, si un esquema de destino contiene un **grupo de elecciones** nodo con los nodos secundarios A y B, no es válido tener a y B simultáneamente en la misma iteración de su grupo primario.</span><span class="sxs-lookup"><span data-stu-id="da22d-115">For example, if a destination schema contains a **Choice Group** node with child nodes A and B, it is not valid to have A and B simultaneously on the same iteration of their parent group.</span></span> <span data-ttu-id="da22d-116">El Asignador de BizTalk no evita que cree asignaciones que no son válidas.</span><span class="sxs-lookup"><span data-stu-id="da22d-116">BizTalk Mapper does not prevent you from creating mappings that are not valid.</span></span> <span data-ttu-id="da22d-117">Por lo tanto, deberá utilizar functoids lógicos para configurar asignaciones en las que A y B nunca aparezcan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="da22d-117">Therefore, you must use logical functoids to set up mappings in which A and B can never occur at the same time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da22d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="da22d-118">See Also</span></span>  
 <span data-ttu-id="da22d-119">[Mapas](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="da22d-119">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="da22d-120">Creación de mapas con el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="da22d-120">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)