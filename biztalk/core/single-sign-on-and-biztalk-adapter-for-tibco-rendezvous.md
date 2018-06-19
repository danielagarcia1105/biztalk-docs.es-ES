---
title: Un único inicio de sesión y el adaptador de BizTalk para TIBCO Rendezvous | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52e698bb-38ba-4a12-b15a-d1581061d62f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 310a3448acd8bd70e617a9a5af650b55a12c9007
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013448"
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-rendezvous"></a>Inicio de sesión único y adaptador de BizTalk para TIBCO Rendezvous

## <a name="overview"></a>Información general
Cuando se usa inicio de sesión único (SSO) con Microsoft BizTalk Adapter para TIBCO Rendezvous, el adaptador obtiene las credenciales de la base de datos de credenciales de SSO; por lo tanto, no es necesario que especifique las credenciales de inicio de sesión para el sistema de servidor en el **propiedades de transporte** ventana.  
  
 En tiempo de diseño, el adaptador obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de BizTalk Server. Ese usuario debe ser un usuario de la aplicación. En tiempo de ejecución, use el adaptador de recepción HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como ubicación de recepción en escenarios de paso a través al usar SSO.  
  
## <a name="processing-requests"></a>Procesamiento de solicitudes  
 Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario. La extensión ISAPI suplanta al usuario de Windows y llama al almacén de credenciales SSO para obtener un vale cifrado. Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.  
  
 El mensaje se dirige entonces a la base de datos de cuadro de mensajes. Cuando el adaptador de BizTalk para TIBCO Rendezvous recibe el mensaje de la base de datos de cuadro de mensajes, llama al método `ValidateAndRedeemTicket`, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión. Entonces, el adaptador usa las credenciales externas para conectarse al sistema y procesar la solicitud.  
  
> [!NOTE]
>  La configuración de SSO forma parte de la configuración de BizTalk Server. Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial. SSO sólo funciona con una cuenta de dominio.  
  
## <a name="see-also"></a>Vea también  
 [Creación de aplicaciones afiliadas](../core/creating-affiliate-applications1.md)   
[Seguridad](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)