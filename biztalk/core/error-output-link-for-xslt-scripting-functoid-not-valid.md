---
title: Error - el vínculo de salida XSLT no es válido el Functoid de secuencias de comandos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.outputLinkForXsltNotValid
ms.assetid: cdf8e779-6cf6-4d9c-8655-f8b406498fb7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd597a3953db76087086c7ea9038e9fa1fd87eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---output-link-for-xslt-scripting-functoid-not-valid"></a>Error - el vínculo de salida XSLT no es válido el Functoid de secuencias de comandos
**Código de error**  
  
 btm1075  
  
 **Explicación**  
  
 El vínculo de salida de la correspondiente **secuencias de comandos** functoid configurado para utilizar XSLT en línea o una plantilla de llamada XSLT no es válido. El resultado de estos **secuencias de comandos** functoids debe estar conectados directamente a un nodo del esquema de destino (y no a otro functoid, por ejemplo).  
  
 **Acción del usuario**  
  
 Asegúrese de que conecta el vínculo de salida de la correspondiente **secuencias de comandos** functoid directamente a un nodo del esquema de destino.