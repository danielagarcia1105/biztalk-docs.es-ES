---
title: Nodos Elemento de campo frente a Nodos de atributo de campo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6c56aae4e681632ef056a7ed3b85aa5c4f88f89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974165"
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a><span data-ttu-id="37578-102">Nodos Elemento de campo frente a Nodos Atributo de campo</span><span class="sxs-lookup"><span data-stu-id="37578-102">Field Element Nodes vs. Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="37578-103">Información general</span><span class="sxs-lookup"><span data-stu-id="37578-103">Overview</span></span>
<span data-ttu-id="37578-104">Los esquemas de archivo sin formato se utilizan en el desensamblador de archivos sin formato para controlar cómo se traducen los mensajes de instancia de archivo sin formato de entrada al formato XML equivalente, y en el ensamblador de archivos sin formato para controlar cómo se traducen los mensajes XML de salida a los mensajes de instancia de archivo sin formato equivalentes.</span><span class="sxs-lookup"><span data-stu-id="37578-104">Flat file schemas are used by the flat file disassembler to control how inbound flat file instance messages are translated into their equivalent XML form, and are used by the flat file assembler to control how outbound XML messages are translated into their equivalent flat file instance messages.</span></span> <span data-ttu-id="37578-105">Al construir estos esquemas, usa un **elemento de campo** nodo o un **atributo de campo** en posiciones concretas dentro del esquema para controlar si un campo determinado en la instancia de archivo sin formato mensaje corresponde a un elemento XML o a un atributo XML en el formato XML equivalente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="37578-105">When constructing such schemas, you use either a **Field Element** node or a **Field Attribute** node in particular positions within the schema to control whether a particular field in the flat file instance message corresponds to an XML element or to an XML attribute in the equivalent XML form of the message.</span></span>  

## <a name="example"></a><span data-ttu-id="37578-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37578-106">Example</span></span>  
 <span data-ttu-id="37578-107">Por ejemplo, el valor del campo a la izquierda y rellena de asterisco "`red*****`" en un archivo sin formato se puede traducir el mensaje de instancia en la representación XML equivalente de dos maneras diferentes, dependiendo de si ese campo en el esquema es un **campo Elemento** nodo o un **atributo de campo** nodo.</span><span class="sxs-lookup"><span data-stu-id="37578-107">For example, the left-aligned, asterisk-padded field value "`red*****`" in a flat file instance message can be translated into its equivalent XML representation in two different ways depending upon whether that field in the schema is a **Field Element** node or a **Field Attribute** node.</span></span> <span data-ttu-id="37578-108">Si ese campo se representa en el esquema por un **elemento de campo** nodo con su **nombre de nodo** propiedad establecida en "color" y que la contiene **registro** nodo tiene su **Nombre del nodo** propiedad establecida en "shirt", el equivalente XML del campo de archivo sin formato es (se muestra en negrita).</span><span class="sxs-lookup"><span data-stu-id="37578-108">When that field is represented in the schema by a **Field Element** node with its **Node Name** property set to "color", and the containing **Record** node has its **Node Name** property set to "shirt", the XML equivalent of the flat file field is (shown in bold type).</span></span>  

```  
<shirt>  
    <color>red</color>  
</shirt>  
```  

 <span data-ttu-id="37578-109">Si ese mismo campo de archivo sin formato se representa en el esquema por un **atributo de campo** nodo con su **nombre de nodo** propiedad establecida en color y que la contiene **registro** nodo tiene su **Nombre de nodo** propiedad establecida en camisa, el equivalente XML del campo de archivo sin formato es (se muestra en negrita):</span><span class="sxs-lookup"><span data-stu-id="37578-109">When that same flat file field is represented in the schema by a **Field Attribute** node with its **Node Name** property set to color, and the containing **Record** node has its **Node Name** property set to shirt, the XML equivalent of the flat file field is (shown in bold type):</span></span>  

```  
<color shirt="red"/>  
```  

> [!NOTE]
>  <span data-ttu-id="37578-110">Esquemas de archivo sin formato tienen la restricción adicional que dentro de un determinado **registro** nodo subordinado **atributo de campo** deben preceder a los nodos subordinados **registro** nodos o  **Elemento de campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="37578-110">Flat file schemas have a further restriction that within a given **Record** node, subordinate **Field Attribute** nodes must come before subordinate **Record** nodes or **Field Element** nodes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="37578-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="37578-111">See Also</span></span>  
- [<span data-ttu-id="37578-112">Consideraciones sobre campos</span><span class="sxs-lookup"><span data-stu-id="37578-112">Field Considerations</span></span>](../core/field-considerations.md)
- <span data-ttu-id="37578-113">**Nombre del nodo** propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="37578-113">**Node Name** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
