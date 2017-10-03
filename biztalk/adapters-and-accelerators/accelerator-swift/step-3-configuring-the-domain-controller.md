---
title: 'Paso 3: Configurar el controlador de dominio | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, domain controller
- domain controller
ms.assetid: 1c513225-378b-4e57-ba29-7532b6cbcc9a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad3cdf84f5a392a8d5f836e78c57f782e14d0639
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configuring-the-domain-controller"></a>Paso 3: Configurar el controlador de dominio
Esta sección describe cómo configurar el controlador de dominio en su [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] implementación. En concreto, esta sección describe cómo instalar y configurar [!INCLUDE[btsAD](../../includes/btsad-md.md)] haciendo lo siguiente:  
  
-   Instalar Active Directory y DNS  
  
-   Crear las cuentas requeridas  
  
-   Unirse al dominio  
  
## <a name="installing-active-directory-and-dns"></a>Instalar Active Directory y DNS  
 Use la [!INCLUDE[btsAD](../../includes/btsad-md.md)] Asistente para la instalación para simplificar el proceso de configuración de un controlador de dominio. Después de instalar Active Directory, cree una zona de búsqueda inversa de sistema de nombres de dominio (DNS). A continuación, crear y agregar hosts a las zonas de búsqueda directa e inversa.  
  
## <a name="creating-the-required-accounts"></a>Crear las cuentas requeridas  
 En la tabla siguiente proporciona detalles sobre cómo crear los grupos de seguridad Global. Cree el siguiente **seguridad Global** grupos y usuarios en el controlador de dominio usando sus propias convenciones de nomenclatura. Los ejemplos proporcionados a continuación se utilizan para simplificar el trabajo. Agregar a los miembros especificados en la lista a los grupos creados.  
  
 Al crear grupos, seleccione **Global** para el ámbito de grupo y **seguridad** para el tipo de grupo.  
  
|Nombre de cuenta o grupo|Tipo|Description|Miembros|  
|---------------------------|----------|-----------------|-------------|  
|Administración|Usuario|Cuenta administrativa local para todos los equipos de BizTalk, el controlador de dominio y todos los equipos que ejecutan SQL Server.<br /><br /> Se trata de una cuenta de usuario de dominio que se utiliza para la instalación de aplicaciones ([!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]y SQL Server) y para configurar el Acelerador de BizTalk para A4SWIFT durante el tiempo de diseño. No es necesario tener privilegios de administrador de dominio para realizar la instalación de A4SWIFT. La cuenta de usuario administrador debe ser miembro del grupo usuarios del dominio, el grupo de administradores de BizTalk Server del dominio y grupo de administradores locales||  
|SQLSvc|Usuario|Cuenta para ejecutar el servicio SQL Server||  
|SSOSvc|Usuario|Cuenta para ejecutar el servicio de inicio de sesión único (SSO)||  
|HostSvc|Usuario|Cuenta para ejecutar el servicio de host de BizTalk||  
|IsolatedSvc|Usuario|Cuenta para ejecutar el servicio aislados de BizTalk||  
|BAMSvc|Usuario|Necesario para la configuración de BizTalk Server de BAMPortal, BAMAlerts y BAMTools||  
|BRESvc|Usuario|Cuenta para ejecutar el servicio del servicio de actualización de motor de reglas||  
|Administradores del dominio|Grupo de dominio|Cuenta de grupo de dominio global para los administradores de dominio||  
|Usuarios de hosts aislados de BizTalk|Grupo de dominio|Grupo global de dominio para las cuentas con acceso a los hosts aislados de BizTalk (procesos de host no se ejecuta en BizTalk Server, como HTTP y SOAP).|\<IsolatedSvc >, \<HostSvc >|  
|Administradores de servidor BizTalk Server|Grupo de dominio|Cuenta de grupo global de dominio que tenga los privilegios mínimos necesarios para realizar tareas administrativas incluidas en el Asistente de configuración del marco de trabajo y para administrar el servidor BizTalk Server.|\<Administración >|  
|Usuarios de aplicación de BizTalk|Grupo de dominio|Cuenta de grupo de dominio global para los usuarios de aplicación de BizTalk.|\<HostSvc >|  
|Operadores de servidor BizTalk Server|Grupo de dominio|El grupo que tiene los privilegios mínimos necesarios para realizar las tareas necesarias para utilizar el entorno de BizTalk Server después de la instalación.||  
|Hosts habilitados de SharePoint|Grupo de dominio|El grupo de Windows que tenga permisos para llamar a los servicios Web del adaptador de Windows SharePoint Services.|\<HostSvc >|  
|Administradores de SSO|Grupo de dominio|Cuenta de grupo de dominio global para los administradores SSO.|\<Administración >, \<SSOSvc >|  
|Administradores afiliados de SSO|Grupo de dominio|Los administradores afiliados de cuenta de grupo de dominio global de SSO|\<Administración >|  
|Usuarios de A4SWIFT|Grupo de dominio|Cuenta de grupo global de dominio que tenga los privilegios mínimos necesarios para realizar tareas básicas de A4SWIFT.|\<HostSvc > adicionales a los usuarios de red|  
|Administradores de A4SWIFT|Grupo de dominio|Cuenta de grupo global de dominio que tenga los privilegios mínimos necesarios para administrar A4SWIFT.|\<Administración >|  
  
> [!NOTE]
>  Todas las cuentas de grupo deben ser cuentas de seguridad global y cuentas de dominio no local. Si se utilizan las cuentas de grupo de dominio local (creadas mediante net localgroup), el programa de instalación para [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] no se puede validar específico [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] los usuarios del dominio.  
  
## <a name="joining-the-domain"></a>Unirse al dominio  
 Después de haber creado el dominio y los controladores de dominio ha reiniciado, unir cada servidor al dominio.