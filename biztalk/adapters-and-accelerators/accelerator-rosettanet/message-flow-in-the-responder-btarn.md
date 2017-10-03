---
title: Flujo en el servicio de respuesta BTARN de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ad33db4f67336f41ac868a7a14e1266a85dd45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-flow-in-the-responder-btarn"></a>Flujo de mensajes en el servicio de respuesta BTARN
Flujo de mensajes en un equipo de servicio de respuesta se inicia con la recepción de un mensaje a través de Internet desde el equipo del iniciador. Implica convertir ese mensaje de RosettaNet Implementation Framework (RNIF)-mensaje conforme a un mensaje en el formato de propietario de la aplicación de back-end y, a continuación, enrutar el mensaje a la aplicación de línea de negocio.  
  
 Si el proceso de interfaz de socio (PIP) es la única acción, la respuesta sola es un mensaje de señal de confirmación. Si el PIP es doble acción, el servicio de respuesta va a procesar y enviar un mensaje de respuesta y posteriormente, recibirá una confirmación de esa respuesta.  
  
 Si el PIP es asincrónico, se produce cada transmisión de un mensaje a través de Internet en una conexión HTTP diferente. Si el PIP es sincrónico, cada transmisión del mensaje se produce en la misma conexión que el adaptador de HTTP contiene hasta que el proceso está completando. En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación al equipo iniciador en respuesta al mensaje de solicitud inicial. El mensaje de respuesta sirve como confirmación.  
  
## <a name="btarn-components-on-the-responder-computer"></a>Componentes BTARN en el equipo de servicio de respuesta  
 Como un mensaje fluye a través de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en el equipo de servicio de respuesta, los siguientes componentes procesarán el mensaje:  
  
-   Página de trabajo RNIFReceive.aspx  
  
-   adaptador de HTTP  
  
-   Canalización de recepción  
  
-   Proceso público de servicio de respuesta  
  
-   Procesos privados del servicio de respuesta  
  
-   Adaptador de SQL  
  
-   Canalización de envío  
  
 Para obtener más información acerca de estos componentes y cómo procesa un mensaje, vea [procesamiento de mensajes de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).  
  
## <a name="message-flow-on-the-responder-computer"></a>Flujo de mensajes en el equipo de servicio de respuesta  
 El flujo de mensajes de un mensaje recibido mediante el servicio de respuesta [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] equipo es como sigue:  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")  
  
1.  La página aspx RNIFReceive recibe el mensaje entrante desde el iniciador.  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]envía el mensaje al adaptador de HTTP, que lo envía a la canalización de recepción.  
  
3.  La canalización de recepción descodifica, desensambla y realiza la resolución de entidades en el mensaje y, a continuación, convierte el mensaje en el formato de propietario de la aplicación de línea de negocio de back-end.  
  
4.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]enruta el mensaje a la base de datos de cuadro de mensajes.  
  
5.  El proceso público procesa los encabezados RNIF del mensaje.  
  
6.  El proceso privado procesa el contenido del servicio del mensaje. Genera una confirmación de que se devuelve para el proceso público, la base de datos de cuadro de mensajes, a la canalización de envío y, a continuación, en el adaptador de HTTP de devolución a través de Internet al iniciador.  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]enruta el mensaje a la base de datos de cuadro de mensajes.  
  
8.  La canalización de envío ensambla y, a continuación, firma y cifra/codifica el mensaje.  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]enruta el mensaje al adaptador de SQL.  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]envía el mensaje a [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]y a la aplicación de línea de negocio en el back-end.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de mensajes de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [Flujo de mensajes en el iniciador BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)