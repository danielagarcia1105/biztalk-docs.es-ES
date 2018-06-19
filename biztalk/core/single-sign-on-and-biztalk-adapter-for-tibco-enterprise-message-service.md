---
title: SSO y BizTalk Adapter para TIBCO Enterprise Message Service | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68e85ceb-bf4c-489a-a2c2-1558e718ceed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 577fa596fadee68c94dfa510de101d01b0ab06e4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013419"
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service"></a>Inicio de sesión único y adaptador de TIBCO Enterprise Message Service

## <a name="overview"></a>Información general
Al usar inicio de sesión único (SSO) con Microsoft BizTalk Adapter para TIBCO Enterprise Message Service (EMS), el adaptador obtiene las credenciales de la base de datos de credenciales de SSO; por lo tanto, no es necesario que especifique las credenciales de inicio de sesión para el sistema de servidor en el **propiedades de transporte** cuadro de diálogo.  
  
 En tiempo de diseño, el adaptador obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de BizTalk Server. Ese usuario debe ser un usuario de la aplicación. En tiempo de ejecución, use el adaptador de recepción HTTP de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como ubicación de recepción en escenarios de paso a través al usar SSO.  
  
## <a name="processing-requests"></a>Procesamiento de solicitudes  
 Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario. La extensión ISAPI suplanta al usuario de Windows y llama al almacén de credenciales SSO para obtener un vale cifrado. Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.  
  
 El mensaje se dirige entonces a la base de datos de cuadro de mensajes. Cuando el adaptador de BizTalk para TIBCO EMS recibe el mensaje de la base de datos de cuadro de mensajes, llama al método ValidateAndRedeemTicket, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión. Entonces, el adaptador usa las credenciales externas para conectarse al sistema y procesar la solicitud.  
  
> [!NOTE]
>  La configuración de SSO forma parte de la configuración de BizTalk Server. Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial. SSO sólo funciona con una cuenta de dominio.  
  
## <a name="see-also"></a>Vea también  
 [Creación de aplicaciones afiliadas](../core/creating-affiliate-applications5.md)   
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-tibco-ems.md)