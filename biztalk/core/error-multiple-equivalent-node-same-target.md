---
title: Error - varios nodos equivalente mismo destino | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleEquivNodeSameTarget
ms.assetid: d8ca9f94-1d87-41bb-9479-6a01a5b6702d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12df4f7a68bb1eceaa3211c6aad6e9a581f17a4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-equivalent-node-same-target"></a>Error - varios nodos equivalente mismo destino
**Código de error**  
  
 btm1025  
  
 **Explicación**  
  
 Los nodos indicados en el esquema de origen, que son nodos secundarios en conflicto de un **equivalente** nodo de grupo, están vinculados al nodo indicado del esquema de destino. Solo puede aparecer uno de estos nodos en el esquema de origen de un mensaje de instancia determinado.  
  
 **Acción del usuario**  
  
 Asegúrese de que solo uno de los secundarios nodos de la **equivalente** nodo de grupo está conectado a un nodo determinado en el esquema de destino.