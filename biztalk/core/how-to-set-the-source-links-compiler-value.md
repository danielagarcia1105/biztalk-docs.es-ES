---
title: Cómo establecer el origen de vínculos de compilador valor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ad777bc5b4df2717d20fd95aa60fdf5d59d1f6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975173"
---
# <a name="how-to-set-the-source-links-compiler-value"></a><span data-ttu-id="63434-102">Cómo establecer el valor del compilador de vínculos de origen</span><span class="sxs-lookup"><span data-stu-id="63434-102">How to Set the Source Links Compiler Value</span></span>
<span data-ttu-id="63434-103">Puede usar el **vínculos de origen** propiedad de un vínculo para especificar cómo un valor se recupera desde el nodo de origen y se aplica al nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="63434-103">You can use the **Source Links** property of a link to specify how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="63434-104">En este tema se explican las opciones disponibles y cómo elegir entre ellas.</span><span class="sxs-lookup"><span data-stu-id="63434-104">This topic explains the available choices and how to choose among them.</span></span>  
  
### <a name="to-set-the-source-links-link-property"></a><span data-ttu-id="63434-105">Para establecer la propiedad Vínculos de origen del vínculo</span><span class="sxs-lookup"><span data-stu-id="63434-105">To set the Source Links link property</span></span>  
  
1. <span data-ttu-id="63434-106">En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="63434-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
    <span data-ttu-id="63434-107">Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="63434-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2. <span data-ttu-id="63434-108">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, establezca la **vínculos de origen** propiedad a una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="63434-108">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, set the **Source Links** property to one of the following choices:</span></span>  
  
   -   <span data-ttu-id="63434-109">**Nombre de la copia.**</span><span class="sxs-lookup"><span data-stu-id="63434-109">**Copy Name.**</span></span> <span data-ttu-id="63434-110">Se utiliza el nombre del nodo del esquema de origen como valor del nodo vinculado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="63434-110">The name of the node in the source schema is used as the value of the linked node in the destination schema.</span></span>  
  
   -   <span data-ttu-id="63434-111">**Copie el valor de texto.**</span><span class="sxs-lookup"><span data-stu-id="63434-111">**Copy Text Value.**</span></span> <span data-ttu-id="63434-112">Se utiliza el valor que corresponde al nodo del esquema de origen (datos de elemento o valor de atributo) como valor del nodo vinculado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="63434-112">The value corresponding to the node in the source schema (element data or an attribute value) is used as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="63434-113">Éste es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="63434-113">This choice is the default.</span></span> <span data-ttu-id="63434-114">Por ejemplo, `<Node>Hello<Name>Chris</Name>Barry</Node>` daría como resultado "Hello".</span><span class="sxs-lookup"><span data-stu-id="63434-114">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello".</span></span>  
  
   -   <span data-ttu-id="63434-115">**Copie el valor de subcontenido y texto.**</span><span class="sxs-lookup"><span data-stu-id="63434-115">**Copy Text and Subcontent Value.**</span></span> <span data-ttu-id="63434-116">El valor correspondiente al nodo de registro, el valor de todos sus nodos secundarios y los nodos secundarios de ambos en el esquema de origen (datos de elemento y valores de atributo) se combinan como el valor del nodo vinculado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="63434-116">The value corresponding to the record node, and the value of all its child nodes, and their child nodes, in the source schema (element data and attribute values) are combined as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="63434-117">Por ejemplo, `<Node>Hello<Name>Chris</Name>Barry</Node>` dará como resultado "Hello Chris Barry".</span><span class="sxs-lookup"><span data-stu-id="63434-117">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello Chris Barry".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63434-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="63434-118">See Also</span></span>  
 <span data-ttu-id="63434-119">[Uso de vínculos para especificar el registro y asignaciones de campos](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="63434-119">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="63434-120">Vínculos y directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="63434-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)