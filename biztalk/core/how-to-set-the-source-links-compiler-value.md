---
title: "Cómo establecer el origen de vínculos de compilador valor | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61a7adf74d0b186f338220a383da6b6831013312
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-the-source-links-compiler-value"></a><span data-ttu-id="252af-102">Cómo establecer el valor del compilador de vínculos de origen</span><span class="sxs-lookup"><span data-stu-id="252af-102">How to Set the Source Links Compiler Value</span></span>
<span data-ttu-id="252af-103">Puede usar el **vínculos de origen** propiedad de un vínculo para especificar cómo se recuperan desde el nodo de origen y se aplica al nodo de destino un valor.</span><span class="sxs-lookup"><span data-stu-id="252af-103">You can use the **Source Links** property of a link to specify how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="252af-104">En este tema se explican las opciones disponibles y cómo elegir entre ellas.</span><span class="sxs-lookup"><span data-stu-id="252af-104">This topic explains the available choices and how to choose among them.</span></span>  
  
### <a name="to-set-the-source-links-link-property"></a><span data-ttu-id="252af-105">Para establecer la propiedad Vínculos de origen del vínculo</span><span class="sxs-lookup"><span data-stu-id="252af-105">To set the Source Links link property</span></span>  
  
1.  <span data-ttu-id="252af-106">En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="252af-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="252af-107">Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="252af-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="252af-108">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, establezca la **vínculos de origen** propiedad a una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="252af-108">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, set the **Source Links** property to one of the following choices:</span></span>  
  
    -   <span data-ttu-id="252af-109">**Nombre de la copia.**</span><span class="sxs-lookup"><span data-stu-id="252af-109">**Copy Name.**</span></span> <span data-ttu-id="252af-110">Se utiliza el nombre del nodo del esquema de origen como valor del nodo vinculado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="252af-110">The name of the node in the source schema is used as the value of the linked node in the destination schema.</span></span>  
  
    -   <span data-ttu-id="252af-111">**Copiar valor de texto.**</span><span class="sxs-lookup"><span data-stu-id="252af-111">**Copy Text Value.**</span></span> <span data-ttu-id="252af-112">Se utiliza el valor que corresponde al nodo del esquema de origen (datos de elemento o valor de atributo) como valor del nodo vinculado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="252af-112">The value corresponding to the node in the source schema (element data or an attribute value) is used as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="252af-113">Éste es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="252af-113">This choice is the default.</span></span> <span data-ttu-id="252af-114">Por ejemplo, `<Node>Hello<Name>Chris</Name>Barry</Node>` dará como resultado "Hello".</span><span class="sxs-lookup"><span data-stu-id="252af-114">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello".</span></span>  
  
    -   <span data-ttu-id="252af-115">**Copiar valor de subcontenido y texto.**</span><span class="sxs-lookup"><span data-stu-id="252af-115">**Copy Text and Subcontent Value.**</span></span> <span data-ttu-id="252af-116">El valor correspondiente al nodo de registro, el valor de todos sus nodos secundarios y los nodos secundarios de ambos en el esquema de origen (datos de elemento y valores de atributo) se combinan como el valor del nodo vinculado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="252af-116">The value corresponding to the record node, and the value of all its child nodes, and their child nodes, in the source schema (element data and attribute values) are combined as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="252af-117">Por ejemplo, `<Node>Hello<Name>Chris</Name>Barry</Node>` dará como resultado "Hello Chris Barry".</span><span class="sxs-lookup"><span data-stu-id="252af-117">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello Chris Barry".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="252af-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="252af-118">See Also</span></span>  
 <span data-ttu-id="252af-119">[Utilizar vínculos para especificar el registro y las asignaciones de campos](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="252af-119">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="252af-120">Vínculos y directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="252af-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)