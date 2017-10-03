---
title: "Error: los elementos secundarios del Functoid de copia masiva generan código | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.massCopyChildtenGenCode
ms.assetid: c791009b-241b-4004-b0c6-f1536bb119c5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68183a90be46b176d13100b02cbed2798fe24b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-mass-copy-functoid-generate-code"></a>Error: los elementos secundarios del Functoid de copia masiva generan código
**Código de error**  
  
 btm1068  
  
 **Explicación**  
  
 Un escenario que contradice la funcionalidad de la **copia masiva** functoid se encontró en la asignación. En el esquema de destino, los nodos descendientes de un nodo que está vinculado a la salida de un **copia masiva** functoid están intentado generar código XSLT propio.  
  
 **Acción del usuario**  
  
 Elimine la incompatibilidad cambiando el uso de la correspondiente **copia masiva** functoid o cambiando los nodos secundarios de modo que ya no generen código XSLT propio.