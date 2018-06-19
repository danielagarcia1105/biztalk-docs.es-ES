---
title: Flujo en el iniciador BTARN de mensajes | Documentos de Microsoft
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
ms.openlocfilehash: 85fed6404627fd8abfa9d50e7d56d98ff7306f09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210596"
---
# <a name="message-flow-in-the-initiator-btarn"></a>Flujo de mensajes en el iniciador BTARN
Flujo de mensajes en un equipo iniciador comienza con recibir un mensaje de la aplicación de línea de negocio de back-end, en su formato de propietario. Implica convertir a un marco de implementación de RosettaNet (RNIF) de ese mensaje-mensaje compatible y, a continuación, enviar el mensaje a través de Internet en el equipo de servicio de respuesta.  
  
 Si el proceso de interfaz de socio (PIP) es la única acción, la respuesta sola es un mensaje de señal de confirmación. Para obtener información acerca del flujo de mensajes de acción única, vea "Flujo de un inició mensaje" más adelante en este tema. Si el PIP es doble acción, el iniciador recibirá un mensaje de respuesta y responder con una confirmación, además del flujo de mensajes de acción única.  
  
 Si el PIP es asincrónico, se produce cada transmisión de un mensaje a través de Internet en una conexión HTTP diferente. Si el PIP es sincrónico, cada transmisión del mensaje se produce en la misma conexión que el adaptador de HTTP contiene hasta que el proceso está completando. En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación al equipo iniciador en respuesta al mensaje de solicitud inicial. El mensaje de respuesta sirve como confirmación.  
  
## <a name="btarn-components-on-the-initiator-computer"></a>Componentes BTARN en el equipo iniciador  
 Como un mensaje fluye a través de [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en el equipo iniciador, los siguientes componentes procesarán el mensaje:  
  
-   Adaptador de SQL  
  
-   Canalización de recepción de XML  
  
-   Proceso privado de iniciador  
  
-   Proceso público de iniciador  
  
-   Canalización de envío XML  
  
-   adaptador de HTTP  
  
-   Página RNIFSend.aspx  
  
 Para obtener más información acerca de estos componentes y cómo procesa un mensaje, vea [procesamiento de mensajes de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).  
  
## <a name="flow-of-an-initiated-message"></a>Flujo de un mensaje iniciado  
 Los siguientes pasos describen el flujo de mensajes de un mensaje iniciado por medio del iniciador [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] equipo. En la ilustración siguiente se muestra este proceso.  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")  
  
1.  La aplicación de línea de negocio envía el mensaje a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]envía el mensaje desde el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos para el adaptador de SQL.  
  
3.  El XML de recepción canalización hace simple validación de XML del mensaje.  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]enruta el mensaje a la base de datos de cuadro de mensajes.  
  
5.  El proceso privado procesa el contenido del servicio del mensaje.  
  
6.  El proceso público procesa los encabezados RNIF del mensaje.  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]enruta el mensaje a la base de datos de cuadro de mensajes.  
  
8.  La canalización de envío realiza el ensamblado y firma o cifrado y codificación del mensaje.  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]enruta el mensaje al adaptador de HTTP.  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]enruta el mensaje a la página RNIFSend.aspx, que lo envía a través de Internet a su destino.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de mensajes de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [Flujo de mensajes en el servicio de respuesta BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md)   
 [Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)