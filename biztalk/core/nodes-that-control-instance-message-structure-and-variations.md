---
title: Nodos que controlan la instancia de mensaje estructura y las variaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af8e6ce-282d-4318-a538-046b423ef033
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0733be2e3331e02bff38a7b93d31b8cafd5ec582
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a><span data-ttu-id="68cb0-102">Nodos que controlan la estructura y las variaciones de los mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="68cb0-102">Nodes That Control Instance Message Structure and Variations</span></span>
<span data-ttu-id="68cb0-103">Algunos de los tipos de nodos utilizados para crear esquemas en el Editor de BizTalk controlan la estructura y las variaciones de los mensajes de instancia.</span><span class="sxs-lookup"><span data-stu-id="68cb0-103">Some of the node types that you use to create schemas in BizTalk Editor control the structure of, and variations within, instance messages.</span></span> <span data-ttu-id="68cb0-104">Usa **grupo de secuencias** nodos para especificar que una secuencia de elementos debe aparecer en un orden específico en la ubicación correspondiente en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="68cb0-104">You use **Sequence Group** nodes to specify that a sequence of elements must occur in a specific order in the corresponding location in an instance message.</span></span> <span data-ttu-id="68cb0-105">Usa **grupo de elecciones** nodos para especificar que un elemento de una colección de elementos pueden aparecer en la ubicación correspondiente en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="68cb0-105">You use **Choice Group** nodes to specify that one element from a collection of elements can occur in the corresponding location in an instance message.</span></span> <span data-ttu-id="68cb0-106">Usa **todos los grupos** nodos para especificar que todos los elementos especificados pueden aparecer en cualquier orden, pero una sola vez, en la ubicación correspondiente en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="68cb0-106">You use **All Group** nodes to specify that all of the specified elements can occur in any order, but only once, at the corresponding location in an instance message.</span></span> <span data-ttu-id="68cb0-107">**\<Equivalente >** nodos y sus nodos secundarios se muestran en el árbol de esquema para indicar las ubicaciones de los mensajes de instancia donde polimorfismo basado en derivación está en vigor, lo que permite uno de los muchos datos complejos relacionados tipos que se produzca en las correspondientes ubicación en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="68cb0-107">**\<Equivalent>** nodes and their child nodes are displayed in the schema tree to indicate locations in instance messages where derivation-based polymorphism is in effect, allowing one of many related complex data types to occur in the corresponding location in an instance message.</span></span>  
  
 <span data-ttu-id="68cb0-108">En el resto de esta sección se proporciona información adicional sobre esta clase de nodos.</span><span class="sxs-lookup"><span data-stu-id="68cb0-108">The remainder of this section provides additional information about this class of nodes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68cb0-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="68cb0-109">In This Section</span></span>  
  
-   [<span data-ttu-id="68cb0-110">Nodos de grupo de secuencias</span><span class="sxs-lookup"><span data-stu-id="68cb0-110">Sequence Group Nodes</span></span>](../core/sequence-group-nodes.md)  
  
-   [<span data-ttu-id="68cb0-111">Nodos de grupo de elecciones</span><span class="sxs-lookup"><span data-stu-id="68cb0-111">Choice Group Nodes</span></span>](../core/choice-group-nodes.md)  
  
-   [<span data-ttu-id="68cb0-112">Todos los nodos de grupo</span><span class="sxs-lookup"><span data-stu-id="68cb0-112">All Group Nodes</span></span>](../core/all-group-nodes.md)  
  
-   [<span data-ttu-id="68cb0-113">\<Equivalente > nodos y sus nodos secundarios</span><span class="sxs-lookup"><span data-stu-id="68cb0-113">\<Equivalent> Nodes and Their Child Nodes</span></span>](../core/equivalent-nodes-and-their-child-nodes.md)