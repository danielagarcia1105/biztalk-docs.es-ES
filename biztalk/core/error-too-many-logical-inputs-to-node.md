---
title: "Error: demasiadas entradas lógicas en el nodo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tooManyLogicalInputsToNode
ms.assetid: 9295d6a2-702d-4cf3-8f5d-26ba63b9fce0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e363d79a2b013b8e90533c4e6e36cff5b5798b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---too-many-logical-inputs-to-node"></a>Error: demasiadas entradas lógicas en el nodo
**Código de error**  
  
 btm1006  
  
 **Explicación**  
  
 Hay un mayor número de vínculos lógicos conectados al nodo indicado en el esquema de destino que el número de vínculos de entrada a la **bucle** functoid que esté conectado al nodo antecesor del nodo indicado. El número de vínculos, tanto del primer tipo como del segundo, debe coincidir.  
  
 **Acción del usuario**  
  
 Repetición del trabajo el número de vínculos conectados al nodo indicado y a la **bucle** functoid conectado al nodo antecesor para que coincidan.