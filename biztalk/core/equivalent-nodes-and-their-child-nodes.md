---
title: Nodos equivalente y sus nodos secundarios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a85c6a1-6121-4849-b958-7c4bd1c7c552
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82c58b477130431ce2b115cb141af759b6614b57
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012053"
---
# <a name="equivalent-nodes-and-their-child-nodes"></a><span data-ttu-id="6ba7d-102">Nodos equivalente y sus nodos secundarios</span><span class="sxs-lookup"><span data-stu-id="6ba7d-102">Equivalent Nodes and Their Child Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="6ba7d-103">Información general</span><span class="sxs-lookup"><span data-stu-id="6ba7d-103">Overview</span></span>
<span data-ttu-id="6ba7d-104">El **\<equivalente\>** nodo y sus elementos secundarios se usan en el árbol de esquema para mostrar los casos de polimorfismo de tipo de datos complejos.</span><span class="sxs-lookup"><span data-stu-id="6ba7d-104">The **\<Equivalent\>** node and its children are used in the schema tree to display occurrences of complex data type polymorphism.</span></span> <span data-ttu-id="6ba7d-105">Al derivar un tipo de datos complejo a partir de otro tipo de datos complejo, el polimorfismo de XSD permite que alguno de estos tipos de datos aparezca en ubicaciones de mensajes de instancia donde se ha especificado el tipo de datos base complejo.</span><span class="sxs-lookup"><span data-stu-id="6ba7d-105">When you derive one complex data type from another complex data type, polymorphism within XSD allows either of these data types to occur in instance messages in locations for which the base complex data type has been specified.</span></span> <span data-ttu-id="6ba7d-106">Durante la validación de esquema, el hecho de que se permite uno de varios tipos de datos complejos en una ubicación concreta se representa de forma implícita por el nombre de tipo de datos base complejo asociado con el **base** atributo de la **extensión** o **restricción** elementos de los tipos de datos complejos derivados.</span><span class="sxs-lookup"><span data-stu-id="6ba7d-106">During schema validation, the fact that one of multiple possible complex data types is allowed at a particular location is represented implicitly by the base complex data type name associated with the **base** attribute of the **extension** or **restriction** elements of the derived complex data types.</span></span> <span data-ttu-id="6ba7d-107">Para que este polimorfismo sea más obvio en el árbol de esquema, el **\<equivalente\>** nodo y sus nodos secundarios se muestran de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="6ba7d-107">To make this polymorphism more obvious in the schema tree, the **\<Equivalent\>** node and its child nodes are displayed explicitly.</span></span>  

 <span data-ttu-id="6ba7d-108">El **\<equivalente\>** nodo se muestra como un nodo secundario de apariciones del tipo de datos base complejo, que indica que hay varios tipos de datos complejos que pueden aparecer en esa posición en una instancia Mensaje.</span><span class="sxs-lookup"><span data-stu-id="6ba7d-108">The **\<Equivalent\>** node is displayed as a child node of occurrences of the base complex data type, indicating that there are multiple complex data types that could occur at that position in an instance message.</span></span> <span data-ttu-id="6ba7d-109">Los nodos secundarios de la **\<equivalente\>** nodo se muestran como el valor de la **nombre** atributo del correspondiente **complexType** elemento en la representación XSD del polimorfismo y aparecen entre corchetes angulares (\<nombre\>).</span><span class="sxs-lookup"><span data-stu-id="6ba7d-109">The child nodes of the **\<Equivalent\>** node are displayed as the value of the **name** attribute of the corresponding **complexType** element in the XSD representation of the polymorphism, displayed within angle brackets (\<name\>).</span></span>  

 <span data-ttu-id="6ba7d-110">El **\<equivalente\>** cada nodo y sus elementos secundarios tienen solo dos propiedades asociadas con ellos:</span><span class="sxs-lookup"><span data-stu-id="6ba7d-110">The **\<Equivalent\>** node and its children each have only two properties associated with them:</span></span>  

-   <span data-ttu-id="6ba7d-111">**\<Equivalente\>**  nodo: **nombre de nodo** y **tipo Base**</span><span class="sxs-lookup"><span data-stu-id="6ba7d-111">**\<Equivalent\>** node: **Node Name** and **Base Type**</span></span>

-   <span data-ttu-id="6ba7d-112">Los nodos secundarios: **nombre de nodo** y **derivación de tipo**</span><span class="sxs-lookup"><span data-stu-id="6ba7d-112">Child nodes: **Node Name** and **Derivation Type**</span></span>

<span data-ttu-id="6ba7d-113">Para obtener más detalles acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="6ba7d-113">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="xsd-representation"></a><span data-ttu-id="6ba7d-114">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="6ba7d-114">XSD representation</span></span>  
 <span data-ttu-id="6ba7d-115">No hay ninguna representación XSD directa de la **\<equivalente\>** nodo y sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="6ba7d-115">There is no direct XSD representation of the **\<Equivalent\>** node and its children.</span></span> <span data-ttu-id="6ba7d-116">Este nodo se utiliza dentro del árbol de esquema para que el polimorfismo de los tipos de datos complejos sea más visible y obvio.</span><span class="sxs-lookup"><span data-stu-id="6ba7d-116">This node is used within the schema tree to make complex data type polymorphism more visible and obvious.</span></span>  

## <a name="see-also"></a><span data-ttu-id="6ba7d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ba7d-117">See Also</span></span>  
- [<span data-ttu-id="6ba7d-118">Representación de esquemas en BizTalk</span><span class="sxs-lookup"><span data-stu-id="6ba7d-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="6ba7d-119">Propiedades de los nodos</span><span class="sxs-lookup"><span data-stu-id="6ba7d-119">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="6ba7d-120">**Propiedades de nodo de grupo de secuencias** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6ba7d-120">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
- [<span data-ttu-id="6ba7d-121">Cómo establecer las propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="6ba7d-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
