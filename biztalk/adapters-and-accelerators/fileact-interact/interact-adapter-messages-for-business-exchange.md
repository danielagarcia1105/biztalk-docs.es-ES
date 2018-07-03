---
title: Interactuar mensajes del adaptador para el intercambio empresarial | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b443b8a-4e56-47f1-8d91-5c807fd54ccc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea8e7d4f4ed8397c88a3cf21280352b446d629c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020156"
---
# <a name="interact-adapter-messages-for-business-exchange"></a>Interactuar mensajes del adaptador para el intercambio empresarial
Hay cuatro mensajes en el ciclo de extremo a otro adaptador InterAct. Estos mensajes son primitivos de SWIFTNet. El primer y último mensajes comprenden los tipos primitivos del lado cliente, SwInt:ExchangeRequest y SwInt:ExchangeResponse. Los dos mensajes intermedios comprenden los tipos primitivos del lado servidor, SwInt:HandleRequest y SwInt:HandleResponse.  
  
 En este nivel de simplificación, hay seis pasos en el ciclo de mensaje to-end:  
  
1. La aplicación cliente prepara el mensaje de solicitud.  
  
2. La aplicación cliente pasa el mensaje de solicitud a SWIFTNet.  
  
3. SWIFTNet procesa el mensaje de solicitud y lo envía a la aplicación de servidor.  
  
4. La aplicación de servidor recibe el mensaje de solicitud de SWIFTNet.  
  
5. La aplicación de servidor prepara el mensaje de respuesta.  
  
6. La aplicación de servidor pasa el mensaje de respuesta a SWIFTNet.  
  
7. SWIFTNet procesa el mensaje de respuesta y lo envía a la aplicación cliente.  
  
8. La aplicación cliente recibe el mensaje de respuesta de SWIFTNet.  
  
   La siguiente ilustración muestra el intercambio de mensajes InterAct.  
  
   ![Intercambio de mensajes interAct](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Aplicación de cliente del adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar adaptador Store y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Entrega confiable de extremo a otro adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [No rechazo del adaptador de InterAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)