---
title: Flujo en el iniciador de BTARN de mensajes | Microsoft Docs
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
- initiator BTARN
ms.assetid: 315f3d4c-5e40-4b8e-b135-9da98dc2db1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160f40d4dfd0d11a7bd5a5c7c127d62b3e42a2cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004029"
---
# <a name="message-flow-in-the-initiator-btarn"></a>Flujo de mensajes en el iniciador de BTARN
Flujo de mensajes en un equipo iniciador empieza por recibir un mensaje de la aplicación de línea de negocio back-end, en su formato de propietario. Implica convertir a un marco de implementación de RosettaNet (RNIF) de ese mensaje-mensaje compatible y, a continuación, enviar el mensaje a través de Internet para el equipo de respuesta.  
  
 Si el proceso de interfaz de socio (PIP) es la única acción, la única respuesta es un mensaje de señal de confirmación. Para obtener información sobre el flujo de mensajes de acción única, vea "Flujo de un iniciado por mensaje de" más adelante en este tema. Si el PIP es doble acción, el iniciador recibe un mensaje de respuesta y responde con una confirmación, además del flujo de mensajes de acción única.  
  
 Si el PIP es asincrónico, se produce cada transmisión de mensajes a través de Internet en una conexión HTTP diferente. Si el PIP es sincrónico, se produce cada transmisión del mensaje en la misma conexión, que contiene el adaptador de HTTP hasta que el proceso está completa. En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación en el equipo iniciador en respuesta al mensaje de solicitud inicial. El mensaje de respuesta sirve como confirmación.  
  
## <a name="btarn-components-on-the-initiator-computer"></a>Componentes en el equipo iniciador de BTARN  
 Como un mensaje fluye a través de [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en el equipo iniciador, los siguientes componentes procesará el mensaje:  
  
- Adaptador de SQL  
  
- Canalización de recepción de XML  
  
- Proceso privado del iniciador  
  
- Proceso público del iniciador  
  
- Canalización de envío XML  
  
- adaptador de HTTP  
  
- Página RNIFSend.aspx  
  
  Para obtener más información acerca de estos componentes y cómo procesar el mensaje, vea [procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).  
  
## <a name="flow-of-an-initiated-message"></a>Flujo de un mensaje iniciado  
 Los pasos siguientes describen el flujo de mensajes de un mensaje iniciado por medio del iniciador [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] equipo. En la ilustración siguiente se muestra este proceso.  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")  
  
1. La aplicación de línea de negocio envía el mensaje a Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía el mensaje desde el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos para el adaptador de SQL.  
  
3. El XML de recepción canalización hace sencillo validación de XML del mensaje.  
  
4. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enruta el mensaje a la base de datos de cuadro de mensajes.  
  
5. Proceso privado procesa el contenido del mensaje del servicio.  
  
6. El proceso público procesa los encabezados RNIF del mensaje.  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enruta el mensaje a la base de datos de cuadro de mensajes.  
  
8. La canalización de envío realiza el ensamblado y firma o cifrado y codificación del mensaje.  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enruta el mensaje al adaptador de HTTP.  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enruta el mensaje a la página RNIFSend.aspx, que envía a través de Internet a su destino.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [Flujo de mensajes en el Respondedor de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md)   
 [Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)