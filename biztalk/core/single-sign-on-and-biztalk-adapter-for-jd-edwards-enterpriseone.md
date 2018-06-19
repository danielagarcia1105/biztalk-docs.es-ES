---
title: Un único inicio de sesión y el adaptador de BizTalk para JD Edwards EnterpriseOne | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8daa94a49be4d120180fca9fb82c07b3603cf95
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015819"
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a>Inicio de sesión único y adaptador de BizTalk para JD Edwards EnterpriseOne
Si usa el inicio de sesión único (SSO) con el adaptador de Microsoft para JD Edwards EnterpriseOne, el adaptador obtiene las credenciales de la base de datos de credenciales de SSO. Por lo tanto, no es necesario que especifique las credenciales de inicio de sesión para el sistema de servidor en el **propiedades de transporte** cuadro de diálogo.  
  
 En tiempo de ejecución, el adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Ese usuario debe ser un usuario de la aplicación. En tiempo de ejecución, use el adaptador de recepción HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como una ubicación de recepción en escenarios de paso a través al usar SSO.  
  
## <a name="processing-requests"></a>Procesamiento de solicitudes  
 Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario. La extensión ISAPI suplanta al usuario de Windows y llama al almacén de credenciales SSO para obtener un vale cifrado. Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.  
  
 El mensaje se dirige entonces a la base de datos de cuadro de mensajes. Cuando el adaptador de BizTalk para JD Edwards EnterpriseOne recibe el mensaje de la base de datos Cuadro de mensaje, llama al método `ValidateAndRedeemTicket`, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión. Entonces, el adaptador usa las credenciales externas para conectarse al sistema y procesar la solicitud.  
  
> [!NOTE]
>  La configuración de SSO forma parte de la configuración de BizTalk Server. Si obtiene errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial. SSO sólo funciona con una cuenta de dominio.  
  
## <a name="see-also"></a>Vea también  
 [Creación de aplicaciones afiliadas](../core/creating-affiliate-applications4.md)   
 [Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)