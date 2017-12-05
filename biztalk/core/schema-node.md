---
title: Nodo de esquema | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ea02c2a-ee00-4f44-9086-83d7ac4a8832
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd892e825194afea880d3bde153f472051ce9102
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="schema-node"></a><span data-ttu-id="3e1df-102">Esquema (nodo)</span><span class="sxs-lookup"><span data-stu-id="3e1df-102">Schema Node</span></span>

## <a name="overview"></a><span data-ttu-id="3e1df-103">Información general</span><span class="sxs-lookup"><span data-stu-id="3e1df-103">Overview</span></span>
<span data-ttu-id="3e1df-104">En el Editor de BizTalk, la parte superior de la jerarquía del esquema es siempre el **esquema** nodo, que no se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="3e1df-104">In BizTalk Editor, the top of the schema hierarchy is always the **Schema** node, which cannot be renamed.</span></span> <span data-ttu-id="3e1df-105">El **esquema** nodo corresponde a la **esquema** elemento en la representación del lenguaje de esquema XML (XSD) de la definición del esquema.</span><span class="sxs-lookup"><span data-stu-id="3e1df-105">The **Schema** node corresponds to the **schema** element in the XML Schema definition (XSD) language representation of the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e1df-106">En el Editor de BizTalk, el **esquema** nodo se representa con la cadena \<esquema\> en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="3e1df-106">In BizTalk Editor, the **Schema** node is represented with the string \<Schema\> in the schema tree view.</span></span>  
  
 <span data-ttu-id="3e1df-107">En general, las propiedades de la **esquema** nodo corresponden a los atributos de la **esquema** elemento en la representación XSD del esquema.</span><span class="sxs-lookup"><span data-stu-id="3e1df-107">In general, the properties of the **Schema** node correspond to the attributes of the **schema** element in the XSD representation of the schema.</span></span> <span data-ttu-id="3e1df-108">Para obtener información general acerca de las propiedades de nodo, vea [propiedades del nodo](../core/node-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3e1df-108">For general information about node properties, see [Node Properties](../core/node-properties.md).</span></span> <span data-ttu-id="3e1df-109">Para obtener información de referencia acerca de las propiedades de la **esquema** nodo, consulte el **propiedades del nodo esquema** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="3e1df-109">For reference information about the properties of the **Schema** node, see the **Schema Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="3e1df-110">Cuando se crea un nuevo esquema XML en el Editor de BizTalk, el **esquema** y un nodo **raíz** nodo se crean automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3e1df-110">When you create a new XML schema in BizTalk Editor, the **Schema** node and one **Root** node are created automatically.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="3e1df-111">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="3e1df-111">XSD representation</span></span>  
 <span data-ttu-id="3e1df-112">El siguiente ejemplo muestra, en negrita, las líneas en la representación XSD del esquema que corresponden a la  **\<esquema\>**  nodo en la vista de árbol del esquema.</span><span class="sxs-lookup"><span data-stu-id="3e1df-112">The following example shows, in bold type, the lines in the XSD representation of the schema that correspond to the **\<Schema\>** node in the tree view of the schema.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3e1df-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e1df-113">See Also</span></span>  
 <span data-ttu-id="3e1df-114">[Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3e1df-114">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="3e1df-115">[Propiedades de nodo](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="3e1df-115">[Node Properties](../core/node-properties.md) </span></span>  
 [<span data-ttu-id="3e1df-116">Establecer propiedades de nodos</span><span class="sxs-lookup"><span data-stu-id="3e1df-116">Set Node Properties</span></span>](../core/how-to-set-node-properties.md)