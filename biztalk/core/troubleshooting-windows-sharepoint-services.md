---
title: Solucionar problemas de Windows SharePoint Services | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9acf9a0d-2c92-4227-80f8-b2d0cca0c232
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51243216f2adb73454477252c7b54358df229610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-windows-sharepoint-services"></a>Solucionar problemas de Windows Sharepoint Services
El adaptador Windows SharePoint Services usa Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. En este tema se explican algunos problemas conocidos que se pueden encontrar con Windows SharePoint Services y las posibles soluciones a estos problemas.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a>Se produce un error de inicio de sesión del usuario 'NT AUTHORITY\NETWORK SERVICE' al intentar crear una base de datos de contenido  
  
##### <a name="problem"></a>Problema  
 Cuando se intenta crear una base de datos de contenido mediante el sitio Web de Administración central de SharePoint, se muestra un error similar al siguiente:  
  
 Error de inicio de sesión del usuario 'NT AUTHORITY\NETWORK SERVICE'  
  
##### <a name="cause"></a>Causa  
 Este problema se produce cuando el propietario de la base de datos a la que se está conectando no coincide con la identidad del grupo de aplicaciones en la que se está ejecutando Windows SharePoint Services.  
  
##### <a name="resolution"></a>Solución  
 Para resolver este problema, realice una de las siguientes opciones:  
  
-   Conceder a la cuenta de servicio de red derechos de creación de bases de datos en SQL Server.  
  
-   Cambiar la cuenta de la identidad del grupo de aplicaciones por una cuenta que tenga derechos de creación de bases de datos en SQL Server.  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a>Se produce un error de tipo "Servicio no disponible" al obtener acceso al sitio Web de Administración central de SharePoint  
  
##### <a name="problem"></a>Problema  
 Cuando se intenta abrir el sitio Web de Administración central de SharePoint, se muestra un error similar al siguiente:  
  
 Servicio no disponible  
  
##### <a name="cause"></a>Causa  
 La causa más frecuente de este error es que se detiene el grupo de aplicaciones (IIS 6.0 o IIS 7.0) o la aplicación COM+ (IIS 5.x) de hospedaje del sitio web de Administración central de SharePoint. Esto suele ocurrir si el grupo de aplicaciones o la aplicación COM+ está configurada con una identidad para la que la contraseña o el nombre de usuario especificado no es válido.  
  
##### <a name="resolution"></a>Solución  
 Siga los pasos descritos en la sección "Identidad de proceso de Host de configuración IIS aplicación" del tema [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md) para establecer la identidad del proceso de host correspondiente.  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a>Se produce un error de tipo "No se puede conectar a la base de datos de configuración" al intentar expandir y crear una base de datos de contenido  
  
##### <a name="problem"></a>Problema  
 Cuando se intenta expandir y crear una base de datos de contenido mediante el sitio Web de Administración central de SharePoint, se muestra un error similar al siguiente:  
  
 No se puede conectar a la base de datos de configuración  
  
##### <a name="cause"></a>Causa  
 Este problema se produce cuando la cuenta que usa el grupo de aplicaciones que está ejecutando el sitio Web de Administración central de SharePoint no tiene los permisos necesarios para la base de datos de SQL Server.  
  
##### <a name="resolution"></a>Solución  
 Para resolver este problema, realice una de las siguientes opciones:  
  
-   Conceder a la cuenta que usa el grupo de aplicaciones para el sitio Web de Administración central de SharePoint derechos de creación de bases de datos en SQL Server.  
  
-   Cambiar la cuenta de la identidad del grupo de aplicaciones por una cuenta que tenga derechos de creación de bases de datos en SQL Server.  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a>En el registro de aplicaciones se produce el error "No se pudo iniciar el servicio Temporizador de extensiones de SharePoint" tras reiniciar el servidor  
  
##### <a name="problem"></a>Problema  
 Tras reiniciar el servidor, aparece el siguiente error en los registros de eventos:  
  
 No se pudo iniciar el servicio Temporizador de extensiones de SharePoint  
  
 Es posible que aparezca también el error siguiente cuando se abra el sitio Web de Administración central de SharePoint:  
  
 No se puede establecer conexión con la base de datos de configuración de WSS STS_Config  
  
##### <a name="cause"></a>Causa  
 Este error se produce cuando el servicio Temporizador de extensiones de SharePoint no puede establecer conexión con la base de datos de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] después de reiniciar. El servicio Temporizador de extensiones de SharePoint se usa para enviar notificaciones y realizar las tareas programadas de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. La razón más común de que el servicio Temporizador de extensiones de SharePoint no se pueda iniciar es que la cuenta que se usa para ejecutar el servicio está configurada con una identidad para la que el nombre de usuario o la contraseña ya no es válido.  
  
##### <a name="resolution"></a>Solución  
 Asegúrese de que el nombre de usuario y la contraseña especificados para la cuenta de inicio de sesión del servicio Temporizador de extensiones de SharePoint sean correctos y de que se haya iniciado el servicio.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar un servidor virtual de Windows SharePoint Services](http://support.microsoft.com/kb/832769)   
 [Cómo realizar copias de y restaurar las instalaciones de Windows SharePoint Services que usan Microsoft SQL Server 2000 Desktop Engine (Windows)](http://support.microsoft.com/kb/833797)   
 [Recibirá un mensaje de error "No se puede conectar a la base de datos de configuración" cuando se conecta a su sitio Web de Windows SharePoint Services](http://support.microsoft.com/kb/823287)   
 [Recibirá un mensaje de Error "Servicio no disponible" al examinar un sitio Web de Windows SharePoint Services](http://support.microsoft.com/kb/823552)   
 [Recibirá un mensaje de error "Database < nombreDeBaseDeDatos > ya existe" cuando se administra la base de datos de contenido de Windows SharePoint Services](http://support.microsoft.com/kb/828815)