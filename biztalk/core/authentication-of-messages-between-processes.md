---
title: Autenticación de mensajes entre procesos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PID
- security, warnings
- processing, messages
- processing, security
- messages, processing
- security, messages
- MessageBox database, authenticating
- SSID
- authenticating, warnings
ms.assetid: fa746ee3-fc22-4e63-a5cc-8bc0cbeb536b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c54fb463353ed6551dcbf5764fae05e63fdb778
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231308"
---
# <a name="authentication-of-messages-between-processes"></a>Autenticación de mensajes entre procesos
La siguiente ilustración muestra las características de seguridad de BizTalk Server que permiten autenticar mensajes entre distintos hosts de BizTalk.  
  
 ![Características de seguridad para autenticar mensajes](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")  
Características de seguridad usadas por BizTalk Server para autenticar mensajes entre procesos.  
  
 Una vez que BizTalk Server recibe un mensaje, lo descifra y valida, y tiene un Id. de entidad (PID) y un certificado válidos para identificar al remitente, la base de datos de cuadro de mensajes está lista para comprobar las suscripciones a las que corresponde el mensaje y enviar éste a otros hosts para su posterior procesamiento.  
  
 Como un mensaje fluye de un proceso a otro, a menudo es necesario pasar la identidad de su remitente original a procesos inferiores para autorización, resolución de entidades y lógica de negocios relacionadas con el remitente. No obstante, si se permitiera que todos los hosts transmitieran esta información sin ningún tipo de mecanismo de seguridad o de confianza aumentaría drásticamente la necesidad de comprobar la fiabilidad de todo el código y los objetos de usuario (por ejemplo, las orquestaciones, los adaptadores, componentes de canalización y los functoids).  
  
 Con el fin de proporcionar una forma de diferenciar el nivel de confianza para código y objetos de usuario, BizTalk Server ofrece Autenticación de confianza como una propiedad de host. Cuando la base de datos de cuadro de mensajes recibe un mensaje de un host que no se ha configurado con autenticación de confianza, dicha base de datos sobrescribe el PID con el Id. de invitado y el SSID con la cuenta de servicio en la que se ejecuta la instancia del host. Cuando un host se marca como con autenticación de confianza, BizTalk le permite que especifique cualquier SID de remitente (SSID) y cualquier Id. de entidad (PID) en los mensajes que agrega a la cola de la base de datos de cuadro de mensajes.  
  
 Al especificar los hosts que son o no de confianza, puede definir límites de seguridad en los que se confíe o desconfíe en el código y los objetos de usuario. Es decir, los objetos de usuario y código implementados en hosts que se hayan configurado con Autenticación de confianza deben ser más fiables que los objetos de usuario y código implementados en hosts que no se hayan configurado así. Para obtener más información sobre cómo configurar el host de confianza de autenticación, vea [cómo modificar propiedades de Host](../core/how-to-modify-host-properties.md).  
  
 Cuando la base de datos de cuadro de mensajes recibe un mensaje, BizTalk Server realiza los pasos siguientes para comprobar la autenticación de confianza de la instancia de host que envía el mensaje a dicha base de datos:  
  
1.  En primer lugar, la base de datos de cuadro de mensajes determina si el host remitente se ha configurado con autenticación de confianza comprobando que el SSID corresponde a la cuenta de servicio de instancia de host de un host de confianza.  
  
2.  Si el host que envía el mensaje a la base de datos de cuadro de mensajes tiene autenticación de confianza, la base de datos deja el SSID y el PID en el contexto del mensaje "tal cual" a menos que estén vacíos. Si el SSID está vacío, la base de datos de cuadro de mensajes lo rellena con el SID del proceso que realiza la llamada, también denominado SID del host (HSID). Si el PID está vacío, lo establece como el Id. de invitado.  
  
3.  Si el host que envía el mensaje a la base de datos de cuadro de mensajes no se ha configurado con autenticación de confianza, el SSID se rellena con el HSID y el PID se define como Invitado, con independencia de si esos campos ya tenían valores.  
  
> [!IMPORTANT]
>  Si desea que un proceso inferior conozca el SSID y el PID del remitente original del mensaje, debe establecer todos los hosts por los que pase el mensaje como con autenticación de confianza. Además, en casos tales como cuando el mensaje se recibe y posteriormente se utiliza para construir mensajes salientes en una orquestación, el SSID y el PID recibidos en mensajes entrantes deben agregarse explícitamente como una propiedad a los mensajes salientes para transmitir estas identidades.  
  
> [!IMPORTANT]
>  Si configuró el host en que se está ejecutando una canalización con autenticación de confianza, BizTalk Server considera que la canalización es un entorno de confianza. Por tanto, es muy importante que compruebe que cualquier componente personalizado que se incluya en una canalización de BizTalk ejecutada en un host con autenticación de confianza también es fiable.  
  
> [!NOTE]
>  No se puede utilizar la misma cuenta de servicio para hosts de autenticación de confianza y para hosts que no son de confianza de autenticación.  
  
## <a name="see-also"></a>Vea también  
 [Autenticación de mensajes entrantes](../core/inbound-message-authentication.md)   
 [Protección de mensajes salientes](../core/outbound-message-protection.md)   
 [Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md)   
 [Autorización del receptor de un mensaje](../core/authorizing-the-receiver-of-a-message.md)