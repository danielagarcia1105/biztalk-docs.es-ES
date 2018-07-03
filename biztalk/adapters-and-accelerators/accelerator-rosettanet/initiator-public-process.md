---
title: Proceso público del iniciador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fa1cd2fc73e37590e25fb381f509c2ad74cd9e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968445"
---
# <a name="initiator-public-process"></a>Proceso público del iniciador
Este proceso inicia la mensajería de RosettaNet Implementation Framework (RNIF) en el sistema de iniciador creando y enviando el mensaje de negocio RNIF inicial.  
  
## <a name="message-flow-in-the-initiator-public-process"></a>Flujo de mensajes en el proceso público del iniciador  
 El flujo de mensajes a través del proceso público del iniciador es como sigue:  
  
1. El proceso público del iniciador recibe el contenido del servicio y los datos adjuntos de los procesos privados a través del puerto de contenido del servicio.  
  
2. El proceso público envía la respuesta al proceso privado y no hace ningún procesamiento adicional.  
  
3. Si el proceso público recibe una notificación que Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] hizo correctamente no enviar el mensaje, el proceso público envía ese estado al proceso privado del iniciador y, a continuación, finaliza.  
  
4. Si el proceso público recibe una notificación que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviado correctamente el mensaje, el proceso entra en un estado de espera (espera de una acción mediante el servicio de respuesta).  
  
5. Las siguientes acciones pueden finalizar el estado de espera:  
  
   1.  El proceso público recibe una señal de confirmación desde el servicio de respuesta.  
  
        Si sin repudio para la señal es necesarios (como se establece en la configuración del proceso), el proceso lee el resumen, el resumen de la señal correlaciona con la síntesis del mensaje de acción original y, a continuación, continúa la señal.  
  
        El proceso público envía los encabezados y el contenido del servicio de la señal al proceso privado.  
  
   2.  El proceso público recibe un mensaje de respuesta de doble acción desde el servicio de respuesta.  
  
        El proceso extrae el contenido del servicio y los encabezados del mensaje de respuesta y los envía al proceso privado.  
  
        Si la actividad es sincrónica, el proceso crea un mensaje de señal RNIF ajustando la parte del mensaje de contenido del servicio con el preámbulo, encabezado de servicio y el encabezado de entrega (para RNIF 2.01). El proceso crea el preámbulo y los encabezados con información de configuración acerca de las entidades de origen y destino y las variables PIP almacenadas en el acuerdo entre socios comerciales entre las partes. El proceso, a continuación, envía el mensaje de señal para el servicio de respuesta.  
  
        Si la actividad es asincrónica, finaliza el proceso.  
  
   3.  El proceso público recibe un mensaje de notificación de error (ndel) desde el servicio de respuesta. El proceso público, envía un mensaje de estado correspondiente al proceso privado del iniciador. Proceso privado, a continuación, controle el error y finaliza ambos procesos.  
  
   4.  El proceso público no recibe una señal de confirmación desde el servicio de respuesta dentro del tiempo período de confirmación (como se establece en la configuración del proceso). Si es así, se produce uno de los siguientes:  
  
        Si el número de reintentos (como se establece en la configuración del proceso) no llegue a cero, y la actividad es asincrónica, el proceso público envía el mensaje de nuevo.  
  
        Si el número de reintentos (como se establece en la configuración del proceso) no llegue a cero, y la actividad es sincrónica, el proceso público inicia un mensaje 0A1.  
  
       > [!NOTE]
       >  CIDX no admite mensajes 0A1.  
  
        Si el número de reintentos llega a cero sin un envío correcta, el proceso público envía un mensaje de error y, si esto no es CIDX, el proceso público envía un mensaje 0A1.  
  
        Si la actividad es sincrónica, y esto no es CIDX, el proceso público inicia un mensaje 0A1.  
  
   5.  Si se realiza ninguna acción dentro del tiempo período realizar, y esto no es CIDX, el proceso público envía un mensaje de 0A1.  
  
## <a name="see-also"></a>Vea también  
 [Procesos públicos](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [Proceso público del respondedor](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)