---
title: Las bases de datos de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM]
- Archive database [BAM]
- Analysis database [BAM]
- Windows SharePoint Services, content database
- Windows SharePoint Services, configuration database
- TPM database
- BizTalk Server, databases
- Notification Services Instance database [BAM]
- Star Schema database [BAM]
- Primary Import database [BAM]
- Rule Engine database
- databases, BizTalk Server
- SSO database
- Tracking Analysis Server database [BAM]
- Management database
- Tracking database
- MessageBox database
ms.assetid: bb504a26-cae6-4f2a-9b86-3554ef8f6045
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08cd452aa7f56ad7802c1ea458620ed9fcd21047
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242612"
---
# <a name="databases-in-biztalk-server"></a>Bases de datos en BizTalk Server
Microsoft BizTalk Server instala varias bases de datos en el servidor SQL Server. Este tema describen estas bases de datos y los grupos de lógica SQL utilizados por estas bases de datos.  

## <a name="database-descriptions"></a>Descripciones de la base de datos
La tabla siguiente describen las características de uso típico de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos.  
  
Las operaciones de tiempo de ejecución de BizTalk Server suelen usan las primeras cuatro bases de datos: base de datos de administración de BizTalk Server, bases de datos de cuadro de mensajes, base de datos de seguimiento y base de datos SSO. Según la funcionalidad de BizTalk Server que use, podrá utilizar todas o algunas de las demás bases de datos de la tabla.  
  
|Base de datos|Nombre predeterminado de la base de datos|Description|  
|--------------|---------------------------|-----------------|  
|Análisis de BAM|BAMAnalysis|Esta base de datos contiene los cubos OLAP de Supervisión de la actividad económica (BAM) para los análisis con y sin conexión.|  
|Archivo de BAM|BAMArchive|Esta base de datos archiva datos antiguos de actividad económica. Cree una base de datos de archivo de BAM para reducir al mínimo la acumulación de datos de actividad económica en la base de datos de importación principal de BAM.|  
|Base de datos de la aplicación de servicios de notificación de BAM|BAMAlertsApplication|Esta base de datos contiene información de alertas para notificaciones de BAM. Por ejemplo, al crear una alerta utilizando el portal de BAM, las entradas se insertan en la base de datos especificando las condiciones y eventos a los que pertenece la alerta, así como otros datos complementarios relativos a ésta.|  
|Base de datos de instancia de servicios de notificación de BAM|BAMAlertsNSMain|Esta base de datos contiene información de la instancia que especifica el modo en que los servicios de notificación se conectan con el sistema supervisado por BAM.|  
|Base de datos de importación principal de BAM|BAMPrimaryImport|Base de datos donde BAM recopila los datos sin procesar de seguimiento.|  
|Esquema de estrella de BAM|BAMStarSchema|Esta base de datos contiene la tabla provisional y las tablas de dimensiones y medidas.|  
|Base de datos de administración de BizTalk|BizTalkMgmtDb|Esta base de datos es el almacén central de metainformación para todas las instancias de BizTalk Server.|  
|Base de datos de BizTalk MessageBox|BizTalkMsgBoxDb|El motor de BizTalk Server usa esta base de datos para el enrutamiento, la puesta en cola, la administración de instancias y otras tareas.|  
|Base de datos de seguimiento de BizTalk|BizTalkDTADb|Esta base de datos almacena datos de supervisión de estado de cuyo seguimiento se ocupa el motor de seguimiento de BizTalk Server.|  
|Base de datos del motor de reglas|BizTalkRuleEngineDb|Esta base de datos es un repositorio para lo siguiente:<br /><br /> -Directivas, que son conjuntos de reglas relacionadas.<br />-Vocabularios, que son colecciones de nombres descriptivos y específico de dominio para referencias de datos de reglas.|  
|base de datos de SSO|SSODB|Esta base de datos de inicio de sesión único empresarial almacena de forma segura la información de configuración de las ubicaciones de recepción.|  
|Base de datos de configuración de Windows SharePoint Services|*Definido por el usuario*|Esta base de datos contiene toda la configuración global del servidor.|  
|Base de datos de contenido de Windows SharePoint Services|*Definido por el usuario*|Esta base de datos incluye todo el contenido de un sitio, como elementos de lista y documentos.|  

## <a name="database-login-accounts"></a>Cuentas de inicio de sesión de base de datos

[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]crea grupos de inicio de sesión SQL y las asigna a los roles de SQL Server y los roles de base de datos que se muestran en la tabla siguiente:  
  
|Grupo|Descripción|Funciones de servidor SQL Server o de base de datos|  
|-----------|-----------------|----------------------------------------|  
|Usuarios de aplicación de BizTalk|Incluye todas las cuentas con acceso a los hosts de tipo En curso de BizTalk (procesos de host en BizTalk Server, BTSNTSvc.exe).  Use un Grupo de host de BizTalk por cada host de tipo En curso de su entorno.|Rol de base de datos de SQL Server BTS_HOST_USERS en las siguientes bases de datos:<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> Función de base de datos de servidor SQL Server de BAM_EVENT_WRITER en el BAMPrimaryImport|  
|Usuarios de hosts aislados de BizTalk|Incluye todas las cuentas con acceso a los hosts aislados de BizTalk. Utilice un grupo de host aislado de BizTalk por cada host aislado de su entorno.|Rol de base de datos de SQL Server BTS_HOST_USERS en las siguientes bases de datos:<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport|  
|Administradores de servidor BizTalk Server|Incluye todos los administradores de BizTalk Server que implementarán soluciones, administrarán aplicaciones y resolverán problemas de procesamiento de mensajes.|Función de base de datos de servidor SQL Server BTS_ADMIN_USERS en las siguientes bases de datos:<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> Función de base de datos de servidor SQL Server db_owner para las siguientes bases de datos:<br /><br /> BAMStarSchema<br /><br /> BAMPrimaryImport<br /><br /> BAMArchive<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> Rol de base de datos de servidor SQL Server NSAdmin en las siguientes bases de datos:<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BizTalkDTADb<br /><br /> BizTalkMgmtDb<br /><br /> Administradores de OLAP en el equipo que hospeda la base de datos de OLAP BAMAnalysis.|  
|Operadores de servidor BizTalk Server|Tiene una función de pocos privilegios, con acceso sólo para supervisar y solucionar problemas de acciones<br /><br /> No contiene ninguna cuenta de servicio|Rol de base de datos de SQL Server BTS_OPERATORS en las siguientes bases de datos:<br /><br /> BizTalkDTADb<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb|  
|Administradores de SSO|Administradores de nivel superior del servicio de inicio de sesión único (SSO) empresarial.<br /><br /> Contiene la cuenta de usuario utilizada para ejecutar la configuración de BizTalk que debe estar en este grupo.<br /><br /> Contiene la cuenta del servicio de inicio de sesión único (SSO) empresarial y los usuarios o grupos que necesitan tener la capacidad de configurar y administrar BizTalk Server y SSO.|Función de base de datos de servidor SQL Server db_owner para el SSO<br /><br /> Función de servidor SQL Server securityadmin para el servidor SQL Server en que se encuentra SSO|  

[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]crea las cuentas de inicio de sesión SQL y las asigna a los roles de base de datos de SQL Server enumerados en la tabla siguiente:  
  
|Cuenta de usuario|Descripción|Roles de base de datos de servidor SQL|  
|------------------|-----------------|------------------------|  
|Servicio de actualización de motor de reglas|Cuenta de usuario usada para ejecutar el Servicio de actualización del motor de reglas.|Función de base de datos de servidor SQL Server RE_HOST_USERS en el BizTalkRuleEngineDb|  
|Usuario de BAM Notification Services|Cuenta de usuario usada para ejecutar los servicios de notificación de BAM.|Función de base de datos de servidor SQL Server NSRunService en las bases de datos siguientes:<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> Rol de base de datos de servidor SQL Server BAM_ManagementNSReader para BAMPrimaryImport|  
|Usuario de Servicio Web de administración de BAM|Cuenta de servicio utilizada en el servicio Web de administración de BAM.|Función de base de datos de servidor SQL Server NSSubscriberAdmin en las siguientes bases de datos:<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> Rol de base de datos de servidor SQL Server BAM_ManagementWS para BAMPrimaryImport|  
  
  
## <a name="see-also"></a>Vea también  
 [Trabajos y la estructura de base de datos](../core/database-structure-and-jobs.md)   
 [La base de datos de cuadro de mensajes](../core/the-messagebox-database.md)   
 [Mantener BizTalk Server](../technical-guides/maintaining-biztalk-server-databases.md)   
 [Escalar soluciones](../core/scaling-your-solutions.md)   
 [Grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [Cómo cambiar contraseñas y cuentas de servicio](../core/how-to-change-service-accounts-and-passwords.md)