---
title: Proceso privado del iniciador | Microsoft Docs
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
- erros
- LOBs
- messages, message flow
- private processes, initiator
- private processes, message flow
- private processes, errors
ms.assetid: 8444a5c8-445a-4bbd-a793-a16816fcb397
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c718921f14e69916f2b1691d57fc51121bb965a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013877"
---
# <a name="initiator-private-process"></a>Proceso privado del iniciador
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proceso privado del iniciador (PrivateInitiator.odx) se utiliza para procesar contenido de un servicio en un equipo iniciador. Incluye lo siguiente:  
  
- Crear el contenido del servicio de un mensaje original y enrutar el mensaje para el proceso público, en la ruta al socio comercial  
  
- Procesar un mensaje de señal de retorno y enrutarlo a la aplicación de línea de negocio (LOB)  
  
- En el caso de un PIP de doble acción, procesar un mensaje de respuesta devuelto y enrutarlo a la aplicación de LOB.  
  
  Proceso privado también establece los metadatos y agrega los datos adjuntos. Proceso privado enruta los mensajes salientes para el proceso público, que agrega encabezados de RosettaNet Implementation Framework (RNIF) y el mensaje se prepara para su transmisión. Proceso privado enruta los mensajes entrantes a la tabla MessagesToLOB en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos, en la ruta a la aplicación de LOB.  
  
  Este proceso privada automatiza los procesos de pedido de compra o compra de consulta que utilizan 3A2 y 3A4 procesos de interfaz de socio (PIP). También controla los demás mensajes PIP. Puede personalizar el proceso privado para sus procesos empresariales específicos.  
  
## <a name="message-flow"></a>Flujo de mensajes  
 El flujo de mensajes a través del proceso privado del iniciador es como sigue:  
  
1. Proceso privado del iniciador recibe el mensaje original de la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos. La aplicación de LOB de back-end enruta el mensaje a esta tabla.  
  
2. Proceso privado prepara el contenido del servicio de un mensaje iniciado y lo envía al proceso público.  
  
3. Proceso privado del iniciador, a continuación, entra en un estado de espera, escuchar una señal de valor devuelto.  
  
4. Al recibir una señal devuelta desde el proceso público, construye un mensaje de señal proceso privado y envía la señal a la tabla MessagesToLOB en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos, en la ruta a la aplicación de LOB.  
  
5. Proceso privado envía una notificación a la aplicación de LOB que coloca el mensaje de señal en la tabla MessagesToLOB.  
  
6. Si la versión RNIF 1.1, el proceso privado espera un mensaje de señal de confirmación de aceptación. Si recibe la señal, se construye el mensaje de señal y envía la señal a la tabla MessagesToLOB, en la ruta a la aplicación de LOB.  
  
7. Si los mensajes original era un mensaje de acción única, el proceso privado completada después de que ha devuelto el mensaje de señal a la aplicación de LOB. Si el mensaje original era un mensaje de doble acción, el proceso privado escucha un mensaje de respuesta.  
  
8. Si el proceso privado recibe un mensaje de respuesta desde el proceso público, construye un mensaje de respuesta en el formato de la aplicación de LOB. Esto implica la obtención de la plantilla de mensaje LOB, serializar el contenido XML del servicio y la carga de las partes del mensaje XML en el mensaje LOB.  
  
9. Proceso privado enruta el mensaje a la tabla MessagesToLOB en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos.  
  
10. Si el mensaje de respuesta tiene datos adjuntos, el proceso privado llama a la herramienta AttachmentHelper para procesar los datos adjuntos.  
  
11. Proceso privado envía una notificación a la aplicación de LOB que colocar el mensaje de respuesta en la tabla MessagesToLOB y, a continuación, está completa.  
  
## <a name="handling-of-incorrect-messages"></a>Tratamiento de los mensajes incorrectos  
 Cuando el proceso privado del iniciador recibe un mensaje incorrecto de la aplicación de LOB, el proceso privado envía un mensaje de excepción a la línea de negocio. Sin embargo, el proceso privado no registra el mensaje incorrecto en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de BizTalk. Por lo tanto, no es posible ver el mensaje incorrecto en la consola de administración de BizTalk. Puede usar el mensaje de excepción para tener acceso al mensaje incorrecto para determinar qué mensaje era incorrecto y, a continuación, acceder al mensaje incorrecto en la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos. Sin embargo, este mensaje puede no ser igual que el mensaje que procesan la privada consumido, porque el proceso almacenado y el adaptador utilizado para procesar el mensaje edición. Agregan un elemento raíz y el espacio de nombres al mensaje. El proceso almacenado y el adaptador posiblemente devuelven varios registros.  
  
## <a name="see-also"></a>Vea también  
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [Proceso privado del Respondedor](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)   
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Ejemplo de PrivateInitiator](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)