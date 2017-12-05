---
title: "Presentación de mensajes de ejemplo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, SWIFT message block
- SWIFT messages, message block example
ms.assetid: 3136a7da-658d-4100-bbe5-2186ee8bafd1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8a3d03e35f6184e6aed6ba4af71e01a9b65e342
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="sample-message-presentation"></a>Presentación de mensajes de ejemplo
En la tabla siguiente se muestra un ejemplo de la distribución por bloques de un mensaje SWIFT.  
  
|Bloquear|Ejemplo|  
|-----------|-------------|  
|**Bloquear 1** encabezado básico|{1:F01BCITITMMAXXX0012000123}|  
|**Bloquear 2** (I) entrada de encabezado de la aplicación (para SWIFT)<br /><br /> O bien<br /><br /> **Bloquear 2** resultado de encabezado de la aplicación (O) (de SWIFT.)|{2:I103VBOEATWWXXXXN} O {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3|  
|**Bloquear 3** encabezado de usuario|{3: {108:BCITITMMA950906}}|  
|**Bloquear 4** texto|{4:\<CRLF\> : 20:1234567890\<CRLF\> : 23B:CRED\<CRLF\> : 32A:010605GBP45000,\<CRLF\> : 33B:GBP45000,\<CRLF\> : 50K:MASTERS IMPORTACIÓN\<CRLF\> TRUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> : 52A:BNPAFRPPCAM\<CRLF\> : 53A: POCIITMM680\<CRLF\> : 57A:BCITITMM680\<CRLF\> : 59: / P03452032022819 30\<CRLF\> IMPORTACIÓN GRAND\<CRLF\> PESCARA\< CRLF\> : 70: / RFB/INV 5591\<CRLF\> : 71A:SHA\<CRLF\> -}|  
|**Bloquear 5** finalizadores|{5: {MAC: 12345678} {CHK:123456789ABC}}|  
  
## <a name="see-also"></a>Vea también  
 [Esquemas de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-schemas.md)