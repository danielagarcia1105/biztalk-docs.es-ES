---
title: Grupos de Windows y cuentas de usuario en BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, BTS_ADMIN_USERS role [SQL Server database]
- MessageBox database, BTS_HOST_USERS role [SQL Server database]
- Rule Engine database, BTS_HOST_USERS role [SQL Server database]
- Management database, BTS_OPERATORS role [SQL Server database]
- BTS_HOST_USERS role [SQL Server database]
- NSSubscriberAdmin role [SQL Server database]
- Management database, tpm_user role [SQL Server database]
- SSO, securityadmin role [SQL Server database]
- IIS_WPG group
- BAM Notification service account
- EDI_ADMIN_USERS role [SQL Server database]
- Archive database [BAM], db_owner role [SQL Server database]
- Primary Import database [BAM], db_owner role [SQL Server database]
- Primary Import database [BAM], BAM_EVENT_WRITER role [SQL Server database]
- Notification Services Application database [BAM], db_owner role [SQL Server database]
- NSRunService role [SQL Server database]
- RE_HOST_USERS role [SQL Server database]
- MessageBox database, BTS_OPERATORS role [SQL Server database]
- Rule Engine database, RE_HOST_USERS role [SQL Server database]
- Windows groups, creating
- securityadmin role [SQL Server database]
- BizTalk Isolated Host Instance service account
- In-Process BizTalk Host groups
- Primary Import database [BAM], BTS_ADMIN_USERS role [SQL Server database]
- SSO Affiliate Administrators [Windows group]
- Star Schema database [BAM], db_owner role [SQL Server database]
- Notification Services Instance database [BAM], db_owner role [SQL Server database]
- MessageBox database, BTS_ADMIN_USERS role [SQL Server database]
- Rule Engine Update Service account
- Configuration Manager, creating user accounts
- SSO Administrators [Windows group]
- Rule Engine database, BTS_ADMIN_USERS role [SQL Server database]
- Tracking database, BTS_OPERATORS role [SQL Server database]
- Primary Import database [BAM], BAM_ManagementNSReader role [SQL Server database]
- Notification Services Instance database [BAM], role [SQL Server database]
- BizTalk Application Users [Windows group]
- user accounts, creating
- Rule Engine database, BTS_OPERATORS role [SQL Server database]
- STS_WPG group
- BAM_ManagementWS role [SQL Server database]
- BTS_OPERATORS role [SQL Server database]
- Tracking database, BTS_HOST_USERS role [SQL Server database]
- SSO, db_owner role [SQL Server database]
- Notification Services Application database [BAM], role [SQL Server database]
- OLAP Administrators
- BAM_EVENT_WRITER role [SQL Server database]
- Windows groups, group list
- tpm_user role [SQL Server database]
- BizTalk Host Instance service account
- Base DBI database, EDI_ADMIN_USERS role [SQL Server database]
- Primary Import database [BAM], role [SQL Server database]
- BizTalk SharePoint Adapter Enabled Hosts [Windows group]
- BAM Management Web service account
- db_owner role [SQL Server database]
- Management database, BTS_ADMIN_USERS role [SQL Server database]
- Configuration Manager, creating groups
- Management database, BTS_HOST_USERS role [SQL Server database]
- BizTalk Server Operators [Windows group]
- Base DBI database, BTS_OPERATORS role [SQL Server database]
- Enterprise Single Sign-On Service account
- NSAdmin role [SQL Server database]
- BAM_ManagementNSReader role [SQL Server database]
- Notification Services Application database [BAM], NSRunService role [SQL Server database]
- BTS_ADMIN_USERS role [SQL Server database]
- BizTalk Isolated Host Users [Windows group]
- Notification Services Instance database [BAM], NSAdmin role [SQL Server database]
- SQLServer2005NotificationServicesUser
- EDI Subsystem Users [Windows group]
- Primary Import database [BAM], BTS_HOST_USERS role [SQL Server database]
- BizTalk Server Administrators [Windows group]
- BAM Portal Users [Windows group]
- Notification Services Application database [BAM], NSAdmin role [SQL Server database]
ms.assetid: a01603bd-4105-4691-819d-de43b00b40f3
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f229c950c3f49eca80810e9702ce021f0e8579
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="windows-groups-and-user-accounts-in-biztalk-server"></a>Cuentas de grupos y de usuario de Windows en BizTalk Server
Información sobre las cuentas de usuario y grupo de locales y de dominio de BizTalk Server. El Administrador de configuración crea las cuentas de grupo de BizTalk necesarias de forma predeterminada si se instala BizTalk Server con todo el software necesario en un solo equipo. La información de esta sección se aplica a topologías de varios equipos.  
  
> [!IMPORTANT]
>  BizTalk Server admite cuentas locales de grupo y de usuario sólo en configuraciones de un solo equipo. BizTalk Server admite cuentas de grupo de dominio y de usuario en configuraciones de uno y de varios equipos. Si utiliza grupos de dominio para la configuración de BizTalk Server, debe crear los grupos manualmente antes de configurar BizTalk Server. El Administrador de configuración no puede crear grupos de dominio.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-create-windows-group-and-user-accounts-in-biztalk-server"></a>Para crear cuentas de grupo y de usuario de Windows en BizTalk Server  
  
1.  Con Active Directory, desde el **iniciar** menú, elija **programas**, seleccione **herramientas administrativas**y seleccione **usuarios de Active Directory y Equipos**.  
  
2.  En la ventana usuarios y equipos de usuarios de Active Directory, haga clic en la parte inferior del panel derecho, o haga clic en el **usuarios** carpeta en el árbol de navegación en el panel izquierdo.  
  
3.  Seleccione **New**, a continuación, seleccione **grupo** o **usuario**.  
  
4.  Escriba la información de grupo o de usuario indicada en la tabla siguiente.  
  
 En la tabla siguiente se enumeran los grupos de Windows usados por BizTalk Server, junto con sus pertenencias. También se identifican las funciones de servidor SQL Server o de base de datos de cada grupo.  
  
|Grupo|Descripción del grupo|Pertenencia|Funciones de servidor SQL Server o de base de datos|  
|-----------|-----------------------|----------------|----------------------------------------|  
|Administradores de SSO|Administrador del servicio de inicio de sesión único (SSO) empresarial.|Contiene cuentas de servicio para el servicio de inicio de sesión único empresarial.<br /><br /> Contiene usuarios o grupos que necesitan tener la capacidad de configurar y administrar BizTalk Server y el servicio de SSO.<br /><br /> Contiene cuentas utilizadas para ejecutar el Administrador de configuración de BizTalk al configurar el servidor secreto principal de SSO.|Función de base de datos de servidor SQL Server db_owner para el SSO<br /><br /> Función de servidor SQL Server securityadmin para el servidor SQL Server en que se encuentra SSO|  
|Administradores afiliados de SSO|Administradores de ciertas aplicaciones afiliadas de SSO.<br /><br /> Puede crear o eliminar aplicaciones afiliadas de SSO, administrar asignaciones de usuarios y definir credenciales para usuarios de aplicaciones afiliadas|No contiene ninguna cuenta de servicio.<br /><br /> Contiene una cuenta utilizada para los Administradores de BizTalk Server.||  
|Administradores de servidor BizTalk Server|Tiene los privilegios mínimos necesarios para realizar tareas administrativas<br /><br /> Puede implementar soluciones, administrar aplicaciones y resolver problemas de procesamiento de mensajes.<br /><br /> Para poder realizar tareas administrativas para los adaptadores, recibir y enviar controladores y recibir ubicaciones, los Administradores de BizTalk Server deben agregarse a los Administradores afiliados de inicio de sesión único.<br /><br /> Para obtener más información, consulte [administrar la seguridad de BizTalk Server](../core/managing-biztalk-server-security.md).|Contiene usuarios o grupos que necesitan poder configurar y administrar BizTalk Server.|Función de base de datos de servidor SQL Server BTS_ADMIN_USERS en las siguientes bases de datos:<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> Función de base de datos de servidor SQL Server db_owner para las siguientes bases de datos:<br /><br /> BAMStarSchema<br /><br /> BAMPrimaryImport<br /><br /> BAMArchive<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> Rol de base de datos de servidor SQL Server NSAdmin en las siguientes bases de datos:<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> Administradores de OLAP en el equipo que hospeda la base de datos de OLAP BAMAnalysis.|  
|Operadores de servidor BizTalk Server|Tiene una función de pocos privilegios, con acceso sólo para supervisar y solucionar problemas de acciones<br /><br /> Para obtener más información, vea [administrar la seguridad de BizTalk Server](../core/managing-biztalk-server-security.md)|Contiene usuarios o grupos que supervisarán soluciones.<br /><br /> No contiene ninguna cuenta de servicio.|Rol de base de datos de SQL Server BTS_OPERATORS en las siguientes bases de datos:<br /><br /> BizTalkDTADb<br /><br /> BizTalkEDIDb<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb|  
|Usuarios de aplicación de BizTalk|El nombre predeterminado del primer grupo de host de BizTalk de tipo En curso creado por el administrador de configuración.<br /><br /> Use un Grupo de host de BizTalk por cada host de tipo En curso de su entorno.<br /><br /> Incluye cuentas con acceso a hosts In-Process de BizTalk (procesos de host en BizTalk Server, BTSNTSvc.exe).|Contiene cuentas de servicio para la instancia de host In-Process de BizTalk en el host para el que se ha designado el grupo de host de BizTalk.|Rol de base de datos de SQL Server BTS_HOST_USERS en las siguientes bases de datos:<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> Función de base de datos de servidor SQL Server de BAM_EVENT_WRITER en el BAMPrimaryImport|  
|Usuarios de hosts aislados de BizTalk|El nombre predeterminado del primer Grupo de host de BizTalk aislado creado por el Administrador de configuración. Hosts de BizTalk aislados que no se ejecutan en BizTalk Server, como HTTP y SOAP.<br /><br /> Utilice un grupo de host aislado de BizTalk por cada host aislado de su entorno.|Contiene cuentas de servicio para la instancia de host de BizTalk aislado en el host para el que se ha designado el grupo de host aislado de BizTalk.|Rol de base de datos de SQL Server BTS_HOST_USERS en las siguientes bases de datos:<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport|  
|Usuarios del portal de SAE|Tiene acceso al sitio web del portal de BAM.|Para esta función se usa el grupo Todos de forma predeterminada.<br /><br /> No contiene ninguna cuenta de servicio.||  
|Hosts habilitados del adaptador de SharePoint de BizTalk|Tiene acceso al servicio Web de Adaptador de Windows SharePoint Services|Contiene cuentas de servicio para que la instancia de host de BizTalk pueda llamar al adaptador de SharePoint.||  
|Grupo de operadores de BizTalk B2B|Rol nuevo de BizTalk que reduce la responsabilidad de los administradores para realizar las operaciones de administración de entidades. Este rol permite a los usuarios de Windows asociados al rol llevar a cabo todas las operaciones de administración de entidades.|Contiene usuarios y grupos que deben poder configurar y administrar datos de TPM de BizTalk Server, así como de supervisar las soluciones.|Rol de base de datos de SQL Server BTS_OPERATORS en las siguientes bases de datos: BizTalkDTADb, BizTalkMgmtDb, BizTalkMsgBoxDb, BizTalkRuleEngineDb y BAMPrimaryImport|  
  
 En la tabla siguiente se enumeran las afiliaciones de grupo y las cuentas de servicio o de usuario de Windows usadas por BizTalk Server. También se identifican las funciones de servidor SQL Server o de base de datos para las cuentas.  
  
|Usuario|Descripción del usuario|Afiliación de grupo|Funciones de servidor SQL Server o de base de datos|  
|----------|----------------------|-----------------------|----------------------------------------|  
|Servicio de inicio de sesión único (SSO) empresarial|Cuenta de servicio usada para ejecutar el servicio de inicio de sesión único empresarial que tiene acceso a la base de datos de SSO.|Administradores de SSO||  
|Cuenta de instancias de host de BizTalk|Cuenta de servicio usada para ejecutar la instancia de host In-Process de BizTalk que tiene acceso a la instancia de host In-Process de BizTalk (BTNTSVC).|Usuarios de aplicación de BizTalk<br /><br /> Administradores afiliados de SSO||  
|Cuenta de instancia de host aislada de BizTalk|Cuenta de servicio usada para ejecutar la instancia de host de BizTalk aislada (HTTP/SOAP).|Usuarios de hosts aislados de BizTalk<br /><br /> Administradores afiliados de SSO<br /><br /> IIS_WPG||  
|Servicio de actualización de motor de reglas|Cuenta de servicio usada para ejecutar el Servicio de actualización del motor de reglas; recibe notificaciones de la base de datos de motor de reglas relativas a directivas de implementación o de anulación de implementación.||Función de base de datos de servidor SQL Server RE_HOST_USERS en el BizTalkRuleEngineDb|  
|Usuario de BAM Notification Services|Cuenta de servicio usada para ejecutar Servicios de notificación de SAE; tiene acceso a las bases de datos de SAE.|SQLServer2008NotificationServicesUser$\<**NombreDeEquipo**>|Función de base de datos de servidor SQL Server NSRunService en las bases de datos siguientes:<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> Función de servidor SQL Server BAM_ManagementNSReader para el BAMPrimaryImport|  
|Usuario de servicio web de administración de BAM|Cuenta de usuario para que el servicio web de administración de BAM (BAMManagementService) tenga acceso a varios recursos de BAM. El portal de SAE llama a BAMManagementService con las credenciales de usuario registradas en el portal de SAE para administrar alertas, obtener el XML de definición de SAE y obtener vistas de SAE|IIS_WPG|Función de base de datos de servidor SQL Server NSSubscriberAdmin en las siguientes bases de datos:<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> Función de servidor SQL Server BAM_ManagementWS para el BAMPrimaryImport|  
|Cuenta de grupo de aplicaciones de SAE|Cuenta de grupo de aplicaciones para BAMAppPool que aloja el sitio Web del portal de SAE.|IIS_WPG||  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Grupos locales](../core/local-groups.md)  
  
-   [Grupos de dominio](../core/domain-groups.md)