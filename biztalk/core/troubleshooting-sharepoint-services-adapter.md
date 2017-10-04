---
title: "Solución de problemas de SharePoint Services adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77f88174-118d-4ed6-8449-c89ca195ce5c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9885696df24cd5c5f8321ad3c6dd79d444559a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-sharepoint-services-adapter"></a>Solución de problemas del adaptador de SharePoint Services
Este tema está centrado en la resolución de problemas con el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS).  
  
## <a name="installation"></a>Installation  
 Cuando utilice el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS), tiene dos opciones:  
  
|||  
|-|-|  
|**Usar el modelo de objetos cliente** establecido en **Sí**.|**Se recomienda**. Cuando se establece en Sí, se utiliza el modelo de objetos cliente (CSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. El adaptador se instala con la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. No es necesario ningún paso de instalación adicional. **Nota:** el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación también instala automáticamente el cliente objeto modelo SharePoint redistribuible disponible en [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).|  
|**Usar el modelo de objetos cliente** establecido en **No**.|**Opción obsoleta**. Con esta opción, se utiliza el modelo de objetos cliente de servicio (SSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].<br /><br /> y se instala un servicio web en el equipo de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], que puede ser el mismo equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otro distinto.<br /><br /> Para instalar el servicio web, ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación en el [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] equipo y compruebe **adaptador de Windows SharePoint Services**. Vea [Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) de pasos de instalación específicos.|  
  
 **Usar el modelo de objetos cliente** establecido en **Sí** se recomienda. Cuando se establece en **Sí**, el servicio web no está instalado en el equipo de SharePoint. Si prefiere usar la opción de servicio web, debe establecer **utilizar modelo de objetos de cliente** a **No** en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="iis"></a>IIS  
 **Servicio web BTSharePointAdapterWS.asmx**  
  
 Cuando se instala el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] en el equipo de SharePoint, se crea el servicio web BTSharePointAdapterWS.asmx en IIS en el equipo de SharePoint. Por lo general, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SharePoint están instalados en equipos diferentes. Al instalar SharePoint, la base de datos SQL de contenido puede ser local del equipo de SharePoint o puede encontrarse en una versión de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] remota.  
  
 **Grupo de aplicaciones usa la cuenta de dominio**  
  
 Cuando BizTalk y SharePoint se encuentran en equipos distintos, el grupo de aplicaciones IIS que ejecute el servicio web BTSharePointAdapterWS.asmx debe utilizar una cuenta de dominio.. En caso de que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las bases de datos de BizTalk, [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] y las bases de datos de SharePoint de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] estén instalados en el mismo equipo, es posible utilizar una cuenta local.  
  
 **Escenario de salto doble**  
  
 Cuando el proceso implica a tres equipos ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]), se crea un escenario de salto doble que requiere autenticación Kerberos. El adaptador de SharePoint del equipo de BizTalk realiza una solicitud POST al servicio web BTSharePointAdapterWS.asmx en el equipo de SharePoint. A continuación, el equipo de SharePoint consulta su base de datos en el equipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
 Esta solicitud POST del adaptador de BizTalk debe completarse correctamente. Si sospecha que existe algún error de autenticación, revise los registros de IIS. De forma predeterminada, los registros de IIS se encuentran en c:\inetpub\logs\LogFiles\W3SVC*x*. La solicitud POST debe mostrar el código de estado 200 (operación llevada a cabo correctamente). Si se devuelve un código de estado de error, como un 401.2, seguido por un 401.1, seguido de otro 4*xx* errores y, a continuación, la autenticación puede no ser correcta.  
  
 Cuando se utilice la autenticación Kerberos, es necesario utilizar los nombres principales de servicio (SPN) y debe habilitarse la delegación.  
  
## <a name="enable-kerberos-authentication"></a>Habilitar la autenticación Kerberos  
 En un escenario de salto doble, es necesario utilizar la autenticación Kerberos y habilitar la delegación. Entre los pasos necesarios se incluyen los siguientes:  
  
1.  Habilitar **Negotiate** en el servidor IIS/SharePoint. [215383: cómo configurar IIS para que admita el protocolo Kerberos y el protocolo NTLM para la autenticación de red](http://support.microsoft.com/kb/215383) se enumeran los pasos.  
  
2.  Los nombres principales de servicio (SPN) son necesarios para las cuentas de dominio que ejecuten el servicio [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y el Grupo de aplicaciones en el equipo de IIS/SharePoint. Para crear un SPN, utilice la herramienta de línea de comandos SetSPN.exe:  
  
     [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]: [Hay disponible una actualización para Setspn.exe en Windows Server 2003](http://support.microsoft.com/kb/970536)  
  
     [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]8, [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)  
  
    > [!IMPORTANT]
    >  SetSPN requiere derechos de administrador del dominio y puede ejecutarse desde cualquier equipo del dominio.  
  
     Para devolver una lista de todos los SPN registrados en una cuenta de dominio:  
  
    ```  
    setspn.exe -l Domain\UserAccount  
    ```  
  
     Cree los SPN:  
  
    1.  Cree un SPN para el FQDN del equipo de IIS/SharePoint:  
  
        ```  
        setspn.exe -s http/IISSharePointComputerName.domain.com domain\IISApplicationPoolDomainAccount  
        ```  
  
    2.  Cree un SPN para el nombre de NETBIOS del equipo de IIS/SharePoint:  
  
        ```  
        setspn.exe -s http/IISSharePointComputerNamedomain\IISApplicationPoolDomainAccount  
        ```  
  
    3.  Cree un SPN para el FQDN del equipo de SQL Server utilizado por el equipo de IIS/SharePoint:  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName.domain.com domain\SQLServerServiceDomainAccount  
        ```  
  
    4.  Cree un SPN para el FQDN y el TCP Port del equipo de SQL Server utilizado por el equipo de IIS/SharePoint:  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName.domain.com:1433 domain\SQLServerServiceDomainAccount  
        ```  
  
    5.  Cree un SPN para el nombre de NETBIOS del equipo de SQL Server utilizado por el equipo de IIS/SharePoint:  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerNamedomain\SQLServerServiceDomainAccount  
        ```  
  
    6.  Cree un SPN para el nombre de NETBIOS, el puerto TCP del equipo de SQL Server utilizado por el equipo de IIS/SharePoint:  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName:1433 domain\SQLServerServiceDomainAccount  
        ```  
  
3.  En el controlador de dominio, vaya a **usuarios de Active Directory y equipos** y realice lo siguiente:  
  
    1.  Comprobar **confiar en este equipo para la delegación a cualquier servicio** para los siguientes equipos:  
  
        -   Servidor de SharePoint/IIS  
  
        -   SQL Server utilizado por SharePoint  
  
    2.  Comprobar **cuenta es de confianza para delegación** y desactive la opción **cuenta es importante y no se puede delegar** para las cuentas de dominio siguientes:  
  
        -   Cuenta de dominio de servicio de SQL Server  
  
        -   Cuenta de dominio del grupo de aplicaciones de IIS  
  
 Para solucionar problemas adicionales, vaya a [solucionar problemas del adaptador de Windows SharePoint Services](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Configurar SharePoint servicios de ubicación de recepción](../core/configure-sharepoint-services-receive-location.md)   
 [Configurar el puerto de envío de SharePoint Services](../core/configure-sharepoint-services-send-port.md)   
 [CSOM: Adaptador de servicios de SharePoint](../core/csom-sharepoint-services-adapter.md)