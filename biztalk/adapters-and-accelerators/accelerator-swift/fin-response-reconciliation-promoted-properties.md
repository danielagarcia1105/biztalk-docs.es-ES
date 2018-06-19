---
title: Propiedades promocionadas de conciliación de respuesta FIN | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cb8aac4325ed0bf8fb0462d79eba25fe129d03c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964914"
---
# <a name="fin-response-reconciliation-promoted-properties"></a>Propiedades promocionadas de conciliación de respuesta FIN
El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] característica FINÉS conciliación de respuesta incluye las siguientes propiedades promocionadas.  
  
|Nombre promocionada|Description|Tipo de datos|Intervalo de valores|Ejemplo de uso|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_FRRFailed**|Esta propiedad se promociona en un escenario negativo al enviar el mensaje principal.|Boolean|True<br /><br /> False|Se utiliza en la expresión de filtro de un puerto de envío FRR para enviar un mensaje con errores a un controlador personalizado.|  
|**A4SWIFT_FrrFailedReason**|Indica que el mensaje original no se procesó correctamente por AAS/SWIFT.|String|-   \<NAKErrorCode\><br />-Tiempo de espera agotado<br />-TransportError<br />-Delayed_NAK<br />-AbortReceived|Se utiliza en la expresión de filtro de un puerto de envío FRR para enviar un mensaje con errores a un controlador personalizado.|  
|**A4SWIFT_FRRCorrelationToken**|Indica el token de correlación único de la salida MT*xxx* mensaje.|String|-|FRR compara esta propiedad en el **MQMD_CorrelID** propiedad de contexto de la respuesta FIN.|  
|**A4SWIFT_SendingServiceType**|Indica que el servicio FRR que envía el mensaje.|String|A4SWIFT_FrrService|Promueve cuando **A4SWIFT_FRRFailed** está establecida en True.|  
  
## <a name="see-also"></a>Vea también  
 [Propiedades promocionadas, A4SWIFT_ *](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   
 [Propiedades promocionadas de reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)