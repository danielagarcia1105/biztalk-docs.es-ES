---
title: Recomendaciones de seguridad del adaptador de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, security
- security, SOAP adapters
ms.assetid: f869bd82-df93-45e1-b747-b538820253fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f61b68ce0fd174dfbb766889e544c9b1005468d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985317"
---
# <a name="soap-adapter-security-recommendations"></a>Recomendaciones de seguridad del adaptador de SOAP
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el adaptador de SOAP para publicar (recibir) y consumir (enviar) servicios Web. Para obtener más información acerca del adaptador de SOAP, vea [adaptador de SOAP](../core/soap-adapter.md). Para obtener más información sobre los servicios Web, consulte [Using Web Services](../core/using-web-services.md). Se recomienda seguir estas directrices para proteger e implementar el adaptador de SOAP en su entorno.  
  
- Para obtener recomendaciones de seguridad para publicar servicios Web, consulte [habilitar los servicios Web](../core/enabling-web-services.md).  
  
- El adaptador de SOAP aprovecha el Protocolo de transferencia de hipertexto (HTTP) para enviar y recibir mensajes desde y hacia BizTalk Server. Por lo tanto, debe seguir las recomendaciones de seguridad para proteger los servicios de Internet Information Server (IIS). Si usa IIS 7.0, asegúrese de seguir las recomendaciones de IIS 7.0 para configurar el aislamiento de aplicaciones. Para obtener más información, consulte [crear un grupo de aplicaciones (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=196674).  
  
- Al crear un grupo de aplicaciones para una ubicación de recepción de SOAP, deberá configurarlo de modo que se ejecute en una cuenta que sea miembro del grupo de Windows del host aislado en que se ejecuta el adaptador de recepción SOAP, y miembro del grupo de proceso de trabajo de Servicios de Internet Information Server (IIS_WPG). A continuación, deberá configurar la instancia de host del adaptador de recepción SOAP para que utilice esta cuenta. Si cambia la cuenta para el grupo IIS_WPG, debe asegurarse de que también actualiza la instancia de host que se ejecute en la nueva cuenta.  
  
- Si se utilizan certificados de cliente de Capa de sockets seguros (SSL) con el adaptador de envío SOAP, los certificados deberán configurarse manualmente.  
  
- Al consumir servicios Web, puede utilizar certificados anónimos, básicos, implícitos, integrados de Windows o cliente para la autenticación. Al consumir servicios Web con autenticación básica, se recomienda utilizar SSL para asegurarse de que las personas no autorizadas no puedan leer las credenciales de usuario del mensaje.  
  
- Puede utilizar el inicio de sesión único (SSO) empresarial en aquellas situaciones en que tenga que asignar el contenido de un usuario cliente a las credenciales de un sistema de servidor. Para obtener más información, consulte [cómo credenciales de inicio de sesión único de mapa](../core/how-to-map-single-sign-on-credentials.md).  
  
- Cuando se usa la autenticación básica, o cuando no usa el cifrado en el nivel de mensaje, se recomienda usar SSL para la recepción y envío de mensajes para asegurarse de que una persona no autorizada no puede leer las credenciales de usuario.  
  
- Se recomienda utilizar la autenticación integrada de Windows para enviar y recibir mensajes.  
  
- El equipo que ejecuta el adaptador de SOAP también incluye el tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Se recomienda no ubicar el adaptador de SOAP en la red perimetral. De hacerlo, tendría que abrir puertos desde la red perimetral hasta el dominio de datos para el tráfico desde SQL Server hasta la base de datos de cuadro de mensaje. De este modo, el tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] quedaría expuesto a posibles ataques. Se recomienda configurar el adaptador de SOAP en el dominio de procesamiento (no en la red perimetral). Entonces podrá configurar el servidor de seguridad externo para que reenvíe las solicitudes de SOAP a través del servidor de seguridad del dominio de procesamiento. Este mecanismo recibe el nombre de proxy inverso. (La implementación del servidor Forefront Threat Management Gateway (TMG) 2010 se denomina Publicación en Web).  
  
## <a name="see-also"></a>Vea también  
 [Puertos para los servidores de envío y recepción](../core/ports-for-the-receive-and-send-servers.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)