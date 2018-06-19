---
title: Derechos de usuario mínimos de seguridad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, user accounts
- permissions, user accounts
- permissions, roles
- administrator accounts, permissions
- roles, permissions
- permissions, administrator accounts
- user accounts, permissions
- user accounts, access control
- security, permissions
ms.assetid: 44b6e7da-8e6c-40c0-a250-52ab422c0adf
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ad405afd1f69b4499b8c4650586411957a2ca3c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22265588"
---
# <a name="minimum-security-user-rights"></a>Derechos de usuario mínimos de seguridad
Los grupos y cuentas usados por BizTalk Server tienen los derechos de usuario mínimos necesarios para realizar la mayoría de las tareas. Por este motivo, hay ciertas tareas para las que puede necesitar más derechos de usuario que los concedidos automáticamente por BizTalk Server al grupo al que pertenece. En este tema:  
  
 [Grupo y la pertenencia a roles](../core/minimum-security-user-rights.md#BKMK_GroupRole)  
  
 [Derechos de usuario para realizar tareas administrativas](../core/minimum-security-user-rights.md#BKMK_UserRights)  
  
 [Adición de la Comunidad: lista de tareas](../core/minimum-security-user-rights.md#BKMK_Community)  
  
##  <a name="BKMK_GroupRole"></a> Grupo y la pertenencia a roles  
 En la tabla siguiente se describen los derechos de usuario de seguridad mínimos que necesitará para realizar tareas en BizTalk Server.  
  
|Tarea|Grupos o roles|  
|----------|---------------------|  
|**Programa de instalación**||  
|Installation|-Local de administradores|  
|Configuración|: Los administradores del servidor de BizTalk<br />-Local de administradores<br />-   sysadmin SQL Server Role<br />: Los administradores SSO<br />-   OLAP Administrator|  
|Unirse a un grupo de BizTalk Server|-Local de administradores<br />: Los administradores del servidor de BizTalk|  
|**Administración de BizTalk**||  
|Crear una base de datos de cuadro de mensajes|: Los administradores del servidor de BizTalk<br />-   sysadmin SQL Server Role|  
|Crear o eliminar un host de BizTalk|: Los administradores del servidor de BizTalk<br />-rol de base de datos de SQL Server db_ddladmin en las bases de datos de BizTalk MessageBox|  
|Cambiar la propiedad Seguimiento de host para un host|: Los administradores del servidor de BizTalk<br />-rol de base de datos de SQL Server db_securityadmin en la base de datos de importación principal de BAM y las bases de datos de BizTalk MessageBox, la base de datos de seguimiento de BizTalk|  
|Crear (instalar), eliminar o cambiar las credenciales de una instancia de host|<ul><li>Administradores de servidor BizTalk Server</li><li>Administradores locales</li><li>Función de SQL Server securityadmin en los servidores en los que se encuentren las bases de datos siguientes:<br /><br /> <ul><li>Bases de datos de cuadro de mensajes de BizTalk, base de datos de administración de BizTalk, base de datos de motor de reglas, base de datos de seguimiento de BizTalk y base de datos de importación principal de BAM</li></ul></li><li>Función de base de datos de SQL Server db_securityadmin en las bases de datos siguientes:<br /><br /> <ul><li>Bases de datos de cuadro de mensajes de BizTalk, base de datos de administración de BizTalk, base de datos de motor de reglas, base de datos de seguimiento de BizTalk y base de datos de importación principal de BAM</li></ul></li></ul>|  
|Iniciar o detener una instancia de host|: Los administradores del servidor de BizTalk|  
|Agregar o quitar un servidor|: Los administradores del servidor de BizTalk<br />-Local de administradores en el equipo está agregando o quitando.|  
|Agregar o quitar un controlador de recepción|: Los administradores del servidor de BizTalk<br />: Administradores afiliados de SSO|  
|Iniciar o detener aplicaciones, orquestaciones, puertos de envío y grupos de puertos de envío|-Operadores de BizTalk Server|  
|Habilitar o deshabilitar ubicaciones de recepción|-Operadores de BizTalk Server|  
|Buscar artefactos|-Operadores de BizTalk Server|  
|Agregar un adaptador|: Los administradores del servidor de BizTalk<br />: Administradores afiliados de SSO|  
|Bases de datos de copia de seguridad|-Función BTS_BACKUP_USERS para las bases de datos<br />-función de SQL Server sysadmin en SQL Server que hospeda la base de datos de administración de BizTalk. **Nota:** debe configurar el servicio Agente SQL Server para ejecutarse en una cuenta de dominio o una cuenta local con un usuario asignado en cada instancia de SQL Server.|  
|Configurar grupos de BizTalk con un certificado|: Los administradores del servidor de BizTalk|  
|Todas las demás tareas (incluido WMI)|: Los administradores del servidor de BizTalk|  
|**Operaciones y el mensaje y la instancia del servicio de seguimiento**||  
|Ver la página Concentrador de grupo, realizar consultas, guardar y cargar consultas|-Operadores de BizTalk Server|  
|Ver resultados de consultas|-Operadores de BizTalk Server|  
|Configuración general y configuración de seguimiento|-Administradores de BizTalk Server (lectura y escritura)<br />-Operadores de BizTalk Server (lectura)|  
|Examinar un cubo de seguimiento de estado|: Los administradores del servidor de BizTalk|  
|Ver propiedades del mensaje|: Los administradores del servidor de BizTalk|  
|Guardar cuerpos de mensaje|: Los administradores del servidor de BizTalk|  
|Use **Buscar mensaje** consulta|: Los administradores del servidor de BizTalk|  
|Use **compilación de consulta**|: Los administradores del servidor de BizTalk|  
|Usar el depurador de orquestaciones|: Los administradores del servidor de BizTalk|  
|Vea el flujo de mensajes y los eventos de mensajes en la página Concentrador de grupo mediante la consola de administración de BizTalk Server.|-Operadores de BizTalk Server|  
|Suspender, finalizar o reanudar instancias|-Operadores de BizTalk Server|  
|Archivar o purgar mensajes de la base de datos de seguimiento|-db_owner en la base de datos de seguimiento de BizTalk|  
|Todas las demás tareas|: Los administradores del servidor de BizTalk|  
|**Editor de perfiles de seguimiento**||  
|Leer o escribir en la base de datos de administración de BizTalk|: Los administradores del servidor de BizTalk|  
|**Bus de eventos de supervisión de MMC**||  
|Todas las tareas|: Los administradores del servidor de BizTalk|  
|**Asistente para publicación de servicio de WCF de BizTalk**||  
|Todas las tareas|-Local de administradores|  
|**Asistente de publicación de servicios Web de BizTalk**||  
|Todas las tareas|-Local de administradores|  
|**Supervisión de la actividad económica**||  
|Ejecutar BM.exe|-rol de base de datos de SQL Server db_owner en las bases de datos de importación principal de BAM, esquema de estrella de BAM y archivo de BAM|  
|Ejecutar BM.exe si hay una base de datos de Analysis Services|-rol de base de datos de SQL Server db_owner en las bases de datos de importación principal de BAM, esquema de estrella de BAM y archivo de BAM<br />: Los administradores OLAP en la base de datos de Analysis Services de BAM|  
|Crear una cuenta para vista de BAM|-rol de base de datos de SQL Server db_owner en la base de datos de importación principal de BAM<br />: Los administradores OLAP en la base de datos de Analysis Services de BAM|  
|**Motor de reglas (reglas de publicación)**||  
|Implementar o anular la implementación de directivas, manipular artefactos relacionados con la seguridad|-Rol de base de datos RE_ADMIN_USERS SQL Server en la base de datos de motor de reglas|  
  
##  <a name="BKMK_UserRights"></a> Derechos de usuario para realizar tareas administrativas  
 Para realizar tareas administrativas mediante la consola de administración de BizTalk Server o el Instrumental de administración de Windows (Windows Management Instrumentation, WMI), la cuenta que realiza las tareas administrativas necesita niveles diferentes de derechos de usuario según la tarea.  
  
 En la tabla siguiente se describen los derechos de usuario que la cuenta necesita para realizar las tareas, desde los derechos mínimos (nivel 1) hasta los máximos (nivel 4).  
  
|Nivel de derechos de usuario|Derechos de usuario concedidos|Tareas|  
|--------------------------|-------------------------|-----------|  
|0|-Operadores de BizTalk Server|-Administración básica y tareas de supervisión. Sin capacidad para cambiar valores de configuración. Sin acceso a las propiedades ni al contenido de los mensajes.|  
|1|: Los administradores del servidor de BizTalk|-Todas las tareas administrativas, excepto las que requieren derechos de usuario de 2 a 4 de nivel|  
|2|-Derechos de usuario concedidos al nivel 1<br />-rol de SQL Server securityadmin en todos los servidores de SQL Server<br />-los roles de base de datos de SQL Server db_securityadmin y db_accessadmin en las bases de datos de seguimiento de BizTalk, el motor de reglas, administración de BizTalk, importación principal de BAM y BizTalk MessageBox<br />-rol de base de datos de SQL Server db_ddladmin en todas las bases de datos de BizTalk MessageBox<br />: Administradores afiliados de SSO|: Permite crear y eliminar hosts de BizTalk<br />-Host cambio tracking (propiedad)<br />-Agregar y eliminar servidores<br />-Agregar y eliminar controladores de recepción<br />-Agregar adaptadores|  
|3|-Derechos de usuario concedidos al nivel 2<br />-Local de administradores en todos los equipos de tiempo de ejecución de BizTalk Server|: Permite crear y eliminar instancias de host|  
|4|-Derechos de usuario concedidos al nivel 3<br />-función de SQL Server sysadmin en todos los servidores SQL Server que tienen bases de datos de BizTalk MessageBox|-Crear bases de datos de cuadro de mensajes|  
  
##  <a name="BKMK_Community"></a> Adición de la Comunidad: lista de tareas  
 [Derechos de seguridad mínimos para BizTalk Server 2013 R2](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx) ()http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)  
  
## <a name="see-also"></a>Vea también  
 [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md)   
 [Diseñar las arquitecturas de sistema de BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [Bases de datos de BizTalk Server](../core/databases-in-biztalk-server.md)   
 [Cuentas de grupos y de usuario de Windows en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)