---
title: Solución de problemas de Internet Information Services | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f77084f1-5797-42ab-bbf6-fe815144232e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7ca928aa2e47b5c62548aba02834b96d6a3baf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006661"
---
# <a name="troubleshooting-internet-information-services"></a>Solución de problemas de Internet Information Services
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa mucho Microsoft Internet Information Services (IIS) para diversas funcionalidades, incluidos los adaptadores de HTTP, SOAP y Windows SharePoint Services. En esta tema se explican algunos problemas conocidos que se puede encontrar en IIS y las posibles soluciones a estos problemas.  
  
## <a name="known-issues"></a>Problemas conocidos  
 Es posible que los errores incluidos en este tema no se muestren a menos que configure Internet Explorer para que deshabilite los mensajes de error descriptivos de HTTP.  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a>Para configurar Internet Explorer de modo que deshabilite los mensajes de error descriptivos de HTTP  
  
1.  En el **herramientas** menú, haga clic en **opciones de Internet**.  
  
2.  En el **avanzadas** ficha la **exploración** sección, desactive la **mostrar mensajes de error HTTP descriptivos** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
3.  Cierre Internet Explorer.  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>Al obtener acceso a una página web en un servidor IIS, se produce el error “HTTP 404 – Archivo no encontrado”  
  
##### <a name="problem"></a>Problema  
 Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:  
  
 No se encontró la página  
  
 \- O bien  
  
 HTTP 404 – Archivo no encontrado  
  
##### <a name="cause"></a>Causa  
 Este error puede producirse por los siguientes motivos:  
  
-   Se ha cambiado el nombre del servicio solicitado.  
  
-   El archivo solicitado se ha movido a otra ubicación o se ha eliminado.  
  
-   El archivo solicitado no está disponible temporalmente debido a mantenimiento, actualizaciones u otros motivos desconocidos.  
  
-   El archivo solicitado no existe.  
  
-   IIS 6.0: el tipo MIME o la extensión de servicio Web adecuada no están habilitados.  
  
-   Un directorio virtual se asigna a la raíz de una unidad en otro servidor.  
  
##### <a name="resolution"></a>Solución  
 Siga los pasos descritos en la sección de solución de Microsoft Knowledge Base artículo 248033, "razones comunes por IIS Server devuelve el error"HTTP 404 – archivo no encontrado"" disponible en [ http://support.microsoft.com/kb/248033 ](http://support.microsoft.com/kb/248033).  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>Al obtener acceso a una página web en un servidor IIS, se produce el error “No se pudo encontrar el servidor o error DNS”  
  
##### <a name="problem"></a>Problema  
 Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:  
  
 No se puede mostrar la página  
  
 \- O bien  
  
 No se pudo encontrar el servidor o error DNS  
  
##### <a name="cause"></a>Causa  
 Este error puede producirse por los siguientes motivos:  
  
-   Su configuración de conexión de Internet Explorer es incorrecta.  
  
-   Se ha instalado software de servidor de seguridad o proxy incompatible, configurado de forma incorrecta o con funcionamiento incorrecto.  
  
-   Hay una entrada incorrecta en un archivo de hosts.  
  
-   Su adaptador de red no está funcionando correctamente o tiene instalados controladores de adaptador de red incompatibles.  
  
##### <a name="resolution"></a>Solución  
 Siga los pasos descritos en la sección resolución de artículo de Microsoft Knowledge Base 326155, "mensaje de Error al intentar obtener acceso a un sitio Web en Internet Explorer:"No se puede mostrar la página"" disponible en [ http://support.microsoft.com/kb/326155 ](http://support.microsoft.com/kb/326155).  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>Al obtener acceso a una página Web en un servidor IIS, se produce el error “401 – Acceso denegado”  
  
##### <a name="problem"></a>Problema  
 Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:  
  
 401 – Acceso denegado  
  
##### <a name="cause"></a>Causa  
 IIS define varios errores 401 diferentes que indican una causa más específica del error. Estos códigos de error específicos se muestran en el explorador:  
  
- 401.1 – Error en el inicio de sesión.  
  
- 401.2 – Error en el inicio de sesión debido a la configuración del servidor.  
  
- 401.3 – No autorizado debido a ACL en el recurso.  
  
- 401.4 – No autorizado: error de autorización debido a un filtro instalado en el servidor web.  
  
- 401.5 – Error de autorización debido a una aplicación ISAP o CGI.  
  
- 401.7 – Acceso denegado por directiva de autorización de URL en el servidor web. Este código de error es específico de IIS 6.0.  
  
  Para obtener una lista completa de los códigos de estado de IIS 7.0, vea el artículo 943891, de Microsoft Knowledge Base "Los códigos de estado HTTP en IIS 7.0" disponible en [ http://support.microsoft.com/kb/943891 ](http://support.microsoft.com/kb/943891).  
  
##### <a name="resolution"></a>Solución  
 Siga los pasos de [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md) para resolver los problemas de permisos de IIS.  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>Al obtener acceso a una página web en un servidor IIS, se produce el error “ 500 – Error interno del servidor”  
  
##### <a name="problem"></a>Problema  
 Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:  
  
 500 – Error interno del servidor  
  
##### <a name="cause"></a>Causa  
 Este mensaje de error lo pueden provocar una amplia gama de problemas del servidor.  
  
##### <a name="resolution"></a>Solución  
 Para solucionar el problema, haga lo siguiente:  
  
- Revise el registro de la aplicación del servidor IIS para obtener información acerca de la causa del error.  
  
- Revise los archivos de registro de IIS o de HTTPERR para obtener información que pueda ser útil a la hora de determinar la causa del error. De forma predeterminada, los archivos de registro de IIS se encuentran en el siguiente directorio de un equipo con el sistema operativo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]:  
  
   <em>% WinDir %\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.  
  
   De forma predeterminada, en un equipo con Windows Server 2008 o Windows Vista, los archivos de registro de IIS se encuentran en el siguiente directorio:  
  
   C:\inetpub\logs\LogFiles\W3SVC1\  
  
   De forma predeterminada, en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de HTTPERR se encuentran en el siguiente directorio:  
  
   <em>% WinDir %</em>system32LogFilesHTTPERR  
  
  > [!NOTE]
  >  El archivo de registro de HTTPERR solo se encuentra disponible en un equipo con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o Windows Vista.  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>Al obtener acceso a una página web en un servidor IIS, se produce el error “Servicio no disponible”  
  
##### <a name="problem"></a>Problema  
 Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:  
  
 Servicio no disponible  
  
##### <a name="cause"></a>Causa  
 La causa más común de este error es que el grupo de aplicaciones (IIS 6.0 e IIS 7.0) para la página web se ha detenido. Esto suele ocurrir si el grupo de aplicaciones o la aplicación COM+ están configurados con una identidad para la que el nombre de usuario y la contraseña especificados no son válidos.  
  
##### <a name="resolution"></a>Solución  
 Siga los pasos descritos en la sección "Identidad de proceso de Host de configuración IIS aplicación" del tema [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md) para establecer la identidad del proceso de host correspondiente.  
  
## <a name="see-also"></a>Vea también  
 [Directrices para solucionar problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md)