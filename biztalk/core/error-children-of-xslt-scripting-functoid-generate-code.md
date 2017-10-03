---
title: "Error: los elementos secundarios del Functoid de secuencia de comandos XSLT generan código | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.xsltScriptingChildrenGenCode
ms.assetid: 9cdac362-177f-445e-904b-aa6a9b1eb46f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810fe9befecd9bbd1a15468ca714177900450cb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a>Error: los elementos secundarios del Functoid de secuencia de comandos XSLT generan código
**Código de error**  
  
 btm1063  
  
 **Explicación**  
  
 Un escenario que contradice el uso de un **secuencias de comandos** functoid que está configurado para usar una plantilla de llamada XSLT o XSLT en línea se encontró en la asignación. En el esquema de destino, los nodos descendientes de un nodo que está vinculado a la salida de estos un **secuencias de comandos** functoid están intentado generar código XSLT propio.  
  
 **Acción del usuario**  
  
 Elimine la incompatibilidad cambiando el uso de la correspondiente **secuencias de comandos** functoid o cambiando los nodos secundarios de modo que ya no generen código XSLT propio.