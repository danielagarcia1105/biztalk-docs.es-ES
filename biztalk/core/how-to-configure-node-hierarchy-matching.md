---
title: Cómo configurar la jerarquía de nodos que coincidan con | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5302e194-cbc7-4d26-b25b-eb4e38abfe23
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eb785793b865e36c5b37bd6b32199ab3e34f5d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009581"
---
# <a name="how-to-configure-node-hierarchy-matching"></a><span data-ttu-id="06be2-102">Cómo configurar coincidencia de jerarquía de nodos</span><span class="sxs-lookup"><span data-stu-id="06be2-102">How to Configure Node Hierarchy Matching</span></span>
<span data-ttu-id="06be2-103">Cuando se crea un vínculo en una asignación, el Asignador de BizTalk crea automáticamente vínculos de compilador para implementar el vínculo diseñado.</span><span class="sxs-lookup"><span data-stu-id="06be2-103">When you create a link in a map, the BizTalk Mapper automatically creates compiler links to implement the link you have drawn.</span></span> <span data-ttu-id="06be2-104">El **vínculos de destino** propiedad de un vínculo controla cómo el asignador de BizTalk dibuja los vínculos de compilador.</span><span class="sxs-lookup"><span data-stu-id="06be2-104">The **Target Links** property of a link controls how the BizTalk Mapper draws the compiler links.</span></span> <span data-ttu-id="06be2-105">En este tema se proporciona información acerca de cómo establecer los vínculos de destino.</span><span class="sxs-lookup"><span data-stu-id="06be2-105">This topic provides information about how to set the target links.</span></span>  
  
 <span data-ttu-id="06be2-106">El **vínculos de origen** propiedad especifica cómo un valor se recupera desde el nodo de origen y se aplica al nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="06be2-106">The **Source Links** property specifies how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="06be2-107">Para obtener información sobre cómo establecer vínculos de origen, vea [cómo establecer el valor del compilador de vínculos de origen](../core/how-to-set-the-source-links-compiler-value.md).</span><span class="sxs-lookup"><span data-stu-id="06be2-107">For information about how to set source links, see [How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06be2-108">Esta operación requiere que se está ejecutando el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="06be2-108">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-set-the-target-links-property"></a><span data-ttu-id="06be2-109">Para establecer la propiedad Vínculos de destino</span><span class="sxs-lookup"><span data-stu-id="06be2-109">To set the Target Links property</span></span>  
  
1. <span data-ttu-id="06be2-110">En la página de cuadrícula de la asignación, haga clic en un enlace el que desee establecer la propiedad de vínculos de destino.</span><span class="sxs-lookup"><span data-stu-id="06be2-110">On the map grid page, click a link to which you want to set the target links property.</span></span>  
  
2. <span data-ttu-id="06be2-111">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] **propiedades** ventana, establezca el **vínculos de destino** propiedad a una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="06be2-111">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**Properties** window, set the **Target Links** property to one of the following choices:</span></span>  
  
   -   <span data-ttu-id="06be2-112">**Vínculos sin formato.**</span><span class="sxs-lookup"><span data-stu-id="06be2-112">**Flatten Links.**</span></span> <span data-ttu-id="06be2-113">Se quita el formato de la jerarquía del nodo de registro de origen en el nodo de registro vinculado del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="06be2-113">The hierarchy in the source record node is flattened to the linked-to-record node in the destination schema.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="06be2-114">De forma predeterminada, el asignador de BizTalk establece el **vínculos de destino** propiedad **Flatten**.</span><span class="sxs-lookup"><span data-stu-id="06be2-114">By default, the BizTalk Mapper sets the **Target Links** property to **Flatten**.</span></span>  
  
   -   <span data-ttu-id="06be2-115">**Coincidir vínculos de arriba abajo.**</span><span class="sxs-lookup"><span data-stu-id="06be2-115">**Match Links Top Down.**</span></span> <span data-ttu-id="06be2-116">La coincidencia de nodos se lleva a cabo nivel a nivel en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="06be2-116">Node matching is performed level-to-level from the top down.</span></span>  
  
   -   <span data-ttu-id="06be2-117">**Coincidir vínculos de abajo arriba.**</span><span class="sxs-lookup"><span data-stu-id="06be2-117">**Match Links Bottom Up.**</span></span> <span data-ttu-id="06be2-118">La coincidencia de nodos se lleva a cabo nivel a nivel en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="06be2-118">Node matching is performed level-to-level from the bottom up.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06be2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="06be2-119">See Also</span></span>  
 <span data-ttu-id="06be2-120">[Coincidencia del nivel jerárquico de nodos](../core/node-hierarchy-level-matching.md) </span><span class="sxs-lookup"><span data-stu-id="06be2-120">[Node-Hierarchy Level Matching](../core/node-hierarchy-level-matching.md) </span></span>  
 <span data-ttu-id="06be2-121">[Vínculos y directivas de compilador](../core/compiler-directives-and-links.md) </span><span class="sxs-lookup"><span data-stu-id="06be2-121">[Compiler Directives and Links](../core/compiler-directives-and-links.md) </span></span>  
 [<span data-ttu-id="06be2-122">Uso de vínculos para especificar asignaciones de registros y campos</span><span class="sxs-lookup"><span data-stu-id="06be2-122">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)