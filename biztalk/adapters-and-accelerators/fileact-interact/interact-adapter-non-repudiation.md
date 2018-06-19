---
title: Interactuar adaptador repudio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13fb77c-b10c-4f8a-ba4b-efecc83e092c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7eabd7eab04c0bd64af0164b73b38af197ac9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224924"
---
# <a name="interact-adapter-non-repudiation"></a>Interactuar sin repudio de adaptador
Se obtiene compatibilidad sin repudio para un mensaje saliente de InterAct estableciendo la SwInt:NRIndicator como TRUE en la SwInt:RequestControl o SwInt:ResponseControl, según corresponda. Esto es necesario sólo si el servicio no selecciona sin repudio soporte de forma predeterminada, según el perfil de servicio.  
  
 Sin repudio se basa en una firma válida creada por el SNL, justo antes de transmitir el mensaje. Por lo tanto, para obtener soporte técnico sin repudio en los mensajes de solicitud salientes, es obligatorio para el elemento SwInt:RequestCrypto, dentro de la SwInt:RequestControl, que se establecerán TRUE en la SwInt:RequestControl.  
  
 Para los mensajes de respuesta, el requisito es equivalente, salvo que los elementos implicados son SwInt:ResponseCrypto, como dentro de la SwInt:ResponseControl; SwInt:ResponseCrypto se debe establecer en TRUE.  
  
 Para obtener soporte sin repudio en una solicitud, es necesario para la firma del mensaje cubrir la SwInt:RequestHeader, SwInt:RequestPayload y el SwInt:SwiftRequestRef de la SwInt:RequestDescriptor. Vínculo de SWIFTNet genera automáticamente el SwInt:SwiftRequestRef. En relación con la generación de la SwInt:SwiftRequestRef, la SNL ajusta también automáticamente el valor de SwSec:MemberRef dentro de la SwSec:CryptoControl para generar la firma del mensaje requerido. De forma similar, para no repudiatin soporte técnico en una respuesta, es necesario para la firma del mensaje cubrir la SwInt:ResponseHeader, SwInt:ResponsePayload y el SwInt:SwiftResponseRef de la SwInt:ResponseDescriptor. Vínculo de SWIFTNet genera automáticamente el SwInt:SwiftResponseRef. En relación con la generación de la SwInt:SwiftResponseRef, la SNL ajusta también automáticamente el valor de SwSec:MemberRef dentro de la SwSec:CryptoControl para generar la firma del mensaje requerido.  
  
 Si el perfil de servicio de negocio selecciona sin repudio de forma predeterminada, la firma del mensaje es necesario sigue siendo necesaria para seleccionarse (como se describe, en la SwInt:RequestControl o la SwInt:ResponseControl) y debe seleccionarse antes de que el mensaje abandona SNL.  
  
 Si la selección de características según el perfil de servicio de negocio invoca soporte sin rechazo en un mensaje y, si no se encuentra la firma necesaria con el mensaje, a continuación, se rechazará el mensaje mediante el conmutador. Se devolverá un mensaje de excepción de estado al remitente del mensaje.  
  
 Cifrado de la carga no es coherente con el soporte técnico sin repudio. Si se selecciona soporte sin rechazo de un mensaje y la carga se cifra en su totalidad o en parte, se rechazará el mensaje por el vínculo de SWIFTNet.  
  
 Tenga en cuenta que si el servicio no tiene la característica sin repudio, cualquier solicitud o respuesta que indica sin repudio en el control, se rechazarán.  
  
## <a name="see-also"></a>Vea también  
 [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)