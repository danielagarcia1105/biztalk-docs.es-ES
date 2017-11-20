---
title: Nodos que se corresponden directamente con el mensaje de instancia de datos y la estructura | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18cf721c-2972-43c6-8ae4-f2f8f83ba2c5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5ed1aae517bb81e5a6cfb888300015e99ec017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="nodes-that-correspond-directly-to-message-instance-data-and-structure"></a><span data-ttu-id="9aa43-102">Nodos que se corresponden directamente con datos y estructuras de instancias de mensaje</span><span class="sxs-lookup"><span data-stu-id="9aa43-102">Nodes That Correspond Directly to Message Instance Data and Structure</span></span>
<span data-ttu-id="9aa43-103">Algunos de los tipos de nodos usados para crear esquemas en el Editor de BizTalk se corresponden directamente con elementos y atributos de la representación XML de los mensajes de instancia regidos por el esquema; para otros formatos de mensaje de instancia, como el formato de archivo sin formato, esta correspondencia solo existe después de la traducción desde el otro formato y antes de la traducción al otro formato.</span><span class="sxs-lookup"><span data-stu-id="9aa43-103">Some of the node types that you use to create schemas in BizTalk Editor correspond directly to elements and attributes in XML representation of instance messages governed by the schema (for other instance message formats, such as flat file formats, this correspondence only exists after translation from the other format and before translation to the other format).</span></span> <span data-ttu-id="9aa43-104">Estos tipos de nodo son **registro** nodos (incluyendo raíz **registro** nodos), **elemento de campo** nodos, y **atributo de campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="9aa43-104">These node types are **Record** nodes (including root **Record** nodes), **Field Element** nodes, and **Field Attribute** nodes.</span></span>  
  
 <span data-ttu-id="9aa43-105">Los valores asignados a la **nombre de nodo** propiedad de **registro** y **elemento de campo** nodos especifican el nombre del elemento correspondiente en los mensajes de instancia XML regidos por el esquema.</span><span class="sxs-lookup"><span data-stu-id="9aa43-105">The values you give to the **Node Name** property of **Record** and **Field Element** nodes specify the name of the corresponding element in XML instance messages governed by the schema.</span></span> <span data-ttu-id="9aa43-106">Del mismo modo, los valores asignados a la **nombre de nodo** propiedad de **atributo de campo** nodos especifican el nombre del atributo correspondiente en los mensajes de instancia XML regidos por el esquema.</span><span class="sxs-lookup"><span data-stu-id="9aa43-106">Likewise, the values you give to the **Node Name** property of **Field Attribute** nodes specify the name of the corresponding attribute in XML instance messages governed by the schema.</span></span> <span data-ttu-id="9aa43-107">Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="9aa43-107">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="9aa43-108">El resto de esta sección proporciona más información acerca de esta clase de nodos, con **registro** nodos recibir tratamiento independiente debido a su rol en especial en esquemas.</span><span class="sxs-lookup"><span data-stu-id="9aa43-108">The remainder of this section provides more information about this class of nodes, with root **Record** nodes receiving separate treatment due to their special role in schemas.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9aa43-109">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9aa43-109">Next steps</span></span> 
  
-   [<span data-ttu-id="9aa43-110">Nodos raíz</span><span class="sxs-lookup"><span data-stu-id="9aa43-110">Root Nodes</span></span>](../core/root-nodes.md)  
  
-   [<span data-ttu-id="9aa43-111">Nodos registro</span><span class="sxs-lookup"><span data-stu-id="9aa43-111">Record Nodes</span></span>](../core/record-nodes.md)  
  
-   [<span data-ttu-id="9aa43-112">Nodos de elemento de campo</span><span class="sxs-lookup"><span data-stu-id="9aa43-112">Field Element Nodes</span></span>](../core/field-element-nodes.md)  
  
-   [<span data-ttu-id="9aa43-113">Nodos de atributo de campo</span><span class="sxs-lookup"><span data-stu-id="9aa43-113">Field Attribute Nodes</span></span>](../core/field-attribute-nodes.md)