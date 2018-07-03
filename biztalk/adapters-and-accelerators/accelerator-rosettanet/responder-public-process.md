---
title: Proceso público del Respondedor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow
- messages, public processes
- public processes, message flow
- public processes, responder
ms.assetid: 78d83954-2998-44ac-a527-5e5858c61009
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6565f10b311a504edbd3323cc0fe3b318c7b2410
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981069"
---
# <a name="responder-public-process"></a>Proceso público del Respondedor
Este proceso público en el Respondedor recibe el mensaje de RosettaNet Implementation Framework (RNIF) desde el iniciador y responde en consecuencia.  
  
## <a name="message-flow-in-the-responder-public-process"></a>Flujo de mensajes en el proceso público del Respondedor  
 El flujo de mensajes a través del proceso público del Respondedor es como sigue:  
  
1. El proceso público del Respondedor recibe el mensaje RNIF de la base de datos de cuadro de mensajes de respuesta.  
  
2. El proceso público extrae el contenido del servicio y los encabezados del mensaje de acción y los envía al proceso privado.  
  
   > [!NOTE]
   >  El proceso público del Respondedor realiza validación estándar en el mensaje entrante (y cualquier validación adicional que se incluye en un adaptador de validación, si procede). Si la validación es correcta, el proceso público iniciará el adaptador de aplicación para realizar la notificación de acuerdo con la implementación específica. El proceso público del Respondedor guardará el mensaje en la base de datos de cuadro de mensajes y le notificará que el proceso privado del Respondedor que guardó el mensaje en el cuadro de mensajes (mediante el `BeginNotify` método en el `ApplicationAdapter` clase). Para obtener más información acerca del adaptador de validación y el adaptador de aplicación, consulte [ValidationAdapter &#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md) y [ApplicationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md).  
  
3. Si la actividad es asincrónica y de acción única, el proceso público construye un mensaje de señal RNIF (confirmación de aceptación) ajustando la parte del mensaje de contenido del servicio con el preámbulo, encabezado de servicio y (para RNIF 2.01 sólo) el encabezado de entrega. El proceso público construye el preámbulo, el encabezado de servicio y el encabezado de entrega usando la información almacenada en el acuerdo entre socios comerciales entre las partes: la configuración del proceso, la información de configuración sobre el origen y las entidades de destino y las variables de proceso de interfaz de socio (PIP). El proceso, a continuación, envía el mensaje de señal al iniciador.  
  
   > [!NOTE]
   >  Si el mensaje es un mensaje de acción única, el flujo de mensajes está completado.  
  
4. El proceso público entra en un estado de espera (espera de una acción mediante el proceso privado del Respondedor).  
  
5. Las siguientes acciones pueden finalizar el estado de espera (espera de una acción mediante el proceso privado del Respondedor):  
  
   1. El proceso privado del Respondedor devuelve un mensaje de contenido del servicio de respuesta y encabezados, en respuesta al mensaje de acción original (que era un mensaje de doble acción).  
  
       Si el proceso público recibe el contenido del servicio de respuesta del proceso privado, el proceso público construye un mensaje RNIF que contiene el contenido del servicio. Para ello, ajuste la parte del mensaje de contenido del servicio con los encabezados que contienen la información de configuración acerca de las entidades de origen y destino y las variables PIP almacenadas en el contrato entre las partes.  
  
       El proceso público, envía el mensaje RNIF al iniciador mediante el puerto de vínculo de rol de la acción o señal.  
  
       Si el proceso público recibe una notificación que Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] hizo correctamente no enviar el mensaje, el proceso público envía ese estado al proceso privado y, a continuación, finaliza.  
  
       Si el proceso público recibe una notificación que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviado correctamente el mensaje, el proceso entra en un estado de espera (espera de una acción por el iniciador). Este estado de espera es similar del estado de espera que el iniciador se escribe cuando está esperando acción por parte del Respondedor.  
  
   2. El proceso público recibe un mensaje de notificación de error (ndel) del iniciador.  
  
   > [!NOTE]
   >  El proceso privado del Respondedor notificará el proceso público del servicio de respuesta después de que ha procesado correctamente el mensaje entrante. El servicio de respuesta después de proceso público ha recibido esta notificación (desde el `EndNotify` método en el `ApplicationAdapter` clase) el proceso público del Respondedor se correctamente completará.  
  
6. El proceso público del Respondedor entra en un estado de espera (en espera para recibir una señal del iniciador en respuesta al mensaje de respuesta que envía el proceso público del Respondedor).  
  
## <a name="see-also"></a>Vea también  
 [Procesos públicos](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [Proceso público del iniciador](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)   
 [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)   
 [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)