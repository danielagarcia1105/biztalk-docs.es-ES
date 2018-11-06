---
title: 'Lista de comprobación: Planificación de operaciones en un entorno seguro | Microsoft Docs'
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
ms.openlocfilehash: fb882531141114842983ca93be9d799898ecefdf
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753116"
---
# <a name="checklist-planning-for-operations-in-a-secure-environment"></a>Lista de comprobación: Planificación de operaciones en un entorno seguro
Ejecutando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno seguro requiere pasos adicionales para la implementación y configuración. Mientras que las instalaciones de sistema operativo predeterminada no necesitan realizar estos elementos en la cuenta, pero en escenarios donde se han aplicado las directivas de seguridad restrictiva, debe tomar en cuenta la información de esta sección. El nivel de restricción que se aplica a los servidores puede variar pero información a continuación debería cubrir la mayoría de los casos y sería un buen punto de partida.  

-   [Consideraciones de seguridad para equipos que ejecutan BizTalk Server](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_BTSSec)  

-   [Consideraciones de seguridad para equipos que ejecutan SQL Server](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_SQLServSec)  

-   [Consideraciones de seguridad adicionales](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_AddSec)  

<a name="BKMK_BTSSec"></a>   
## <a name="security-considerations-for-computers-running-biztalk-server"></a>Consideraciones de seguridad para equipos que ejecutan BizTalk Server  
 La siguiente tabla proponen la configuración de seguridad en equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

### <a name="user-rights-assignment"></a>Asignación de derechos de usuario  
 Para iniciar el complemento MMC de asignación de derechos de usuario, haga clic en **iniciar**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **directiva de seguridad Local**. En el **directiva de seguridad Local** MMC complemento, expanda **configuración de seguridad**, expanda **directivas locales**y, a continuación, haga clic en **asignación de derechos de usuario**.  

|Configuración de directiva|Valores|Referencia y detalles|  
|--------------------|------------|---------------------------|  
|Iniciar sesión como servicio|Usuarios de aplicación de BizTalk|Necesario para ejecutar instancias de Host de BizTalk. Para obtener más información acerca de las cuentas de usuario diferente, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=155755) (http://go.microsoft.com/fwlink/?LinkID=155755).|  
|Iniciar sesión como servicio|Cuenta de servicio de actualización de RuleEngine|Necesario para ejecutar el servicio de actualización de RuleEngine. Para obtener más información acerca de las cuentas de usuario diferente, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=155755) (http://go.microsoft.com/fwlink/?LinkID=155755).|  
|Iniciar sesión como servicio|Cuenta de servicio de inicio de sesión único|Necesario para ejecutar Enterprise Single Sign-On Service. Para obtener más información acerca de las cuentas de usuario diferente, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=155755) (http://go.microsoft.com/fwlink/?LinkID=155755).|  

### <a name="system-services"></a>Servicios del sistema  
 Para iniciar el complemento MMC de servicios, haga clic en **iniciar**, haga clic en **ejecutar**y en el **ejecutar** cuadro de diálogo, escriba `services.msc` y presione ENTRAR.  


|                Nombre del servicio                 | Tipo de inicio<sup>1</sup> |                                                              Detalles                                                               |       Usuario<sup>2</sup>        | Permisos  |             Detalles             |
|---------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|--------------|---------------------------------|
|           Aplicación de sistema COM+           |        Automático         |                                                BizTalk requiere se ejecute correctamente                                                 |           (predeterminado).           |              |                                 |
|                 Cliente DHCP                 |        Automático         |                                              Necesario incluso si las direcciones IP son estáticas                                              |           (predeterminado).           |              |                                 |
|     Coordinador de transacciones distribuidas     |        Automático         |                                                BizTalk requiere se ejecute correctamente                                                 |      Cuenta de servicio de inicio de sesión único      | Control total |  Necesario para iniciar el servicio de inicio de sesión único  |
|                                             |                          |                                                                                                                                    | Cuenta de servicio de Hosts de BizTalk | Control total | Necesarios para empezar a Hosts de BizTalk |
|                                             |                          |                                                                                                                                    |        Servicio de red        | Control total |         Requiere IIS         |
|            HTTP SSL<sup>3</sup>             |        Automático         |                                                          Requiere IIS                                                           |           (predeterminado).           |              |                                 |
|         Los Servicios IPSEC<sup>3</sup>          |        Automático         |                                              IPSEC aumenta la seguridad de red si utiliza                                              |           (predeterminado).           |              |                                 |
|                  Netlogon                   |        (predeterminado).         |                                                                                                                                    |         Servicio local         | Control total |                                 |
| Proveedor de soporte técnico de seguridad de NT LM<sup>3</sup> |        Automático         | Necesario para la autenticación de Kerberos para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en SQL |           (predeterminado).           |              |                                 |
|      Administrador de conexión de acceso remoto       |        (predeterminado).         |                                                                                                                                    |      Cuenta de servicio de inicio de sesión único      | Control total |  Necesario para iniciar el servicio de inicio de sesión único  |
|                                             |                          |                                                                                                                                    | Cuenta de servicio de Hosts de BizTalk | Control total | Necesarios para empezar a Hosts de BizTalk |
|                                             |                          |                                                                                                                                    |        Servicio de red        | Control total |         Requiere IIS         |
|     Localizador de procedimiento remoto (RPC) de la llamada     |        Automático         |                                                        Requerido por BizTalk                                                         |           (predeterminado).           |              |                                 |
|  Servicio de detección automática de Proxy Web de WinHTTP   |        (predeterminado).         |                                                                                                                                    |      Cuenta de servicio de inicio de sesión único      | Control total |  Necesario para iniciar el servicio de inicio de sesión único  |
|                                             |                          |                                                                                                                                    | Cuenta de servicio de Hosts de BizTalk | Control total | Necesarios para empezar a Hosts de BizTalk |

 <sup>1</sup> un valor (predeterminado) significa que no se puede cambiar la configuración predeterminada que se aplica la directiva de seguridad  

 <sup>2</sup> un valor (predeterminado) significa que no han cambiado los permisos de usuario predeterminada para el servicio  

### <a name="registry-settings"></a>Configuración del Registro  
 Para iniciar el Editor del registro, haga clic en **iniciar**, haga clic en **ejecutar**y en el **ejecutar** cuadro de diálogo, escriba `regedit` y presione ENTRAR.  

|Key|Usuario|Permisos|Detalles|  
|---------|----------|-----------------|-------------|  
|HKLM\ SYSTEM\CurrentControlSet\Services\DHCP|Servicio de red|Control total|Requerido por el servicio cliente DHCP|  
|HKLM\ SYSTEM\CurrentControlSet\Services\TCPIP|Servicio de red|Control total|Requerido por el servicio cliente DHCP|  

<a name="BKMK_SQLServSec"></a>   
## <a name="security-considerations-for-computers-running-sql-server"></a>Consideraciones de seguridad para equipos que ejecutan SQL Server  
 La siguiente tabla proponen la configuración de seguridad en equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  

### <a name="user-rights-assignment"></a>Asignación de derechos de usuario  
 Para iniciar el complemento MMC de asignación de derechos de usuario, haga clic en **iniciar**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **directiva de seguridad Local**. En el **directiva de seguridad Local** MMC complemento, expanda **configuración de seguridad**, expanda **directivas locales**y, a continuación, haga clic en **asignación de derechos de usuario**.  


|                         Configuración de directiva                         |                                             Valores                                              |                                                                                                                             Referencia y detalles                                                                                                                             |
|----------------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              Actuar como parte del sistema operativo               |                  Cuenta de servicio del Agente SQL Server, cuenta de servicio SQL Server                   |         Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [Setting Up Windows Service Accounts](http://go.microsoft.com/fwlink/?LinkId=157415) (<http://go.microsoft.com/fwlink/?LinkId=157415>).          |
|               Adjust memory quotas for a process (Ajustar las cuotas de memoria de un proceso)               |                   Cuenta de servicio del Agente SQL Server, cuenta de servicio SQL Server                   |         Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [Setting Up Windows Service Accounts](http://go.microsoft.com/fwlink/?LinkId=157415) (<http://go.microsoft.com/fwlink/?LinkId=157415>).          |
|                    Omisión de la comprobación transversal                    |                   Cuenta de servicio del Agente SQL Server, cuenta de servicio SQL Server                   |         Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [Setting Up Windows Service Accounts](http://go.microsoft.com/fwlink/?LinkId=157415) (<http://go.microsoft.com/fwlink/?LinkId=157415>).          |
|                     Crear objetos globales                      |                                   Cuenta de servicio de SQL Server                                    |                                          Requiere el servicio SSIS. Para obtener más información, consulte [Setting Up Windows Service Accounts](http://go.microsoft.com/fwlink/?LinkId=157415) (<http://go.microsoft.com/fwlink/?LinkId=157415>).                                           |
| Habilitar las cuentas de usuario y equipo sea de confianza para delegación | Nombre del clúster de servidores SQL Server Service cuenta, los servidores SQL Server, BizTalk Server, SQL Server | BizTalk Server requiere. Nombre del servidor está en el formulario \<servername\>$. Para obtener más información, consulte [Cómo: habilitar la autenticación Kerberos en un clúster de conmutación por error de SQL Server](http://go.microsoft.com/fwlink/?LinkId=157417) (<http://go.microsoft.com/fwlink/?LinkId=157417>). |
|                      Iniciar sesión como servicio                       |                   Cuenta de servicio del Agente SQL Server, cuenta de servicio SQL Server                   |         Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [Setting Up Windows Service Accounts](http://go.microsoft.com/fwlink/?LinkId=157415) (<http://go.microsoft.com/fwlink/?LinkId=157415>).          |
|                      Iniciar sesión como servicio                       |                                       Cuenta de servicio de inicio de sesión único                                       |       Necesario para ejecutar Enterprise Single Sign-On Service. Para obtener más información acerca de las cuentas de usuario diferente, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=155755) (<http://go.microsoft.com/fwlink/?LinkID=155755>).       |
|                      Inicie sesión como trabajo por lotes                       |                   Cuenta de servicio del Agente SQL Server, cuenta de servicio SQL Server                   |         Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [Setting Up Windows Service Accounts](http://go.microsoft.com/fwlink/?LinkId=157415) (<http://go.microsoft.com/fwlink/?LinkId=157415>).          |
|                 Replace a process level token (Reemplazar un símbolo de nivel de proceso)                  |                   Cuenta de servicio del Agente SQL Server, cuenta de servicio SQL Server                   |         Necesario para ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información, consulte [Setting Up Windows Service Accounts](http://go.microsoft.com/fwlink/?LinkId=157415) (<http://go.microsoft.com/fwlink/?LinkId=157415>).          |

### <a name="system-services"></a>Servicios del sistema  
 Para iniciar el complemento MMC de servicios, haga clic en **iniciar**, haga clic en **ejecutar**y en el **ejecutar** cuadro de diálogo, escriba `services.msc` y presione ENTRAR.  


|                Nombre del servicio                 |     Tipo de inicio<sup>1</sup>      |                                                              Detalles                                                               |             Usuario<sup>2</sup>              | Permisos  |            Detalles            |
|---------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|--------------|-------------------------------|
|                 Cliente DHCP                 |             Automático             |                                              Necesario incluso si las direcciones IP son estáticas                                              |                 (predeterminado).                 |              |                               |
|     Coordinador de transacciones distribuidas     |              Manual               |                                             Inicio del servicio administrado por el servicio de Cluster Server                                             |            Cuenta de servicio de inicio de sesión único            | Control total | Necesario para iniciar el servicio de inicio de sesión único |
|                                             |                                   |                                                                                                                                    |              Servicio de red              | Control total |        Requiere IIS        |
|            HTTP SSL<sup>3</sup>             |             Automático             |                                                          Requiere IIS                                                           |                 (predeterminado).                 |              |                               |
|         Los Servicios IPSEC<sup>3</sup>          |             Automático             |                                              IPSEC aumenta la seguridad de red si utiliza                                              |                 (predeterminado).                 |              |                               |
|                  Netlogon                   |             (predeterminado).             |                                                                                                                                    |               Servicio local               | Control total |                               |
| Proveedor de soporte técnico de seguridad de NT LM<sup>3</sup> |             Automático             | Necesario para la autenticación de Kerberos para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en SQL |                 (predeterminado).                 |              |                               |
|      Administrador de conexión de acceso remoto       |             (predeterminado).             |                                                                                                                                    |            Cuenta de servicio de inicio de sesión único            | Control total | Necesario para iniciar el servicio de inicio de sesión único |
|                                             |                                   |                                                                                                                                    |              Servicio de red              | Control total |        Requiere IIS        |
|                   Servidor                    |             Automático             |                                              Utilizan los recursos del recurso compartido de archivos en clúster                                               |              Servicio de red              | Control total |                               |
|  Servicio de detección automática de Proxy Web de WinHTTP   |             (predeterminado).             |                                                                                                                                    |            Cuenta de servicio de inicio de sesión único            | Control total | Necesario para iniciar el servicio de inicio de sesión único |
|                                             | Servicio de publicación World Wide Web |                                                             Automático                                                              | Requiere SQL Server Reporting Services |  (predeterminado).   |                               |

 <sup>1</sup> un valor (predeterminado) significa que no se puede cambiar la configuración predeterminada que se aplica la directiva de seguridad  

 <sup>2</sup> un valor (predeterminado) significa que no han cambiado los permisos de usuario predeterminada para el servicio  

### <a name="registry-settings"></a>Configuración del Registro  
 Para iniciar el Editor del registro, haga clic en **iniciar**, haga clic en **ejecutar**y en el **ejecutar** cuadro de diálogo, escriba `regedit` y presione ENTRAR.  

|Key|Usuario|Permisos|Detalles|  
|---------|----------|-----------------|-------------|  
|HKLM\ SYSTEM\CurrentControlSet\Services\DHCP|Servicio de red|Control total|Requerido por el servicio cliente DHCP|  
|HKLM\ SYSTEM\CurrentControlSet\Services\TCPIP|Servicio de red|Control total|Requerido por el servicio cliente DHCP|  

<a name="BKMK_AddSec"></a>   
## <a name="additional-security-considerations"></a>Consideraciones de seguridad adicionales  
 La siguiente tabla propone las otras relacionadas con la seguridad opciones importantes para su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  


|                                        Artefacto afectado                                        |                                 Cambiar                                  |                                                                                                               Referencia y detalles                                                                                                                |
|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                       Cuenta de servicio de inicio de sesión único                                       |       Conceder el permiso Control total en el clúster en el Administrador de clústeres       |                                                                                             Este cambio es necesario para el inicio de sesión único para que funcione correctamente                                                                                              |
| Nombre del clúster de servidores SQL Server Service cuenta, los servidores SQL Server, BizTalk Server, SQL Server |                Relación de confianza para delegación en Active Directory                 | Se requiere para la autenticación Kerberos apropiada. Para obtener más información, consulte [Cómo: habilitar la autenticación Kerberos en un clúster de conmutación por error de SQL Server](http://go.microsoft.com/fwlink/?LinkId=157417) (<http://go.microsoft.com/fwlink/?LinkId=157417>). |
|                                   Cuenta de servicio de SQL Server                                    |                 Conceder permiso para crear entradas de SPN                  |            Se requiere para la autenticación Kerberos apropiada. Para obtener más información, consulte [cómo usar la autenticación Kerberos en SQL Server](http://go.microsoft.com/fwlink/?LinkId=157420) (<http://go.microsoft.com/fwlink/?LinkId=157420>).             |
|                               Nodos de SQL Server, el nombre del clúster SQL                                |         Cree entradas SPN para el usuario de cuenta de servicio de SQL Server          |            Se requiere para la autenticación Kerberos apropiada. Para obtener más información, consulte [cómo usar la autenticación Kerberos en SQL Server](http://go.microsoft.com/fwlink/?LinkId=157420) (<http://go.microsoft.com/fwlink/?LinkId=157420>).             |
|                               Recurso de clúster nombre de red de SQL                                |     El registro de DNS deben ser correctos, habilitar la autenticación Kerberos      |                                                                                                    Necesario para la autenticación Kerberos apropiada                                                                                                     |
|                                Configuración de superficie de SQL Server                                 |              Habilitar la conexión de administrador directo remoto              |                                           Requerido por el servicio SQL Browser para funcionar correctamente que es necesaria para los clientes de SQL (BizTalk/ASP.NET) para ubicar correctamente la instancia con nombre de SQL Server                                           |
|                                 Grupo de usuarios de aplicación de BizTalk                                 | Permiso GRANT Execute en **sp_help_jobhistory** en **msdb** base de datos |                                                                           Requerido por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                           |

## <a name="see-also"></a>Vea también  
 [Listas de comprobación para otras tareas importantes](~/technical-guides/checklists-for-other-important-tasks.md)
