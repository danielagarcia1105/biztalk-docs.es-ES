---
title: "Raíz nodos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2161f877-835e-434d-a8d1-2426f977d60e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2070982a6bca09e8bffb2bcc88e5997360c86851
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="root-nodes"></a><span data-ttu-id="eeae1-102">Nodos raíz</span><span class="sxs-lookup"><span data-stu-id="eeae1-102">Root Nodes</span></span>
<span data-ttu-id="eeae1-103">En el Editor de BizTalk, los nodos secundarios de la **esquema** nodo se conocen como **raíz** nodos.</span><span class="sxs-lookup"><span data-stu-id="eeae1-103">In BizTalk Editor, child nodes of the **Schema** node are known as **Root** nodes.</span></span> <span data-ttu-id="eeae1-104">**Raíz** nodos son un tipo especial de **registro** nodo, y tienen algunas propiedades más que normal **registro** nodos.</span><span class="sxs-lookup"><span data-stu-id="eeae1-104">**Root** nodes are a special type of **Record** node, and have a few more properties than regular **Record** nodes.</span></span> <span data-ttu-id="eeae1-105">El **raíz** nodo representa el tipo de documento se describe el esquema y se pueden cambiar según corresponda.</span><span class="sxs-lookup"><span data-stu-id="eeae1-105">The **Root** node represents the type of document described by the schema, and can be renamed as appropriate.</span></span> <span data-ttu-id="eeae1-106">Por ejemplo, puede cambiar el nombre del **raíz** nodo, por lo que TI describe el tipo de mensaje que representa el esquema, como purchaseOrder, orderAcknowledgment o shipNotice.</span><span class="sxs-lookup"><span data-stu-id="eeae1-106">For example, you can rename the **Root** node so that it describes the type of message that the schema represents, such as purchaseOrder, orderAcknowledgment, or shipNotice.</span></span>  
  
 <span data-ttu-id="eeae1-107">Cuando se crea un nuevo esquema XML en el Editor de BizTalk, el **esquema** y un nodo **raíz** nodo se crean automáticamente.</span><span class="sxs-lookup"><span data-stu-id="eeae1-107">When you create a new XML schema in BizTalk Editor, the **Schema** node and one **Root** node are created automatically.</span></span> <span data-ttu-id="eeae1-108">Puede crear más **raíz** nodos como elementos secundarios de la **esquema** nodo; Esto le permite crear una biblioteca de esquemas dentro de una única representación de lenguaje de definición (XSD) del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="eeae1-108">You can create additional **Root** nodes as children of the **Schema** node; this enables you to create a library of schemas within a single XML Schema definition (XSD) language representation.</span></span> <span data-ttu-id="eeae1-109">Por ejemplo, puede crear una biblioteca de esquemas para describir los distintos esquemas de mensajes relacionados con el envío de pedidos, así como cambiar el nombre de varios nodos raíz a purchaseOrder, orderAcknowledgment y shipNotice.</span><span class="sxs-lookup"><span data-stu-id="eeae1-109">For example, you can create a library of schemas to describe the various schemas of messages related to sending purchase orders, naming the various root nodes purchaseOrder, orderAcknowledgment, and shipNotice.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="eeae1-110">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="eeae1-110">XSD representation</span></span>  
 <span data-ttu-id="eeae1-111">El ejemplo siguiente muestra las líneas en la representación XSD del esquema que corresponden a la **raíz** nodo en la vista de árbol del esquema.</span><span class="sxs-lookup"><span data-stu-id="eeae1-111">The following example shows the lines in the XSD representation of the schema that correspond to the **Root** node in the tree view of the schema.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="Root">  
        <xs:complexType />   
    </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="eeae1-112">**Raíz** nodos en el Editor de BizTalk representan el elemento principal de una instancia XML correspondiente del mensaje en cuestión.</span><span class="sxs-lookup"><span data-stu-id="eeae1-112">**Root** nodes in BizTalk Editor represent the main element in a corresponding XML instance of the message in question.</span></span> <span data-ttu-id="eeae1-113">Por ejemplo, si la **raíz** se cambia el nombre de nodo de un esquema concreto a purchaseOrder, la representación XSD correspondiente tiene la siguiente estructura de alto nivel.</span><span class="sxs-lookup"><span data-stu-id="eeae1-113">For example, if the **Root** node of a particular schema is renamed to purchaseOrder, the corresponding XSD representation has the following high-level structure.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="">  
        <xs:complexType>   
            ...  
        </xs:complexType>   
    </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="eeae1-114">Un mensaje de instancia XML correspondiente debe tener la siguiente estructura básica.</span><span class="sxs-lookup"><span data-stu-id="eeae1-114">A corresponding XML instance message must have the following basic structure.</span></span>  
  
```  
<?xml version="1.0"?>  
<purchaseOrder ...>  
    ...  
</purchaseOrder>  
```  
  
> [!NOTE]
>  <span data-ttu-id="eeae1-115">No pueden tener nodos raíz **campo** atributos.</span><span class="sxs-lookup"><span data-stu-id="eeae1-115">Root nodes may not have **Field** attributes.</span></span> <span data-ttu-id="eeae1-116">**Campo** atributos conectado a la **raíz** nodo no se guardan con el esquema.</span><span class="sxs-lookup"><span data-stu-id="eeae1-116">**Field** attributes attached to the **Root** node are not saved with the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeae1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="eeae1-117">See Also</span></span>  
-  [<span data-ttu-id="eeae1-118">Representación de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="eeae1-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="eeae1-119">Propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="eeae1-119">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="eeae1-120">**Propiedades del nodo registro**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="eeae1-120">**Record Node Properties**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="eeae1-121">Cómo establecer propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="eeae1-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)