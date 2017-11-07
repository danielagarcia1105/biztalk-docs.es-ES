---
title: "Un único inicio de sesión y el adaptador de BizTalk para JD Enterprise OneWorld | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b0fbe7aa671d543a0fd6cd7da78e05d18c63c3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a>Inicio de sesión único y adaptador de BizTalk para JD Enterprise OneWorld
Se obtienen las credenciales de inicio de sesión (SSO) único de la base de datos de credenciales SSO; por lo tanto, no es necesario que escriba las credenciales de inicio de sesión del sistema del servidor en el **propiedades de transporte** ventana.  
  
 En tiempo de ejecución, el adaptador de Microsoft BizTalk para JD Edwards OneWorld obtiene las credenciales para el sistema (para la aplicación afiliada especificada) en el contexto del usuario que inició el proyecto de BizTalk Server. Ese usuario debe ser un usuario de la aplicación.  
  
 En tiempo de ejecución, use el adaptador de BizTalk para JD Edwards OneWorld como una ubicación de recepción en escenarios de paso a través al usar SSO.  
  
 Cuando los Servicios de Internet Information Server (IIS) reciben una solicitud HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario. La extensión ISAPI suplanta al usuario de Windows y llama al almacén de credenciales SSO para obtener un vale cifrado. Este vale se almacena como propiedad SSOTicket en el contexto del mensaje.  
  
 El mensaje se dirige entonces a la base de datos de cuadro de mensajes. Cuando el adaptador recibe el mensaje de la base de datos de cuadro de mensajes, llama al método IBTSTicket.ValidateAndRedeemTicket, con el vale cifrado y el nombre de la aplicación afiliada, a fin de recuperar del almacén de SSO las credenciales de inicio de sesión. Seguidamente, el adaptador de BizTalk para JD Edwards OneWorld utiliza las credenciales externas para conectarse al sistema de servidor y procesar la solicitud.  
  
> [!NOTE]
>  La configuración de SSO forma parte de la configuración de BizTalk Server. Si recibe errores de SSO, compruebe que ha utilizado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial. SSO sólo funciona con una cuenta de dominio.  
  
## <a name="see-also"></a>Vea también  
 [Creación de aplicaciones afiliadas](../core/creating-affiliate-applications3.md)   
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)