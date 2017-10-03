---
title: "Error: el destino necesario tiene origen de nodo elección | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.reqdTargetHasChoiceNodeSource
ms.assetid: 5b5af999-d100-4e5d-a959-c8b11d574d3b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c9ad912b03bbb475efcc9eb8207a388400b43b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-target-has-choice-node-source"></a>Error: el destino necesario tiene origen de nodo elección
**Código de error**  
  
 btm1029  
  
 **Explicación**  
  
 El nodo indicado del esquema de destino se especifica como obligatoria pero está vinculado a un nodo del esquema de origen que está dentro de un **elección** nodo. Como el nodo indicado en el esquema de origen puede no aparecer en un mensaje de instancia de entrada, puede que no exista un origen a partir del cual crear el nodo necesario en el esquema de destino.  
  
 **Acción del usuario**  
  
 Según sea necesario, cambie el nodo indicado del esquema de destino a opcional, o bien proporcione un origen distinto para el nodo indicado en el esquema de destino que deba encontrarse en todos los mensajes de instancia de entrada válidos.