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
# <a name="nodes-that-control-instance-message-structure-and-variations"></a>Nodos que controlan la estructura y las variaciones de los mensajes de instancia
Algunos de los tipos de nodos utilizados para crear esquemas en el Editor de BizTalk controlan la estructura y las variaciones de los mensajes de instancia. Usa **grupo de secuencias** nodos para especificar que una secuencia de elementos debe aparecer en un orden específico en la ubicación correspondiente en un mensaje de instancia. Usa **grupo de elecciones** nodos para especificar que un elemento de una colección de elementos pueden aparecer en la ubicación correspondiente en un mensaje de instancia. Usa **todos los grupos** nodos para especificar que todos los elementos especificados pueden aparecer en cualquier orden, pero una sola vez, en la ubicación correspondiente en un mensaje de instancia. **\<Equivalente >** nodos y sus nodos secundarios se muestran en el árbol de esquema para indicar las ubicaciones de los mensajes de instancia donde polimorfismo basado en derivación está en vigor, lo que permite uno de los muchos datos complejos relacionados tipos que se produzca en las correspondientes ubicación en un mensaje de instancia.  
  
 En el resto de esta sección se proporciona información adicional sobre esta clase de nodos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Nodos de grupo de secuencias](../core/sequence-group-nodes.md)  
  
-   [Nodos de grupo de elecciones](../core/choice-group-nodes.md)  
  
-   [Todos los nodos de grupo](../core/all-group-nodes.md)  
  
-   [\<Equivalente > nodos y sus nodos secundarios](../core/equivalent-nodes-and-their-child-nodes.md)