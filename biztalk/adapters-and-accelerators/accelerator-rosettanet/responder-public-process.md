---
title: "Proceso público de servicio de respuesta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow
- messages, public processes
- public processes, message flow
- public processes, responder
ms.assetid: 78d83954-2998-44ac-a527-5e5858c61009
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c89c246bca80fdb648df909cd4f01fca4e2691dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="responder-public-process"></a>Proceso público de servicio de respuesta
Este proceso público en el servicio de respuesta recibe el mensaje de RosettaNet Implementation Framework (RNIF) desde el iniciador y responde en consecuencia.  
  
## <a name="message-flow-in-the-responder-public-process"></a>Flujo de mensajes en el proceso público de servicio de respuesta  
 El flujo de mensajes a través del proceso público del servicio de respuesta es el siguiente:  
  
1.  El proceso público de servicio de respuesta recibe el mensaje RNIF de la base de datos de cuadro de mensajes de respuesta.  
  
2.  El proceso público extrae el contenido del servicio y los encabezados del mensaje de acción y los envía al proceso privado.  
  
    > [!NOTE]
    >  El proceso público de servicio de respuesta realiza la validación estándar en el mensaje entrante (y cualquier validación adicional que se incluye en un adaptador de validación, si es aplicable). Si la validación es correcta, el proceso público iniciará el adaptador de la aplicación para realizar la notificación de acuerdo con la implementación específica. El proceso público de servicio de respuesta se guardará el mensaje en la base de datos de cuadro de mensajes y le notificará que el proceso privada del servicio de respuesta que se ha guardado el mensaje en el cuadro de mensajes (mediante el `BeginNotify` método en la `ApplicationAdapter` clase). Para obtener más información acerca del adaptador de validación y el adaptador de la aplicación, consulte [ValidationAdapter &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md) y [ApplicationAdapter &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md).  
  
3.  Si la actividad es asincrónica y de acción única, el proceso público construye un mensaje de señal RNIF (confirmación de aceptación) ajustando la parte del mensaje de contenido del servicio con el preámbulo, el encabezado de servicio y (para RNIF 2.01 solo) el encabezado de entrega. El proceso público construye el preámbulo, el encabezado de servicio y el encabezado de entrega usando la información almacenada en el acuerdo entre socios comerciales entre las partes: la configuración del proceso, la información de configuración sobre el origen y entidades de destino y las variables de proceso de interfaz de socio (PIP). El proceso, a continuación, envía el mensaje de señal al iniciador.  
  
    > [!NOTE]
    >  Si el mensaje es un mensaje de acción única, el flujo de mensajes está terminado.  
  
4.  El proceso público entra en un estado de espera (espera de acción por el proceso privada del servicio de respuesta).  
  
5.  Las siguientes acciones pueden finalizar el estado de espera (espera de acción por proceso privado Respondedor):  
  
    1.  El proceso privada del servicio de respuesta devuelve un mensaje de contenido del servicio de respuesta y encabezados, en respuesta al mensaje de acción original (que era un mensaje de doble acción).  
  
         Si el proceso público recibe el contenido del servicio de respuesta de procesos privado, el proceso público construye un mensaje RNIF que contiene el contenido del servicio. Para ello, ajuste la parte del mensaje de contenido del servicio con los encabezados que contengan la información de configuración acerca de las entidades de origen y destino y las variables PIP almacenadas en el acuerdo entre las partes.  
  
         El proceso público, envía el mensaje RNIF al iniciador mediante el puerto de vínculo de rol de señal y la acción.  
  
         Si el proceso público recibe una notificación que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] hicimos correctamente no enviar el mensaje, el proceso público envía ese estado al proceso privado y, a continuación, finaliza.  
  
         Si el proceso público recibe una notificación que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviado correctamente el mensaje, el proceso entre en un estado de espera (espera de acción por el iniciador). Este estado de espera es similar del estado de espera que entra en el iniciador cuando está esperando para la acción por el servicio de respuesta.  
  
    2.  El proceso público recibe un mensaje de notificación de error (ndel) desde el iniciador.  
  
    > [!NOTE]
    >  El proceso privado Respondedor le notificará el proceso público de servicio de respuesta después de que ha procesado correctamente el mensaje entrante. Después el servicio de respuesta proceso público ha recibido esta notificación (desde el `EndNotify` método en la `ApplicationAdapter` clase) el proceso público de servicio de respuesta correctamente finalizará.  
  
6.  El proceso público de servicio de respuesta entra en un estado de espera (espera recibir una señal del iniciador en respuesta al mensaje de respuesta que envía el proceso público de servicio de respuesta).  
  
## <a name="see-also"></a>Vea también  
 [Procesos públicos](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [Iniciador de proceso público](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)   
 [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)   
 [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)