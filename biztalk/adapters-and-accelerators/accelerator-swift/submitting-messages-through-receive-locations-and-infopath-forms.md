---
title: "Enviar mensajes a través de ubicaciones de recepción y formularios de InfoPath | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6cddeca2eb80fbeb7c9fb5742e2838a860079d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a>Enviando mensajes a través de ubicaciones de recepción y formularios de InfoPath
Recibir ubicaciones reciban mensajes de envío en [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicaciones. Puede definir ubicaciones de recepción como puntos de conexión físicos configurados para recibir mensajes mediante un protocolo de transporte especificado. Por ejemplo, una ubicación de recepción puede configurarse para archivos de recepción que se coloquen en una carpeta de sistema de archivo en particular mediante el transporte de archivo.  
  
 Crear ubicaciones de recepción para puertos de recepción que agrupar lógicamente y administran ubicaciones de recepción. Para cada ubicación de recepción se especifica una canalización de recepción, que realiza el procesamiento real de mensajes recibidos en dicha ubicación de recepción determinada (descodificación, desensamblado, validación y así sucesivamente). Ubicaciones de recepción de recepción de A4SWIFT enlaza los puertos que agrupar lógicamente y administran ubicaciones de recepción.  
  
 Para enviar un mensaje SWIFT en una aplicación de A4SWIFT a través de una ubicación de recepción, el mensaje se coloca en una ubicación de recepción configurado, procesado por una canalización de recepción mediante el Desensamblador SWIFT, analizará y validado el Desensamblador SWIFT, y publicado en la base de datos de cuadro de mensajes. Después de que los mensajes se publican en la base de datos de cuadro de mensajes, otros componentes de la aplicación de A4SWIFT recuperan los mensajes (mediante suscripciones) para su procesamiento adicional. Por ejemplo, puede usar puertos de envío para el enrutamiento final.  
  
 Para obtener más información sobre cómo crear y configurar puertos de recepción y ubicaciones de recepción, vea [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
 También puede enviar un mensaje nuevo a través de un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formar, con la característica de reparación de mensajes y nuevo envío. Para ello, abra el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario para ese mensaje desde una carpeta en el sitio MRSR. Rellene los datos en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman, inicie sesión con su certificado y, a continuación, enviarla. La orquestación de reparación de mensajes y nuevo envío procesa el mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Acelerador de BizTalk para SWIFT en tiempo de ejecución](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)