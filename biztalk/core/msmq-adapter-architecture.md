---
title: Arquitectura del adaptador de MSMQ | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, MSMQ adapters
- MSMQ adapters, architecture
ms.assetid: acecc2a4-0670-487e-be39-28a24c8c3f16
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd314b6f835568b6336121478268b84381a288ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msmq-adapter-architecture"></a>Arquitectura del adaptador de MSMQ
El adaptador de MSMQ le permite aprovechar las características de Microsoft Message Queuing (también denominado MSMQ) que, por otra parte, no están disponibles en BizTalk Server.  
  
## <a name="adapter-structure"></a>Estructura del adaptador  
 El adaptador de MSMQ tiene la misma estructura que otros adaptadores de BizTalk y utiliza el marco de trabajo de adaptadores. Está compuesto por un componente de tiempo de diseño y otro de tiempo de ejecución. El componente de tiempo de ejecución, a su vez, contiene los elementos que implementan el transporte de mensaje.  
  
 El componente de tiempo de diseño le permite configurar las propiedades del adaptador para el envío y la recepción.  
  
 El componente de tiempo de ejecución puede enviar mensajes a una cola definida en tiempo de diseño o recibir mensajes desde una cola designada. El tiempo de ejecución del adaptador se ejecuta en el mismo proceso que la aplicación de BizTalk Server y no se ejecuta en un host aislado.  
  
 La administración de todos los mensajes se basa en el servicio Message Queue Server incluso para colas remotas. Para colas remotas, el adaptador entrega los mensajes al servicio local de Message Queue Server. Éste, a su vez, envía los mensajes a la cola remota.  
  
 Para obtener una lista completa de envío y recepción de propiedades de configuración, consulte [cómo configurar un puerto de envío MSMQ](../core/how-to-configure-an-msmq-send-port.md) y [cómo configurar una ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md).  
  
 Para obtener más información sobre Message Queue Server, vea los temas siguientes disponibles en Microsoft TechNet Library:  
  
-   **Guía de diseño de puesta en cola de mensajes** en [http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080).  
  
-   **Guía de operaciones de puesta en cola de mensajes** en [http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079).  
  
-   **Message Queue Server Guía de solución de problemas** en [http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081).  
  
-   **Referencia técnica de puesta en cola de mensajes** en [http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el adaptador de MSMQ?](../core/what-is-the-msmq-adapter.md)