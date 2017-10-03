---
title: Adaptador de SMTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, about SMTP adapters
- SMTP adapters, authenticating
- send adapters, SMTP adapters
- authenticating, SMTP adapters
- SMTP adapters
- SMTP adapters, send adapters
ms.assetid: b712f76d-3ce4-4780-9627-951e5951bd8a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0d0d16bf266d0b636aa9955b5c25b37d9ab54d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter"></a>Adaptador de SMTP
El protocolo de transferencia de correo (SMTP) se utiliza para intercambiar información entre un servidor que ejecuta Microsoft BizTalk Server y otras aplicaciones a través del protocolo SMTP. BizTalk Server puede enviar mensajes a otras aplicaciones mediante la creación de un mensaje de correo electrónico y su entrega a una dirección de correo electrónico especificada. De forma interna, el adaptador de envío SMTP crea un mensaje de correo electrónico basado en SMTP y lo envía a una dirección de correo electrónico de destino. La dirección de correo electrónico de destino es una propiedad del adaptador de SMTP. El Explorador de BizTalk expone esta propiedad cuando configura el puerto de envío de SMTP.  
  
 El adaptador de SMTP admite caracteres comodín en el **TO**, **FROM**, **CC** y **asunto** propiedades y se resuelve en su real valores. Si los caracteres comodín en el **TO**, **FROM**, y **CC** propiedades no se pueden resolver, el protocolo de transporte SMTP registra un error y pone el mensaje en la cola de suspensión o redirige el mensaje al transporte de reserva. Si los caracteres comodín no se puede resolver en el **asunto** propiedad, el mensaje se envía con el **asunto** propiedad especificada exactamente igual que en la propiedad (por ejemplo, "Message % MessageID %").  
  
 De forma predeterminada, el texto de mensaje de los mensajes SMTP es texto sin formato. Para utilizar HTML en los cuerpos de los mensajes, puede configurar el adaptador para utilizar el contenido de un archivo HTML para el texto de mensaje.  
  
 Para obtener más información acerca de los problemas de seguridad de SMTP, consulte [recomendaciones de seguridad del adaptador de SMTP](../core/smtp-adapter-security-recommendations.md).  
  
 El adaptador de SMTP consta de un único adaptador, un adaptador de envío. El adaptador de envío controla los puertos de envío que utilizan el adaptador de SMTP.  
  
 En este tema se describe el flujo de un mensaje a través del adaptador de envío SMTP.  
  
 **Adaptador de envío SMTP**  
  
 El adaptador de envío SMTP obtiene los mensajes del servidor y los envía a un servidor SMTP que los envía a los destinatarios de correo electrónico. El adaptador de envío SMTP obtiene el contenido del mensaje de la parte del cuerpo del objeto de mensaje de BizTalk, del archivo especificado, o de un texto que se introdujo en un cuadro de diálogo que está disponible cuando se configura el adaptador.  
  
 Después de que el adaptador de envío SMTP haya enviado el mensaje correctamente al servidor SMTP, el adaptador de envío SMTP elimina el mensaje de la base de datos de cuadro de mensajes.  
  
 El adaptador de envío SMTP puede solicitar la notificación de entrega y la confirmación de lectura de los mensajes enviados a través del adaptador de envío SMTP. El adaptador de SMTP entrega la notificación de notificación y lectura a la dirección especificada en el protocolo SMTP **de** encabezado.  
  
 **Autenticación con el servidor SMTP**  
  
 Si necesita autenticación de servidor SMTP, el adaptador de envío SMTP utiliza uno de los tipos de autenticación siguientes:  
  
-   **Básica.** El servidor SMTP utiliza credenciales proporcionadas por el usuario para autenticación.  
  
-   **Cuenta de proceso (NTLM).** El servidor SMTP utiliza credenciales del proceso actual para autenticación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar el adaptador de SMTP](../core/configuring-the-smtp-adapter.md)  
  
-   [Restricciones al configurar el adaptador de SMTP](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [Recomendaciones de seguridad del adaptador de SMTP](../core/smtp-adapter-security-recommendations.md)