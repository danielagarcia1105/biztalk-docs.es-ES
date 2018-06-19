---
title: Planear la seguridad de mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826db8480d378342ee30993f67bbd60e27751d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264292"
---
# <a name="planning-message-security"></a>Planear la seguridad de los mensajes
Dependiendo de las directivas de seguridad de su empresa, puede serle útil considerar las preguntas de la tabla siguiente para determinar el nivel de seguridad que debe implementar en su entorno de BizTalk Server. Las respuestas a estas preguntas determinarán las características de seguridad que necesita para la mensajería.  
  
|Pregunta|Característica de seguridad de BizTalk Server|  
|--------------|-------------------------------------|  
|**Al recibir un mensaje:**||  
|¿Cómo determina la identidad del remitente del mensaje?|Puede identificar con certeza al remitente de un mensaje mediante el componente de resolución de entidades de la canalización de BizTalk y el certificado de firma, o el Id. de seguridad de Windows (SID). Para obtener más información, consulte [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).|  
|¿Sabe qué entidad le envió el mensaje?|Puede determinar si la entidad que le envió el mensaje ya es un socio comercial de su sistema mediante el componente de resolución de entidades de la canalización de BizTalk. Para obtener más información, consulte [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).|  
|¿Desea no recibir mensajes de entidades que no conoce?|Puede usar la función de autenticación necesaria en el puerto para requerir que BizTalk Server sólo procese los mensajes de entidades conocidas. Para obtener más información, consulte [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).|  
|**Al enviar un mensaje:**||  
|¿Cómo garantiza la privacidad de los mensajes salientes?|Puede cifrar el mensaje para asegurarse de que sólo lo pueda leer la entidad deseada. Para obtener más información, consulte [protección de mensaje saliente](../core/outbound-message-protection.md).|  
|¿Cómo impide que usuarios malintencionados manipulen el mensaje durante la transmisión?|Puede utilizar firmas digitales para garantizar la integridad del mensaje. Para obtener más información, consulte [protección de mensaje saliente](../core/outbound-message-protection.md).|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguridad para enviar y recibir mensajes](../core/security-for-sending-and-receiving-messages.md)  
  
-   [Cifrado y certificados de firma](../core/encryption-and-signing-certificates.md)  
  
-   [Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md)  
  
-   [Autorización del receptor de un mensaje](../core/authorizing-the-receiver-of-a-message.md)