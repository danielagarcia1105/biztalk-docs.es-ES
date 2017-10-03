---
title: Proceso iniciador privada | Documentos de Microsoft
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
- erros
- LOBs
- messages, message flow
- private processes, initiator
- private processes, message flow
- private processes, errors
ms.assetid: 8444a5c8-445a-4bbd-a793-a16816fcb397
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569d176a15ba5236d5f44d87406d9bbc0a19fca9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="initiator-private-process"></a>Proceso de iniciador privada
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza el proceso privado de iniciador (PrivateInitiator.odx) para procesar contenido de un servicio en un equipo de iniciador. Incluye lo siguiente:  
  
-   Crear el contenido del servicio de un mensaje original y enrutar el mensaje para el proceso público, en la ruta al socio comercial  
  
-   Procesar un mensaje de la señal de retorno y enrutarlos a la aplicación de línea de negocio (LOB)  
  
-   En el caso de un PIP de doble acción, procesar un mensaje de respuesta de vuelta y enviarlo a la aplicación de LOB.  
  
 El proceso privado también establece los metadatos y agrega los datos adjuntos. El proceso privado enruta los mensajes salientes para el proceso público, lo que agrega encabezados de RosettaNet Implementation Framework (RNIF) y el mensaje se prepara para su transmisión. El proceso privado enruta los mensajes entrantes a la tabla MessagesToLOB en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos, en la ruta a la aplicación de LOB.  
  
 Este proceso privada automatiza los procesos de pedido de compra o consulta de compra que utiliza 3A2 y 3A4 procesos de interfaz de socio (PIP). También controla los demás mensajes PIP. Puede personalizar el proceso privado para sus procesos empresariales específicos.  
  
## <a name="message-flow"></a>Flujo de mensajes  
 El flujo de mensajes a través del proceso privada iniciador es como sigue:  
  
1.  El proceso privado iniciador recibe el mensaje original de la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos. La aplicación de LOB de back-end enruta el mensaje a esta tabla.  
  
2.  El proceso privado prepara el contenido del servicio de un mensaje iniciado y lo envía al proceso público.  
  
3.  El proceso privado de iniciador, a continuación, entra en un estado de espera, escuchar una señal de valor devuelta.  
  
4.  Al recibir una señal devuelta desde el proceso público, el proceso privado construye un mensaje de señal y envía la señal a la tabla MessagesToLOB en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos, en la ruta a la aplicación de LOB.  
  
5.  El proceso privado envía una notificación a la aplicación de LOB que coloca el mensaje de señal en la tabla MessagesToLOB.  
  
6.  Si la versión RNIF 1.1, el proceso privado espera un mensaje de señal de confirmación de aceptación. Si recibe la señal, genera el mensaje de señal y envía la señal a la tabla MessagesToLOB, en la ruta a la aplicación de LOB.  
  
7.  Si los mensajes original era un mensaje de acción única, el proceso privado es completando después de que ha devuelto el mensaje de señal a la aplicación de LOB. Si el mensaje original era un mensaje de doble acción, el proceso privado escucha un mensaje de respuesta.  
  
8.  Si el proceso privado recibe un mensaje de respuesta desde el proceso público, crea un mensaje de respuesta en el formato de la aplicación de LOB. Esto implica la obtención de la plantilla de mensaje LOB, serializar el contenido XML del servicio y la carga de las partes del mensaje XML en el mensaje LOB.  
  
9. El proceso privado enruta el mensaje a la tabla MessagesToLOB en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos.  
  
10. Si el mensaje de respuesta tiene un archivo adjunto, el proceso privado llama a la herramienta AttachmentHelper para procesar los datos adjuntos.  
  
11. El proceso privado envía una notificación a la aplicación de LOB que colocar el mensaje de respuesta en la tabla MessagesToLOB y, a continuación, completa.  
  
## <a name="handling-of-incorrect-messages"></a>Tratamiento de los mensajes incorrectos  
 Cuando el proceso privado iniciador recibe un mensaje incorrecto de la aplicación de LOB, el proceso privado envía un mensaje de excepción al LOB. Sin embargo, el proceso privado no publica el mensaje incorrecto en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de BizTalk. Por lo tanto, no es posible ver el mensaje incorrecto en la consola de administración de BizTalk. Puede usar el mensaje de excepción para tener acceso al mensaje incorrecto para determinar qué mensaje era incorrecto y, a continuación, acceder al mensaje incorrecto en la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos. Sin embargo, este mensaje no sea el mismo que el mensaje que procesan la privada consumido, porque el proceso almacenado y el adaptador usado para procesar el mensaje edición. Agregan un elemento raíz y el espacio de nombres al mensaje. El proceso almacenado y el adaptador devuelven posiblemente varios registros.  
  
## <a name="see-also"></a>Vea también  
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [Proceso de respuesta privado](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)   
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Ejemplo de PrivateInitiator](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)