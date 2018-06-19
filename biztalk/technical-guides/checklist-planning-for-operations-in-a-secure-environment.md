---
title: 'Lista de comprobación: Planeación de operaciones en un entorno seguro | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d6464df-6736-46e2-a0c7-cc2a256c5144
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c99c14f16df3f6b98555a4006706eb7804f24a34
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976834"
---
# <a name="checklist-planning-for-operations-in-a-secure-environment"></a>Lista de comprobación: Planeación de operaciones en un entorno seguro
Ejecutando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno seguro, requiere pasos adicionales para la implementación y configuración. Mientras que las instalaciones predeterminadas de sistema operativo necesitan no tenerla en cuenta, pero en escenarios donde se aplicaron las directivas de seguridad restrictiva, debe tomar en cuenta la información de esta sección. Puede variar en el nivel de restricción aplicada en servidores, pero la información a continuación debe cubrir la mayoría de los casos y sería un buen punto de partida.  
  
-   [Consideraciones de seguridad para equipos que ejecutan BizTalk Server](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_BTSSec)  
  
-   [Consideraciones de seguridad para equipos que ejecutan SQL Server](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_SQLServSec)  
  
-   [Consideraciones de seguridad adicionales](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_AddSec)  
  
<a name="BKMK_BTSSec"></a>   
## <a name="security-considerations-for-computers-running-biztalk-server"></a>Consideraciones de seguridad para equipos que ejecutan BizTalk Server  
 La siguiente tabla sugiere la configuración de seguridad en equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="user-rights-assignment"></a>Asignación de derechos de usuario  
 Para iniciar el complemento de MMC de asignación de derechos de usuario, haga clic en **iniciar**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **directiva de seguridad Local**. En el **directiva de seguridad Local** MMC complemento, expanda **configuración de seguridad**, expanda **directivas locales**y, a continuación, haga clic en **asignación de derechos de usuario**.  
  
|Configuración de directiva|Valores|Referencia y detalles|  
|--------------------|------------|---------------------------|  
|Iniciar sesión como servicio|Usuarios de aplicación de BizTalk|Necesarios para ejecutar instancias de Host de BizTalk. Para obtener más información acerca de las cuentas de usuario diferente, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=155755) (http://go.microsoft.com/fwlink/?LinkID=155755).|  
|Iniciar sesión como servicio|Cuenta de servicio de actualización de RuleEngine|Necesario para ejecutar el servicio de actualización de RuleEngine. Para obtener más información acerca de las cuentas de usuario diferente, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=155755) (http://go.microsoft.com/fwlink/?LinkID=155755).|  
|Iniciar sesión como servicio|Cuenta de servicio SSO|Necesario para ejecutar el servicio de inicio de sesión único de Enterprise. Para obtener más información acerca de las cuentas de usuario diferente, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=155755) (http://go.microsoft.com/fwlink/?LinkID=155755).|  
  
### <a name="system-services"></a>Servicios del sistema  
 Para iniciar el complemento MMC de servicios, haga clic en **iniciar**, haga clic en **ejecutar**y en el **ejecutar** cuadro de diálogo, escriba `services.msc` y presione ENTRAR.  
  
|Nombre del servicio|Tipo de inicio<sup>1</sup>|Detalles|Usuario<sup>2</sup>|Permissions|Detalles|  
|------------------|------------------------------|-------------|----------------------|-----------------|-------------|  
|Aplicación de sistema COM+|Automático|Requiere BizTalk para que se ejecute correctamente|(predeterminado).|||  
|Cliente DHCP|Automático|Necesario incluso si las direcciones IP estáticas|(predeterminado).|||  
|Coordinador de transacciones distribuidas|Automático|Requiere BizTalk para que se ejecute correctamente|Cuenta de servicio SSO|Control total|Debe para iniciar el servicio SSO|  
||||Cuenta de servicio de Hosts de BizTalk|Control total|Necesita para iniciar los Hosts de BizTalk|  
||||Servicio de red|Control total|Requiere IIS|  
|SSL DE HTTP<sup>3</sup>|Automático|Requiere IIS|(predeterminado).|||  
|Los Servicios IPSEC<sup>3</sup>|Automático|IPSEC aumenta la seguridad de red si utiliza|(predeterminado).|||  
|Netlogon|(predeterminado).||Servicio local|Control total||  
|Proveedor de soporte técnico de seguridad de NT LM<sup>3</sup>|Automático|Necesario para la autenticación de Kerberos para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en SQL|(predeterminado).|||  
|Administrador de conexión de acceso remoto|(predeterminado).||Cuenta de servicio SSO|Control total|Debe para iniciar el servicio SSO|  
||||Cuenta de servicio de Hosts de BizTalk|Control total|Necesita para iniciar los Hosts de BizTalk|  
||||Servicio de red|Control total|Requiere IIS|  
|Localizador de procedimiento remoto (RPC) de la llamada|Automático|Requerido por BizTalk|(predeterminado).|||  
|Servicio de detección automática de Proxy Web WinHTTP|(predeterminado).||Cuenta de servicio SSO|Control total|Debe para iniciar el servicio SSO|  
||||Cuenta de servicio de Hosts de BizTalk|Control total|Necesita para iniciar los Hosts de BizTalk|  
  
 <sup>1</sup> valor (valor predeterminado) significa que no se cambia la configuración predeterminada que se aplica la directiva de seguridad  
  
 <sup>2</sup> valor (valor predeterminado) significa que no se cambiaron los permisos de usuario predeterminados para el servicio  
  
### <a name="registry-settings"></a>Configuración del Registro  
 Para iniciar el Editor del registro, haga clic en **iniciar**, haga clic en **ejecutar**y en el **ejecutar** cuadro de diálogo, escriba `regedit` y presione ENTRAR.  
  
|Key|Usuario|Permissions|Detalles|  
|---------|----------|-----------------|-------------|  
|HKLM\ SYSTEM\CurrentControlSet\Services\DHCP|Servicio de red|Control total|Requerido por el servicio cliente DHCP|  
|HKLM\ SYSTEM\CurrentControlSet\Services\TCPIP|Servicio de red|Control total|Requerido por el servicio cliente DHCP|  
  
<a name="BKMK_SQLServSec"></a>   
## <a name="security-considerations-for-computers-running-sql-server"></a>Consideraciones de seguridad para equipos que ejecutan SQL Server  
 La siguiente tabla sugiere la configuración de seguridad en equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
### <a name="user-rights-assignment"></a>Asignación de derechos de usuario  
 Para iniciar el complemento de MMC de asignación de derechos de usuario, haga clic en **iniciar**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **directiva de seguridad Local**. En el **directiva de seguridad Local** MMC complemento, expanda **configuración de seguridad**, expanda **directivas locales**y, a continuación, haga clic en **asignación de derechos de usuario**.  
  
|Configuración de directiva|Valores|Referencia y detalles|  
|--------------------|------------|---------------------------|  
|Actuar como parte del sistema operativo|Cuenta de servicio Agente SQL Server, cuenta de servicio SQL Server|Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [cuentas de servicios de configuración de Windows](http://go.microsoft.com/fwlink/?LinkId=157415) (http://go.microsoft.com/fwlink/?LinkId=157415).|  
|Adjust memory quotas for a process (Ajustar las cuotas de memoria de un proceso)|Cuenta de servicio Agente SQL Server, cuenta de servicio SQL Server|Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [cuentas de servicios de configuración de Windows](http://go.microsoft.com/fwlink/?LinkId=157415) (http://go.microsoft.com/fwlink/?LinkId=157415).|  
|Omisión de la comprobación transversal|Cuenta de servicio Agente SQL Server, cuenta de servicio SQL Server|Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [cuentas de servicios de configuración de Windows](http://go.microsoft.com/fwlink/?LinkId=157415) (http://go.microsoft.com/fwlink/?LinkId=157415).|  
|Crear objetos globales|Cuenta de servicio de SQL Server|Requiere el servicio SSIS. Para obtener más información, consulte [cuentas de servicios de configuración de Windows](http://go.microsoft.com/fwlink/?LinkId=157415) (http://go.microsoft.com/fwlink/?LinkId=157415).|  
|Habilitar cuentas de usuario y equipo que sea de confianza para la delegación|Nombre del clúster de servidores del servidor BizTalk Server de cuenta, servidores de SQL Server, servicio SQL Server, SQL Server|Requiere el servidor BizTalk Server. Nombre del servidor tiene la forma de \<servername\>$. Para obtener más información, consulte [Cómo: habilitar la autenticación Kerberos en un clúster de conmutación por error de SQL Server](http://go.microsoft.com/fwlink/?LinkId=157417) (http://go.microsoft.com/fwlink/?LinkId=157417).|  
|Iniciar sesión como servicio|Cuenta de servicio Agente SQL Server, cuenta de servicio SQL Server|Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [cuentas de servicios de configuración de Windows](http://go.microsoft.com/fwlink/?LinkId=157415) (http://go.microsoft.com/fwlink/?LinkId=157415).|  
|Iniciar sesión como servicio|Cuenta de servicio SSO|Necesario para ejecutar el servicio de inicio de sesión único de Enterprise. Para obtener más información acerca de las cuentas de usuario diferente, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=155755) (http://go.microsoft.com/fwlink/?LinkID=155755).|  
|Iniciar sesión como proceso por lotes|Cuenta de servicio Agente SQL Server, cuenta de servicio SQL Server|Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [cuentas de servicios de configuración de Windows](http://go.microsoft.com/fwlink/?LinkId=157415) (http://go.microsoft.com/fwlink/?LinkId=157415).|  
|Replace a process level token (Reemplazar un símbolo de nivel de proceso)|Cuenta de servicio Agente SQL Server, cuenta de servicio SQL Server|Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [cuentas de servicios de configuración de Windows](http://go.microsoft.com/fwlink/?LinkId=157415) (http://go.microsoft.com/fwlink/?LinkId=157415).|  
  
### <a name="system-services"></a>Servicios del sistema  
 Para iniciar el complemento MMC de servicios, haga clic en **iniciar**, haga clic en **ejecutar**y en el **ejecutar** cuadro de diálogo, escriba `services.msc` y presione ENTRAR.  
  
|Nombre del servicio|Tipo de inicio<sup>1</sup>|Detalles|Usuario<sup>2</sup>|Permissions|Detalles|  
|------------------|------------------------------|-------------|----------------------|-----------------|-------------|  
|Cliente DHCP|Automático|Necesario incluso si las direcciones IP estáticas|(predeterminado).|||  
|Coordinador de transacciones distribuidas|Manual|Inicio del servicio administrado por el servicio de Cluster Server|Cuenta de servicio SSO|Control total|Debe para iniciar el servicio SSO|  
||||Servicio de red|Control total|Requiere IIS|  
|SSL DE HTTP<sup>3</sup>|Automático|Requiere IIS|(predeterminado).|||  
|Los Servicios IPSEC<sup>3</sup>|Automático|IPSEC aumenta la seguridad de red si utiliza|(predeterminado).|||  
|Netlogon|(predeterminado).||Servicio local|Control total||  
|Proveedor de soporte técnico de seguridad de NT LM<sup>3</sup>|Automático|Necesario para la autenticación de Kerberos para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en SQL|(predeterminado).|||  
|Administrador de conexión de acceso remoto|(predeterminado).||Cuenta de servicio SSO|Control total|Debe para iniciar el servicio SSO|  
||||Servicio de red|Control total|Requiere IIS|  
|Server|Automático|Utilizado para recursos compartidos de archivos en clúster|Servicio de red|Control total||  
|Servicio de detección automática de Proxy Web WinHTTP|(predeterminado).||Cuenta de servicio SSO|Control total|Debe para iniciar el servicio SSO|  
||Servicio de publicación World Wide Web|Automático|Requiere SQL Server Reporting Services|(predeterminado).||  
  
 <sup>1</sup> valor (valor predeterminado) significa que no se cambia la configuración predeterminada que se aplica la directiva de seguridad  
  
 <sup>2</sup> valor (valor predeterminado) significa que no se cambiaron los permisos de usuario predeterminados para el servicio  
  
### <a name="registry-settings"></a>Configuración del Registro  
 Para iniciar el Editor del registro, haga clic en **iniciar**, haga clic en **ejecutar**y en el **ejecutar** cuadro de diálogo, escriba `regedit` y presione ENTRAR.  
  
|Key|Usuario|Permissions|Detalles|  
|---------|----------|-----------------|-------------|  
|HKLM\ SYSTEM\CurrentControlSet\Services\DHCP|Servicio de red|Control total|Requerido por el servicio cliente DHCP|  
|HKLM\ SYSTEM\CurrentControlSet\Services\TCPIP|Servicio de red|Control total|Requerido por el servicio cliente DHCP|  
  
<a name="BKMK_AddSec"></a>   
## <a name="additional-security-considerations"></a>Consideraciones de seguridad adicionales  
 La siguiente tabla sugiere los otros relacionados con la seguridad valores importantes para su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
|Artefacto afectado|Cambiar|Referencia y detalles|  
|-----------------------|------------|---------------------------|  
|Cuenta de servicio SSO|Conceder el permiso Control total en clúster en el Administrador de clústeres|Este cambio es necesario para SSO para que funcione correctamente|  
|Nombre del clúster de servidores del servidor BizTalk Server de cuenta, servidores de SQL Server, servicio SQL Server, SQL Server|La confianza para delegación en Active Directory|Necesario para la correcta autenticación de Kerberos. Para obtener más información, consulte [Cómo: habilitar la autenticación Kerberos en un clúster de conmutación por error de SQL Server](http://go.microsoft.com/fwlink/?LinkId=157417) (http://go.microsoft.com/fwlink/?LinkId=157417).|  
|Cuenta de servicio de SQL Server|Conceder permiso para crear entradas de SPN|Necesario para la correcta autenticación de Kerberos. Para obtener más información, consulte [cómo usar la autenticación Kerberos en SQL Server](http://go.microsoft.com/fwlink/?LinkId=157420) (http://go.microsoft.com/fwlink/?LinkId=157420).|  
|Nodos de SQL Server, el nombre del clúster SQL|Crear entradas SPN para el usuario de cuenta de servicio de SQL Server|Necesario para la correcta autenticación de Kerberos. Para obtener más información, consulte [cómo usar la autenticación Kerberos en SQL Server](http://go.microsoft.com/fwlink/?LinkId=157420) (http://go.microsoft.com/fwlink/?LinkId=157420).|  
|Recurso de clúster de nombre de red de SQL|El registro de DNS deben ser correctos, habilitar la autenticación Kerberos|Necesario para la correcta autenticación de Kerberos|  
|Configuración de superficie de SQL Server|Habilitar la conexión de administrador directo remoto|Requerido por el servicio SQL Browser para funcionar correctamente y es necesario para los clientes de SQL (BizTalk/ASP.NET) con el fin de localizar correctamente la instancia con nombre de SQL Server|  
|Grupo de usuarios de aplicación de BizTalk|El permiso GRANT Execute en **sp_help_jobhistory** en **msdb** base de datos|Requerido por[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
  
## <a name="see-also"></a>Vea también  
 [Listas de comprobación para otras tareas importantes](~/technical-guides/checklists-for-other-important-tasks.md)