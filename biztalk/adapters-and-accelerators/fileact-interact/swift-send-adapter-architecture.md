---
title: "Arquitectura del adaptador de envío de SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e52a5a21-0aa1-4cd9-a2a4-f9df425913a0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d772203c980495c5aa62266beb060693c1a8ad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-send-adapter-architecture"></a>Arquitectura del adaptador de envío SWIFT
En general, los adaptadores de envío de BizTalk Server se hospedan en el proceso de servicio de BizTalk, Btsntsvc.exe. Esto significa que el servidor BizTalk Server administra la duración del adaptador.  
  
 Hay dos maneras de enviar mensajes a la red SWIFT: (ExchangeRequest) sincrónica y asincrónica (es decir, no está implementado en esta versión). En BizTalk Server, el adaptador de envío debe admitir los siguientes patrones de comunicación para interactuar con el motor de mensajería de BizTalk:  
  
-   Respuesta de petición-respuesta, los mensajes se intercambian en parejas, llamados a los tipos primitivos, con la red SWIFT. Los mensajes enviados a SWIFT tendrá una respuesta sea empresarial, confirmación o un error. El mensaje de respuesta se envía al cuadro de mensajes. Este modo de funcionamiento se utiliza para la comunicación en tiempo real.  
  
-   Una manera de envío, el adaptador cuando se configura de una manera opera en el almacén y el modo de reenvío. Los mensajes se envían a una cola preconfigurada en lugar de un destinatario. El remitente puede recuperar la respuesta al abrir una sesión con la cola en modo de inserción o extracción.  
  
> [!NOTE]
>  La manera de crear el adaptador afecta al modo en que funciona.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [URI del adaptador de envío SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [Envío dinámico del adaptador de envío SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [Inicialización del adaptador de envío SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [Modo sincrónico del adaptador de envío SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [Finalización del adaptador de envío SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)