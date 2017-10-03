---
title: Primitivas de extremo a extremo en tiempo real de FileAct adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8591120-7259-49cb-90ac-954d8be226ed
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95e52d4fbd5ec0df8ee580583f429ffe9e0f08d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a>Primitivas de extremo a extremo de FileAct adaptador en tiempo real
Primitivas de SWIFTNet son un par de documentos XML intercambiados entre la aplicación y el vínculo de SWIFTNet (SNL). Para cada existen primitivo, de-to-end son dos versiones de la primitiva: uno en el lado cliente (o envío) y otro en el servidor (o recepción). Esto incluye un total de cuatro mensajes: archivo colocar primitiva, primitivos de Get File y una notificación de entrega de envío para cada uno.  
  
 La siguiente ilustración muestra a las primitivas de extremo a extremo FileAct.  
  
 ![FileAct final &#45; a &#45; primitivas final](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")  
  
## <a name="put-file"></a>Copiar archivo  
 Una aplicación inicia la primitiva colocar archivos para enviar un archivo en el sistema de archivos de otro usuario SWIFTNet. Como una función to-end, existen tipos primitivos de colocar archivos de lado de cliente y servidor. Estos colaborarán juntos para completar correctamente una transferencia de archivos.  
  
 Cada tal colaboración envía un único archivo. Hay varios primitivos colocar archivos pueden realizarse en paralelo.  
  
## <a name="get-file"></a>Obtener archivo  
 Una aplicación inicia la primitiva Get File para recuperar un archivo desde el sistema de archivos de otro usuario SWIFTNet. Como una función to-end, existen tipos primitivos de obtener archivo de cliente y servidor. Estos colaborarán juntos para completar correctamente una transferencia de archivos.  
  
 Cada tal colaboración recupera un único archivo. Hay varios primitivos Get File pueden realizarse en paralelo.  
  
## <a name="send-delivery-notification"></a>Enviar una notificación de entrega  
 Cada archivo Put y cada archivo obtener primitivo tienen la opción de hacer que el lado emisor de la solicitud de archivo que el lado receptor devuelven una notificación de entrega relacionada con la transferencia de archivos. Para un tipo primitivo archivo Put, el mensaje de solicitud contiene la solicitud para una notificación de entrega.  
  
 En el caso de un archivo obtener primitivo, el mensaje de respuesta contiene la solicitud para una notificación de entrega.  
  
 En cualquier caso, después de comprobar que el archivo se ha recibido en su totalidad (realizando una de las primitivas de estado para comprobar que la transferencia alcance el estado completado) y que el archivo ha sido adecuadamente seguro almacenado (por ejemplo, en un sistema de back-office), el aplicación receptora ejercicios por separado de la primitiva de notificación de entrega para devolver una confirmación positiva de entrega al remitente. Como una función to-end, existen tipos primitivos de notificación de entrega de cliente y servidor. Estos colaborarán juntos para completar correctamente una notificación de entrega de archivos.  
  
 Notificación de entrega requiere el Diseñador de servicio establecer y aplicar un protocolo entre los remitentes y receptores de archivos.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [Estado del adaptador de FileAct supervisión](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)