---
title: "Iniciador de proceso público | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- public processes, initiator
- CIDX, 0A1 messages
- messages, 0A1 messages
- messages, message flow
- messages, public processes
- 0A1 messages
- public processes, message flow
ms.assetid: 371d0792-d346-405b-a8f4-2dfa64dd1566
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df1565915d36f3036543ff69c5da680d5949dc74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="initiator-public-process"></a>Iniciador de proceso público
Este proceso empieza de mensajería de RosettaNet Implementation Framework (RNIF) en el sistema de iniciador: crear y enviar el mensaje de negocio RNIF inicial.  
  
## <a name="message-flow-in-the-initiator-public-process"></a>Flujo de mensajes en el proceso público de iniciador  
 El flujo de mensajes a través del proceso público de iniciador es como sigue:  
  
1.  El proceso público de iniciador recibe el contenido del servicio y los datos adjuntos de los procesos privados a través del puerto de contenido del servicio.  
  
2.  El proceso público envía la respuesta al proceso privado y no realiza ningún procesamiento adicional.  
  
3.  Si el proceso público recibe una notificación que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] hicimos correctamente no enviar el mensaje, el proceso público envía ese estado al proceso privado iniciador y, a continuación, finaliza.  
  
4.  Si el proceso público recibe una notificación que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviado correctamente el mensaje, el proceso entre en un estado de espera (espera de acción por el servicio de respuesta).  
  
5.  Las siguientes acciones pueden finalizar el estado de espera:  
  
    1.  El proceso público recibe una señal de confirmación desde el servicio de respuesta.  
  
         Si está sin repudio para la señal necesarios (como está definido en las opciones de configuración de proceso), el proceso lee el resumen, el resumen de la señal correlaciona con la síntesis del mensaje de acción original y, a continuación, continúa la señal.  
  
         El proceso público envía los encabezados y el contenido del servicio de la señal al proceso privado.  
  
    2.  El proceso público recibe un mensaje de respuesta de doble acción desde el servicio de respuesta.  
  
         El proceso extrae el contenido del servicio y los encabezados del mensaje de respuesta y envía al proceso privado.  
  
         Si la actividad es sincrónica, el proceso crea un mensaje de señal RNIF ajustando la parte del mensaje de contenido del servicio con el preámbulo, encabezado de servicio y encabezado de entrega (para RNIF 2.01). El proceso crea el preámbulo y los encabezados con la información de configuración sobre las entidades de origen y de destino y las variables PIP almacenadas en el acuerdo entre socios comerciales entre las partes. El proceso, a continuación, envía el mensaje de señal para el servicio de respuesta.  
  
         Si la actividad es asincrónica, finaliza el proceso.  
  
    3.  El proceso público recibe un mensaje de notificación de error (ndel) desde el servicio de respuesta. El proceso público, envía un mensaje de estado correspondiente al proceso privado del iniciador. El proceso privado, a continuación, controle el error y finaliza los procesos de ambos.  
  
    4.  El proceso público no recibe una señal de confirmación desde el servicio de respuesta en el tiempo al período de confirmación (como está definido en las opciones de configuración de proceso). Si es así, se produce uno de los siguientes:  
  
         Si el número de reintentos (como está definido en las opciones de configuración de proceso) no llegue a cero, y la actividad es asincrónica, el proceso público envía el mensaje de nuevo.  
  
         Si el número de reintentos (como está definido en las opciones de configuración de proceso) no llegue a cero, y la actividad es sincrónica, el proceso público inicia un mensaje 0A1.  
  
        > [!NOTE]
        >  CIDX no admite mensajes 0A1.  
  
         Si el número de reintentos llega a cero sin un envío correcta, el proceso público envía un mensaje de error y, si esto no es CIDX, el proceso público envía un mensaje 0A1.  
  
         Si la actividad es sincrónica y no es CIDX, el proceso público inicia un mensaje 0A1.  
  
    5.  Si se realiza ninguna acción en el tiempo para realizar período, y esto no es CIDX, el proceso público envía un mensaje 0A1.  
  
## <a name="see-also"></a>Vea también  
 [Procesos públicos](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [Proceso público de servicio de respuesta](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)