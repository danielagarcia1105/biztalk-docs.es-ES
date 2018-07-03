---
title: Recomendaciones de seguridad del adaptador de HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, HTTP adapters
- configuring [HTTP adapters], security
- HTTP adapters, security
ms.assetid: ef6043c2-c62a-40e5-b2e1-53e60f87a761
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb4ad155eed3788a76bdf8cdd342750f45dfe72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992750"
---
# <a name="http-adapter-security-recommendations"></a>Recomendaciones de seguridad del adaptador de HTTP
El adaptador de HTTP se usa para intercambiar información entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y una aplicación por medio del Protocolo de transferencia de hipertexto (HTTP). Las aplicaciones pueden enviar mensajes a un servidor mediante el envío de solicitudes HTTP POST o HTTP GET a una dirección URL de HTTP concreta. Para obtener más información acerca del adaptador de HTTP, consulte [adaptador de HTTP](../core/http-adapter.md). Se recomienda seguir estas directrices para proteger e implementar el adaptador de HTTP en su entorno:  
  
- Asegúrese de configurar los parámetros de Servicios de Internet Information Server (IIS) para el adaptador de HTTP. Para obtener más información, consulte [cómo configurar IIS para una ubicación de recepción HTTP](../core/how-to-configure-iis-for-an-http-receive-location.md).  
  
- Si usa la versión 7.0, asegúrese de seguir las recomendaciones de IIS 7.0 para configurar el aislamiento de aplicaciones.  
  
- Cuando se utiliza la autenticación básica, o cuando no se utiliza ningún cifrado en el nivel de mensajes, es recomendable utilizar la Capa de sockets seguros (SSL) para el envío y la recepción de mensajes para asegurarse de que las personas no autorizadas no puedan detectar las credenciales de usuario.  
  
- Se recomienda utilizar la autenticación integrada de Windows para enviar y recibir mensajes.  
  
- Se recomienda no copiar, mover ni cambiar el nombre del archivo de extensión ISAPI. De este modo, se garantiza que los programas de instalación de actualizaciones de seguridad puedan aplicar correctamente las actualizaciones de seguridad necesarias para el archivo.  
  
- Debe utilizar listas seguras de control de acceso discrecional (DACL) en el directorio que contenga el archivo de extensión ISAPI, así como en el directorio virtual que haya creado para la recepción de mensajes. Los miembros del grupo Usuarios de hosts aislados de BizTalk del host en que se ejecuta el adaptador de HTTP necesitan permisos de lectura y ejecución, y los usuarios que requieren autenticación por parte del adaptador de HTTP necesitan permisos de lectura en estos directorios.  
  
- Cuando se utilicen certificados de cliente SSL con el adaptador de envío HTTP, se deberá configurar manualmente estos certificados.  
  
- Como sucede con el resto de componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se recomienda no colocar el adaptador de HTTP en la red perimetral. De hacerlo, tendría que abrir puertos desde la red perimetral hasta el dominio de datos para el tráfico desde SQL Server hasta la base de datos de cuadro de mensajes, lo que entrañaría algunos riesgos. Se recomienda configurar el adaptador de HTTP en el dominio de procesamiento (no en la red perimetral). Entonces podrá configurar el servidor de seguridad externo (FW4) para que reenvíe las solicitudes de HTTP a través del servidor de seguridad del dominio de procesamiento (FW3). En este caso, no necesitará IIS en la red perimetral. Este mecanismo recibe el nombre de proxy inverso. (La implementación del servidor Forefront Threat Management Gateway (TMG) 2010 se denomina Publicación en Web).  
  
- Al crear un grupo de aplicaciones para una ubicación de recepción de HTTP, deberá configurarlo de modo que se ejecute en una cuenta que sea miembro del grupo de Windows del host aislado que ejecute el adaptador de recepción HTTP, y del grupo de procesos de trabajo de Servicios de Internet Information Server (IIS_WPG). A continuación, deberá usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar la instancia de host, de modo que el adaptador de recepción HTTP use esta cuenta. Si cambia la cuenta para el grupo IIS_WPG, debe asegurarse de que también actualiza la instancia de host que se ejecute en la nueva cuenta. Para obtener más información, consulte [cómo configurar IIS para una ubicación de recepción HTTP](../core/how-to-configure-iis-for-an-http-receive-location.md).  
  
## <a name="see-also"></a>Vea también  
 [Puertos para los servidores de envío y recepción](../core/ports-for-the-receive-and-send-servers.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)