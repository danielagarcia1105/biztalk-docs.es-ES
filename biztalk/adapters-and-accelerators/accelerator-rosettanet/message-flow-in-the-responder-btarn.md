---
title: Flujo en el Respondedor de BTARN de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b629e53f7126c15f84640c8862644beb78e2a5cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980709"
---
# <a name="message-flow-in-the-responder-btarn"></a>Flujo de mensajes en el Respondedor de BTARN
Inicia el flujo de mensajes en un equipo de servicio de respuesta recibe un mensaje a través de Internet desde el equipo iniciador. Implica convertir ese mensaje de RosettaNet Implementation Framework (RNIF)-mensaje conforme a un mensaje en el formato de propietario de la aplicación de back-end y, a continuación, enrutar el mensaje a la aplicación de línea de negocio.  
  
 Si el proceso de interfaz de socio (PIP) es la única acción, la única respuesta es un mensaje de señal de confirmación. Si el PIP es doble acción, el servicio de respuesta procesar y enviar un mensaje de respuesta y posteriormente, recibirá una confirmación para esa respuesta.  
  
 Si el PIP es asincrónico, se produce cada transmisión de mensajes a través de Internet en una conexión HTTP diferente. Si el PIP es sincrónico, se produce cada transmisión del mensaje en la misma conexión, que contiene el adaptador de HTTP hasta que el proceso está completa. En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación en el equipo iniciador en respuesta al mensaje de solicitud inicial. El mensaje de respuesta sirve como confirmación.  
  
## <a name="btarn-components-on-the-responder-computer"></a>Componentes BTARN en el equipo de respuesta  
 Como un mensaje fluye a través de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en el equipo de servicio de respuesta, los siguientes componentes procesará el mensaje:  
  
- Página de trabajo RNIFReceive.aspx  
  
- adaptador de HTTP  
  
- Canalización de recepción  
  
- Proceso público del Respondedor  
  
- Proceso privado del Respondedor  
  
- Adaptador de SQL  
  
- Canalización de envío  
  
  Para obtener más información acerca de estos componentes y cómo procesar el mensaje, vea [procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).  
  
## <a name="message-flow-on-the-responder-computer"></a>Flujo de mensajes en el equipo de respuesta  
 El flujo de mensajes de un mensaje recibido a través del servicio de respuesta [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] equipo es como sigue:  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")  
  
1. La página de aspx RNIFReceive recibe el mensaje entrante del iniciador.  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía el mensaje al adaptador de HTTP, que lo envía a la canalización de recepción.  
  
3. La canalización de recepción descodifica, desensambla y realiza la resolución de entidades en el mensaje y, a continuación, convierte el mensaje en el formato propietario de la aplicación de línea de negocio de back-end.  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enruta el mensaje a la base de datos de cuadro de mensajes.  
  
5. El proceso público procesa los encabezados RNIF del mensaje.  
  
6. Proceso privado procesa el contenido del mensaje del servicio. Genera una confirmación que se devuelve para el proceso público, la base de datos de cuadro de mensajes, a la canalización de envío y, a continuación, para el adaptador de HTTP para la devolución a través de Internet al iniciador.  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enruta el mensaje a la base de datos de cuadro de mensajes.  
  
8. La canalización de envío ensambla y, a continuación, firma o cifra/codifica el mensaje.  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enruta el mensaje al adaptador de SQL.  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía el mensaje a [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]y a la aplicación de línea de negocio en el back-end.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [Flujo de mensajes en el iniciador de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)