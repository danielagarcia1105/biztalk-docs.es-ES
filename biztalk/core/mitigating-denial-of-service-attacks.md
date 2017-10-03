---
title: "Denegación de servicio de mitigar los ataques | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IPSec, message protection
- messages, size
- security, configuring
- Authentication Required property
- security, Internet Information Services (IIS) Lockdown Tool
- security, Denial of Service attacks
- discretionary access control lists (DACLs)
- IPSec, data protection
- Internet Information Services (IIS) Lockdown Tool
- Denial of Service attacks
ms.assetid: f39c0d0a-b890-4c48-874d-5cafbc71473c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94fe45a2882d85164ab81c13e78fca2ac26d0ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mitigating-denial-of-service-attacks"></a>Denegación de servicio de mitigar los ataques
Se recomienda utilizar las siguientes técnicas de mitigación para ayudar a proteger los servidores y servicios de BizTalk Server contra los ataques de denegación de servicio. Tendrá que decidir si estas técnicas de mitigación son apropiadas para su entorno.  
  
-   **Utilice la propiedad de autenticación necesaria en el puerto de recepción.** De forma predeterminada, BizTalk envía todos los mensajes que recibe a la base de datos de cuadro de mensajes, aunque procedan de una entidad desconocida o sin resolver (Invitado). Para mitigar la posibilidad de que un atacante envíe un gran número de mensajes a BizTalk Server y sature (llene) la base de datos de cuadro de mensajes, puede usar el **requerida autenticación** propiedad en el puerto de recepción para recibir solo mensajes que procedan de entidades que BizTalk Server conozca. Puede elegir entre quitar los mensajes procedentes de una entidad desconocida o colocarlos en estado de suspensión. Para obtener más información sobre la **requerida autenticación** propiedad, vea [autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md). Además el **requerida autenticación** propiedad, considere el uso de un mecanismo externo, como el filtrado de puertos de firewall o bloqueo para protegerse frente a ataques por denegación de servicio de dirección IP.  
  
-   **Limitar el tamaño de los mensajes que BizTalk puede recibir.** Por ejemplo, al usar el adaptador de recepción de SOAP, puede evitar la recepción de tamaño de mensajes muy grandes estableciendo el atributo maxRequestLength el \<httpRuntime > elemento a un tamaño razonable. El \<httpRuntime > elemento está definido en el archivo Machine.config, que se encuentra en la \< *unidad*>:\\<*directorio de Windows* > \Microsoft.NET\Framework\vX.X.XXXXX\CONFIG directory. Para obtener más información acerca de \<httpRuntime > elemento, vea el sitio Web de Microsoft MSDN en [http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948).  
  
-   **Use listas DACL seguras para ubicaciones de recepción.** Se recomienda utilizar listas de control de acceso discrecional (DACL) seguras en las ubicaciones de descarga para las ubicaciones de recepción. Por ejemplo, utilice listas DACL seguras en el directorio en el que la ubicación de recepción de archivos recoge los mensajes, de modo que sólo los usuarios autorizados puedan descargar mensajes en esta ubicación.  
  
-   **Utilice IPSec.** Si no dispone de servidores de seguridad de hardware o software, utilice la seguridad del Protocolo de Internet (IPSec) para proteger los datos y los mensajes mientras BizTalk Server los transfiere de un servidor a otro. Para obtener más información acerca de IPSec, consulte Microsoft Download Center en [http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949).  
  
## <a name="see-also"></a>Vea también  
 [Identificar las posibles amenazas](../core/identifying-potential-threats.md)   
 [Planeación de la seguridad](../core/planning-for-security.md)