---
title: Enviar mensajes a través de ubicaciones de recepción y formularios de InfoPath | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4589649be79ce369f0e6756ae7f96615d4a36c0f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005125"
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a>Enviando mensajes a través de ubicaciones de recepción y formularios de InfoPath
Recibir ubicaciones reciban mensajes de envío en [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicaciones. Puede definir ubicaciones de recepción como puntos de conexión físicos configurados para recibir mensajes mediante un protocolo de transporte especificado. Por ejemplo, una ubicación de recepción puede configurarse para archivos de recepción que se coloquen en una carpeta de sistema de archivo en particular mediante el transporte de archivo.  
  
 Crear ubicaciones de recepción para puertos de recepción que agrupar lógicamente y administran ubicaciones de recepción. Para cada ubicación de recepción se especifica una canalización de recepción, que realiza el procesamiento real de mensajes recibidos en dicha ubicación de recepción determinada (descodificación, desensamblado, validación y así sucesivamente). Ubicaciones de recepción de recepción de A4SWIFT enlaza los puertos que agrupar lógicamente y administran ubicaciones de recepción.  
  
 Para enviar un mensaje SWIFT en una aplicación de A4SWIFT a través de una ubicación de recepción, el mensaje se coloca en una ubicación de recepción configurado, procesado por una canalización de recepción mediante el Desensamblador SWIFT, analizará y validado el Desensamblador SWIFT, y publicado en la base de datos de cuadro de mensajes. Después de que los mensajes se publican en la base de datos de cuadro de mensajes, otros componentes de la aplicación de A4SWIFT recuperan los mensajes (mediante suscripciones) para su procesamiento adicional. Por ejemplo, puede usar puertos de envío para el enrutamiento final.  
  
 Para obtener más información sobre cómo crear y configurar puertos de recepción y ubicaciones de recepción, consulte la Ayuda de BizTalk Server.  
  
 También puede enviar un mensaje nuevo a través de un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formar, con la característica de reparación de mensajes y nuevo envío. Para ello, abra el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario para ese mensaje desde una carpeta en el sitio MRSR. Rellene los datos en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman, inicie sesión con su certificado y, a continuación, enviarla. La orquestación de reparación de mensajes y nuevo envío procesa el mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Acelerador de BizTalk para el tiempo de ejecución de SWIFT](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)