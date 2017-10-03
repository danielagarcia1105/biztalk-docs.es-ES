---
title: Proceso privado Respondedor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- messages, private processes
- LOBs
- messages, message flow
- private processes, responder
- private processes, message flow
ms.assetid: 69b58320-977c-44d2-a7d6-f986213aecf2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8ba5ca38eb64859182242c944d260c9db15c880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="responder-private-process"></a>Proceso de respuesta privado
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza el proceso de servicio de respuesta privado (PrivateResponder.odx) para procesar el contenido de un servicio en un equipo de respuesta. Incluye lo siguiente:  
  
-   Enrutar un mensaje entrante a la aplicación de línea de negocio (LOB)  
  
-   Crear el contenido del servicio de un mensaje de respuesta y enrutar el mensaje para el proceso público, de ruta en el equipo de respuesta  
  
 El proceso privado también establece los metadatos y agrega los datos adjuntos al mensaje de respuesta. El proceso privado enruta los mensajes salientes para el proceso público de servicio de respuesta, lo que agrega encabezados de RosettaNet Implementation Framework (RNIF) y el mensaje se prepara para su transmisión. El proceso privado enruta los mensajes entrantes a la tabla MessagesToLOB en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos, en la ruta a la aplicación de LOB.  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye dos ejemplos de procesos privados de servicio de respuesta que se pueden personalizar para sus procesos empresariales específicos. El primero es el ejemplo de proceso de PrivateResponder que contiene el código para el proceso de servicio de respuesta privado instalado por [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]. Para obtener más información, consulte [PrivateResponder ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md).  
  
 El segundo ejemplo es el ejemplo de procesos privados PIP3A4PrivateResponder que automatiza los procesos de pedido de compra o consulta de compra que utiliza 3A2 y 3A4 procesos de interfaz de socio (PIP). También controla los demás mensajes PIP. Para obtener más información, consulte [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).  
  
## <a name="message-flow"></a>Flujo de mensajes  
 El flujo de mensajes a través del proceso privada del servicio de respuesta es el siguiente:  
  
1.  Proceso privado Respondedor recibe el mensaje de entrada original desde el proceso público de servicio de respuesta, en la ruta desde el equipo del iniciador.  
  
2.  El proceso privado construye el mensaje de la aplicación de LOB. Esto implica la obtención de la plantilla de mensaje LOB, serializar el contenido XML del servicio y la carga de las partes del mensaje XML en el mensaje LOB.  
  
3.  El proceso privado enruta el mensaje a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos, en la ruta a la aplicación de LOB de back-end.  
  
4.  Si el mensaje original tiene un archivo adjunto, el proceso privado llama al componente AttachmentHelper para procesar los datos adjuntos.  
  
5.  El proceso privado envía una notificación a la aplicación de LOB que guarda el mensaje de respuesta en la tabla MessagesToLOB.  
  
6.  Si el mensaje es un mensaje de acción única, el proceso privado está terminado.  
  
7.  Si el mensaje es un mensaje de doble acción, el proceso privado escucha una respuesta de la aplicación de LOB.  
  
8.  Cuando el proceso privado recibe la respuesta de la aplicación de LOB, genera un mensaje de respuesta y envía el mensaje para el proceso público.  
  
9. Espera a que el proceso privado para la señal desde el proceso público. Si recibe la señal, genera el mensaje de señal LOB y lo envía a la aplicación de LOB. Si la versión RNIF 1.1, proceso privado se escuchar para una señal de confirmación de segundo y tras recibirlo, se construirá el mensaje de señal LOB y enviar a la aplicación de LOB. El proceso privado notifica a la aplicación de LOB después de enviar cada mensaje de señal.  
  
10. Si el proceso privado recibe un mensaje de notificación de error (ndel) desde el proceso público, en la ruta del iniciador, el proceso privado crea un "[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]excepción", el mensaje y lo envía a la aplicación de LOB.  
  
## <a name="see-also"></a>Vea también  
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [Proceso de iniciador privada](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)   
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Ejemplo de PrivateResponder](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)