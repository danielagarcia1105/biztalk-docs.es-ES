---
title: "Error: la entrada para Functoid de copia masiva no válido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.massCopyInputNotValid
ms.assetid: 141c45cd-79da-4f99-abb0-60a88dfcab76
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 903954fabb99520ce5b4a8e20c0296165944053a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---input-for-mass-copy-functoid-not-valid"></a>Error: la entrada para Functoid de copia masiva no válido
**Código de error**  
  
 btm1069  
  
 **Explicación**  
  
 El parámetro de entrada para la correspondiente **copia masiva** functoid no es válido o hay demasiados parámetros de entrada para la correspondiente **copia masiva** functoid se han especificado. **Copia masiva** functoids debe tener exactamente una entrada: un vínculo desde un **registro** nodo del esquema de origen.  
  
 **Acción del usuario**  
  
 Reconfigure el **copia masiva** functoid de modo que solo haya un parámetro de entrada de un **registro** nodo del esquema de origen.