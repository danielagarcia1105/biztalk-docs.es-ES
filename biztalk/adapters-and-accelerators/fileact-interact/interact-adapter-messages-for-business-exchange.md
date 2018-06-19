---
title: Interactuar mensajes del adaptador para el intercambio de negocio | Documentos de Microsoft
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
ms.openlocfilehash: d19e10940e6a83c24e9397f0df94d0fc54e4da38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224604"
---
# <a name="interact-adapter-messages-for-business-exchange"></a>Interactuar mensajes del adaptador para el intercambio de negocios
Hay cuatro mensajes en el ciclo de InterAct adaptador-to-end. Estos mensajes son primitivos de SWIFTNet. El primer y último mensajes forman parte de los tipos primitivos del lado cliente, SwInt:ExchangeRequest y SwInt:ExchangeResponse. Los dos mensajes intermedios forman parte de los tipos primitivos del lado servidor, SwInt:HandleRequest y SwInt:HandleResponse.  
  
 En este nivel de simplificación, hay seis pasos en el ciclo de mensajes de extremo a extremo:  
  
1.  La aplicación cliente prepara el mensaje de solicitud.  
  
2.  La aplicación cliente pasa el mensaje de solicitud a SWIFTNet.  
  
3.  SWIFTNet procesa el mensaje de solicitud y lo envía a la aplicación de servidor.  
  
4.  La aplicación del servidor recibe el mensaje de solicitud de SWIFTNet.  
  
5.  La aplicación de servidor prepara el mensaje de respuesta.  
  
6.  La aplicación de servidor pasa el mensaje de respuesta a SWIFTNet.  
  
7.  SWIFTNet procesa el mensaje de respuesta y lo envía a la aplicación cliente.  
  
8.  La aplicación cliente recibe el mensaje de respuesta de SWIFTNet.  
  
 La siguiente ilustración muestra el intercambio de mensajes de interacción.  
  
 ![Intercambio de mensajes interAct](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")  
  
## <a name="see-also"></a>Vea también  
 [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [Interactuar sin repudio de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)