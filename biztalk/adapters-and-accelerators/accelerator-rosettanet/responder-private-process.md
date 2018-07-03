---
title: Proceso privado del Respondedor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- messages, private processes
- LOBs
- messages, message flow
- private processes, responder
- private processes, message flow
ms.assetid: 69b58320-977c-44d2-a7d6-f986213aecf2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 045559ad13492055e0e63a0cb19c4e7e780d5252
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989621"
---
# <a name="responder-private-process"></a>Proceso privado del Respondedor
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] usa el proceso privado del Respondedor (PrivateResponder.odx) para procesar contenido de un servicio en un equipo de servicio de respuesta. Incluye lo siguiente:  
  
- Enrutamiento de un mensaje entrante a la aplicación de línea de negocio (LOB)  
  
- Crear el contenido de un mensaje de respuesta del servicio y enrutar el mensaje para el proceso público, de ruta en el equipo de respuesta  
  
  Proceso privado también establece los metadatos y agrega los datos adjuntos al mensaje de respuesta. Proceso privado enruta los mensajes salientes para el proceso público del Respondedor, que agrega encabezados de RosettaNet Implementation Framework (RNIF) y el mensaje se prepara para su transmisión. Proceso privado enruta los mensajes entrantes a la tabla MessagesToLOB en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos, en la ruta a la aplicación de LOB.  
  
  El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye dos ejemplos de procesos privados de servicio de respuesta que se pueden personalizar para sus procesos empresariales específicos. El primero es el ejemplo de proceso de PrivateResponder que contiene el código para el proceso privado del Respondedor instalado de forma [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]. Para obtener más información, consulte [ejemplo de PrivateResponder](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md).  
  
  El segundo ejemplo es el ejemplo de procesos privado PIP3A4PrivateResponder que automatiza los procesos de pedido de compra o compra de consulta que utilizan 3A2 y 3A4 procesos de interfaz de socio (PIP). También controla los demás mensajes PIP. Para obtener más información, consulte [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).  
  
## <a name="message-flow"></a>Flujo de mensajes  
 El flujo de mensajes a través del proceso privado del Respondedor es como sigue:  
  
1. El proceso privado del Respondedor recibe el mensaje entrante original desde el proceso público del Respondedor, en la ruta desde el equipo iniciador.  
  
2. Proceso privado construye el mensaje de la aplicación de LOB. Esto implica la obtención de la plantilla de mensaje LOB, serializar el contenido XML del servicio y la carga de las partes del mensaje XML en el mensaje LOB.  
  
3. Proceso privado enruta el mensaje a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos, en la ruta a la aplicación de LOB de back-end.  
  
4. Si el mensaje original tiene datos adjuntos, el proceso privado llama al componente de AttachmentHelper para procesar los datos adjuntos.  
  
5. Proceso privado envía una notificación a la aplicación de LOB que guarda el mensaje de respuesta en la tabla MessagesToLOB.  
  
6. Si el mensaje es un mensaje de acción única, el proceso privado está completado.  
  
7. Si el mensaje es un mensaje de doble acción, el proceso privado realiza escuchas para una respuesta de la aplicación de LOB.  
  
8. Cuando el proceso privado recibe la respuesta de la aplicación de LOB, construye un mensaje de respuesta y envía el mensaje para el proceso público.  
  
9. Proceso privado espera a que la señal de que el proceso público. Si recibe la señal, construye el mensaje de señal LOB y lo envía a la aplicación de LOB. Si la versión RNIF 1.1, proceso privado se escuchar una segunda señal de confirmación y, al recibirlo, se construirá el mensaje de señal LOB y enviarlo a la aplicación de LOB. Proceso privado notifica a la aplicación de LOB después de enviar cada mensaje de señal.  
  
10. Si el proceso privado recibe un mensaje de notificación de error (ndel) desde el proceso público, en la ruta del iniciador, proceso privado crea un "[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]excepción" del mensaje y lo envía a la aplicación de LOB.  
  
## <a name="see-also"></a>Vea también  
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [Proceso privado del iniciador](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)   
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Ejemplo de PrivateResponder](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)