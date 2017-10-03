---
title: "Preparar el equipo para la instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 2016-03-15
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a493c1a0ef38e9be5e229ff82f8773211adfe765
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-your-computer-for-installation"></a>Preparar el equipo para la instalación
En este tema se muestran los pasos necesarios para preparar el equipo, mediante la instalación y configuración de todos los requisitos previos de software, y para crear cuentas y configurar permisos.  

> [!TIP] 
> Un MVP de integración ha preparado una guía paso a paso muy detallada para instalar los requisitos previos y BizTalk Server: [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/) (Instalación y configuración de BizTalk 2013, parte 1).  
> 
> Microsoft no recomienda algunos pasos, como deshabilitar el Control de acceso de usuarios (UAC) o el Firewall de Windows. 
  
> [!IMPORTANT]
>  Complete estas tareas en el orden que se indica.  
  
##  <a name="BKMK_InstUpdates"></a> Instalar actualizaciones de Windows  
  
-   **Windows 7**: haga clic en Inicio. En el cuadro de texto **Buscar**, escriba **Windows Update**.  
  
-   **Windows 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] y [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2**: pulse la tecla Windows del teclado y escriba **Windows Update**. En los resultados de la búsqueda, haga clic en **Windows Update**.  
  
 Tras instalar las actualizaciones, puede ser necesario reiniciar el equipo.  
  
##  <a name="BKMK_IIS"></a> Habilitar Internet Information Services  
 Microsoft Internet Information Services (IIS) proporciona una infraestructura de aplicación web para numerosas características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], incluidas:  
  
-   adaptador de HTTP  
  
-   Adaptador de SOAP  
  
-   Adaptador de Windows Sharepoint Services  
  
-   Cifrado de Capa de sockets seguros (SSL)  
  
-   Portal de BAM  
  
#### <a name="install-iis-75-on-windows-7-sp1"></a>Instalar IIS 7.5 en Windows 7 SP1  
  
1.  Seleccione **Inicio**. En el cuadro de texto **Buscar**, escriba **Programas y características** y ábralo.  
  
2.  Seleccione **Activar o desactivar las características de Windows**.  
  
3.  Seleccione **Internet Information Services** y expanda **Internet Information Services**. Además de las opciones predeterminadas, seleccione las siguientes:  
  
    -   **Herramientas de administración web**: Seleccione también:  
  
        -   Compatibilidad con la administración de IIS 6:  
  
            -   Consola de administración de IIS 6  
  
            -   Compatibilidad con la configuración de IIS 6 y metabase de IIS  
  
        -   Consola de administración de IIS  
  
    -   **Servicios World Wide Web**: expanda **Seguridad** y seleccione también:  
  
        -   Autenticación básica  
  
        -   Autenticación de Windows  
  
4.  Seleccione **Aceptar**. Cuando termine, haga clic en **Cerrar**.  
  
 En [http://go.microsoft.com/fwlink/p/?LinkId=257033](http://go.microsoft.com/fwlink/p/?LinkId=257033) se proporcionan también los pasos para habilitar IIS en Windows 7.  
  
#### <a name="install-iis-80-on-windows-8"></a>Instalar IIS 8.0 en Windows 8  
  
1.  Presione la tecla Windows del teclado. Escriba **Programas y características** y seleccione **Configuración**. En la ventana Resultados, seleccione **Programas y características**.  
  
2.  Seleccione **Activar o desactivar las características de Windows**.  
  
3.  Seleccione **Internet Information Services** y expanda **Internet Information Services**. Además de las opciones predeterminadas, seleccione las siguientes:  
  
    -   **Herramientas de administración web**: Seleccione también:  
  
        -   Compatibilidad con la administración de IIS 6:  
  
            -   Consola de administración de IIS 6  
  
            -   Compatibilidad con la configuración de IIS 6 y metabase de IIS  
  
        -   Consola de administración de IIS  
  
    -   **Servicios World Wide Web**: expanda **Seguridad** y seleccione también:  
  
        -   Autenticación básica  
  
        -   Autenticación de Windows  
  
4.  Haga clic en **Aceptar**. Cuando termine, haga clic en **Cerrar**.  
  
 En [http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) se proporcionan también los pasos para habilitar IIS en Windows 8.  
  
#### <a name="install-iis-80-on-windows-server-2012"></a>Instalar IIS 8.0 en Windows Server 2012  
  
1.  Abra **Administrador del servidor** y haga clic en **Panel** en el panel de la izquierda.  
  
2.  Haga clic en **Agregar roles y características**. También se puede abrir **Agregar roles y características** desde el menú **Administrar** de la esquina superior derecha.  
  
3.  En la ventana **Antes de comenzar**, haga clic en **Siguiente**.  
  
4.  En la ventana **Tipo de instalación**, haga clic en **Instalación basada en características o en roles** y, después, en **Siguiente**.  
  
5.  En la ventana **Selección de servidor**, haga clic en **Seleccionar un servidor del grupo de servidores**, elija el servidor deseado y haga clic en **Siguiente**.  
  
     En la ventana **Selección del servidor** se muestra una lista de los servidores que se han agregado con la opción **Agregar servidor** en el **Administrador del servidor**. De forma predeterminada, se selecciona el servidor local. En [Adición de servidores al Administrador del servidor](http://go.microsoft.com/fwlink/p/?LinkID=241353) se proporcionan los pasos para usar la opción **Agregar servidor** en [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].  
  
6.  En la ventana **Roles de servidor**, haga clic en **Servidor web (IIS)**. Si se le pide, haga clic en **Agregar características** y, después, en **Siguiente**.  
  
7.  En la ventana **Características**, deje habilitadas las opciones predeterminadas y considere también lo siguiente:  
  
     **Características de .NET Framework 3.5**: [!INCLUDE[dotnet45](../includes/dotnet45-md.md)] y [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] se pueden usar para desarrollar aplicaciones .NET con [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Normalmente, **Características de [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]** está ya instalado. Si va a usar [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] para crear aplicaciones en este equipo, puede instalar también **Características de .NET Framework 3.5**.  
  
     **Message Queue Server**: si usa el adaptador MSMQ, puede crear un almacén MSMQ local. Para ello, seleccione **Message Queue Server**.  
  
     **Servidor SMTP**: si usa el adaptador SMTP, puede crear un servidor SMTP local. Para ello, seleccione **Servidor SMTP**.  
  
     **Windows Identity Foundation 3.5**: el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] requiere Windows Identity Foundation (WIF) cuando se usa la opción de instalación CSOM. En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se describe la opción de instalación CSOM para el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)].  
  
     Haga clic en **Siguiente**.  
  
8.  En la ventana **Rol de servidor web (IIS)**, haga clic en **Siguiente**.  
  
9. En la ventana **Servicios de rol** (en **Rol de servidor web (IIS)**), haga clic en las siguientes opciones:  
  
     **Seguridad**: además de las opciones predeterminadas, haga clic en:  
  
    -   Autenticación básica  
  
    -   Autenticación de Windows  
  
     **Desarrollo de aplicaciones**: las opciones predeterminadas son suficientes para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si hospeda otras aplicaciones basadas en IIS en este equipo, seleccione los roles necesarios.  
  
     **Herramientas de administración**: además de las opciones predeterminadas, haga clic en:  
  
    -   Consola de administración de IIS  
  
    -   Compatibilidad con la administración de IIS 6:  
  
        -   Compatibilidad con la metabase de IIS 6  
  
        -   Consola de administración de IIS 6  
  
     Haga clic en **Siguiente**.  
  
10. En la ventana **Confirmación**, haga clic en **Instalar**. Cuando termine, haga clic en **Cerrar**.  
  
 En [http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) se proporcionan también los pasos para habilitar IIS en [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].  
  
##  <a name="BKMK_XLS"></a> Instalar Microsoft Office Excel  
  
1.  Ejecute el programa de instalación de Microsoft Office.  
  
2.  Cuando llegue a la pantalla **Tipo de instalación**, seleccione **Instalación personalizada** y haga clic en **Siguiente**.  
  
3.  En la pantalla **Instalación personalizada**, seleccione **Excel** y haga clic en **Siguiente**.  
  
4.  Elija **Instalar**.  
  
5.  En **Instalación finalizada**, haga clic en **Finalizar**.  
  
 **Notas**  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo es compatible con la versión de 32 bits de Microsoft Office.  
  
-   Microsoft Office Excel es necesario para la Supervisión de la actividad económica (BAM) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El libro de BAM de Office Excel se usa para definir los procesos empresariales que desee supervisar. El libro de Excel de BAM también se usa para definir el modo en que los usuarios empresariales ven los datos que BAM recopila.  
  
-   Para cargar correctamente BAM.xla en Excel, instale la opción **Visual Basic para Aplicaciones** de **Características compartidas de Office**. De lo contrario, puede obtener el error "Este libro ha perdido su proyecto de VBA, los controles de ActiveX y todas las demás características relacionadas con la programabilidad".  
  
##  <a name="BKMK_VS"></a> Instalar Visual Studio  
  
1.  Ejecute el programa de instalación de Visual Studio como administrador.  
  
2.  Acepte el contrato de licencia y haga clic en **Siguiente**.  
  
3.  En **Características opcionales para instalar**, seleccione las opciones que necesite y haga clic en **Instalar**. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no necesita ninguna característica opcional.  
  
4.  En la página **Finalizar**, cierre la ventana y haga clic en **Iniciar** para abrir Visual Studio.  
  
 **Notas**  
  
-   Si instala Visual Studio antes de instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y después actualiza a Visual Studio Team Explorer, puede que sea necesario reparar la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde la opción **Panel de control** / **Programas**.  
  
-   Visual Studio instala automáticamente Microsoft SQL Server Express, que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no usa. Como procedimiento recomendado, desinstale Microsoft SQL Server Express.  
  
-   Las herramientas de programadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] están basadas en Visual Studio. Como mínimo, debe instalar el componente Microsoft Visual C#® .NET de Visual Studio antes de instalar el **SDK y herramientas de desarrollo** de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Visual Studio *no* es necesario si va a instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo de producción (solo en tiempo de ejecución), en el que no es necesario ningún trabajo de desarrollo o depuración de aplicaciones.  
  
-   El runtime de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] requiere [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]. Si se instala el adaptador o el interceptor de Windows Communication Foundation (WCF), es necesario .NET Framework 3.0.  
  
##  <a name="BKMK_SQL"></a> Instalar SQL Server  
 Instalar [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)  
  
 Instalar [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)  
  
 Instalar [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)  
  
 Cuando instale [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], seleccione las siguientes características:  
  
-   Servicios de Motor de base de datos  
  
    -   Replicación de SQL Server  
  
    -   Búsqueda de texto completo  
  
-   Analysis Services  
  
-   Reporting Services  
  
-   Características compartidas  
  
    -   SQL Server Data Tools (SQL Server 2014/SQL Server 2012) o Business Intelligence Development Studio (SQL Server 2008 R2)  
  
         [Descargar las herramientas de datos SQL Server 2014](http://www.microsoft.com/download/details.aspx?id=42313)  
  
    -   Conectividad con las herramientas de cliente  
  
    -   Integration Services  
  
    -   Herramientas de administración: básicas  
  
        -   Herramientas de administración - Completa  
  
 **Notas**  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias. No se admiten intercalaciones binarias.  
  
-   Para un rendimiento óptimo, Microsoft recomienda usar Enterprise Edition de SQL Server. Consulte [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx) (Características compatibles con las ediciones de SQL Server 2008 R2), [Características compatibles con las ediciones de SQL Server 2012](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx) o [Características compatibles con las ediciones de SQL Server 2014](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).  
  
-   Se admiten y deben instalarse los Service Packs y las actualizaciones de Windows.  
  
-   Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] están en equipos diferentes, el Coordinador de transacciones distribuidas (MS DTC) controla las transacciones entre los equipos. La característica AlwaysOn de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] no admite transacciones MSDTC. No se admite la característica AlwaysOn de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
##  <a name="BKMK_MQSeries"></a> Instalar los requisitos previos de MQSeries  
 **Adaptador de MQSeries**: se instala de forma automática con la instalación de BizTalk Server.  
  
 **Adaptador de MQSeries Client (MQSC)**:  
  
1.  Ejecute la instalación de Host Integration Server (HIS).  
  
2.  En Instalación de componentes, expanda **BizTalk Adapters** (Adaptadores de BizTalk).  
  
3.  Seleccione **BizTalk Adapter for WebSphere MQ (Client-Based)** (Adaptador de BizTalk para WebSphere MQ (basado en cliente)).  
  
 **Versiones de IBM WebSphere MQ admitidas**:  
  
-   IBM WebSphere MQ 6.0.2.12 y posterior  
  
-   IBM WebSphere MQ 7.0.1.9 y posterior  
  
-   IBM WebSphere MQ 7.1.0.5 y versiones posteriores  
  
-   IBM WebSphere MQ 7.5.0.3 y versiones posteriores  
  
-   IBM WebSphere MQ 8 (limitado al tiempo de ejecución, sin API de administración)  
  
     Se incluye compatibilidad con la versión 8 de MQ con [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).  
  
> [!NOTE]
>  Si no aparece una versión específica de WebSphere MQ, como MQ 5.x, entonces no es compatible con esta versión [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 **Notas**  
  
-   Como práctica recomendada, instale siempre el paquete de corrección de WebSphere MQ más reciente. Consulte [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).  
  
-   Si IBM WebSphere MQ está instalado en un equipo que no tiene Windows, instale la **aplicación MQSAgent COM+** (MQSConfigWiz.exe) y **MQSeries Server para Windows** en el mismo equipo. Si IBM WebSphere MQ está instalado en un equipo con Windows, no se usan la **aplicación MQSAgent COM+** y **MQSeries Server para Windows** y, por tanto, no son necesarios.  
  
     **MQSConfigWiz.exe** se incluye en los archivos de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
     **MQSeries Server para Windows** no es un programa de Microsoft y debe obtenerse con el programa IBM WebSphere MQ.  
  
-   En [Adaptador de MQSeries](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) se proporciona más información sobre este adaptador, incluida la configuración de los diferentes componentes. En [BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) (BizTalk Server: adaptadores MQSeries y MQSeries Client (MQSC)) se proporciona más información sobre estos adaptadores.  
  
-   IBM WebSphere no es un producto de Microsoft y, por tanto, Microsoft no ofrece soporte técnico para este producto. Microsoft no garantiza la idoneidad de este programa. Para obtener más información acerca de IBM WebSphere MQ, incluidas las instrucciones de descarga, vea www.ibm.com.  
  
##  <a name="BKMK_BAMAlerts"></a> Alertas de BAM  
 Las alertas de BAM con [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] o [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] utilizan Correo electrónico de base de datos en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Las alertas de BAM con [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] usan SQL Notification Services. Antes de instalar o configurar alertas de BAM, debe configurar Notification Services o Correo electrónico de base de datos en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
###  <a name="BKMK_DBMail"></a> Alertas de BAM con SQL Server 2012/2014  
 Configure [Correo electrónico de base de datos de SQL Server 2012](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).  
  
 Configure [Correo electrónico de base de datos de SQL Server 2014](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).  
  
 **Notas**  
  
-   Correo electrónico de base de datos usa un servidor SMTP para enviar las alertas de BAM. El servidor SMTP se puede instalar en modo local en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otro servidor IIS. En [Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md) se enumeran los pasos necesarios para instalar y configurar un servidor SMTP.  
  
###  <a name="BKMK_SSNS"></a> Alertas de BAM con SQL Server 2008 R2: instalar SQL Server 2005 Notification Services  
  
1.  Vaya a [Feature Pack para Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).  
  
2.  Descargue e instale el paquete de plataforma adecuado para los siguientes componentes:  
  
     **Cliente nativo de Microsoft SQL Server**  
  
    -   HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" del paquete X86 (sqlncli.msi)  
  
    -   HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" del paquete X64 (sqlncli_x64.msi)  
  
     **Colección de objetos de administración de Microsoft SQL Server 2005**  
  
    -   HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" del paquete X86 (SQLServer2005_XMO.msi)  
  
    -   HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" del paquete X64 (SQLServer2005_XMO_x64.msi)  
  
     **Componentes de cliente de Microsoft SQL Server 2005 Notification Services**  
  
    -   HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" del paquete X86 (SQLServer2005_NS.msi)  
  
    -   HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" del paquete X64 (SQLServer2005_NS_x64.msi)  
  
 **Notas**  
  
-   No es necesario configurar SQL Notification Services, solo instalarlo en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##  <a name="BKMK_WIF"></a> Windows Identity Foundation  
  
|||  
|-|-|  
|[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] y [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2|Windows Identity Foundation se incluye con el sistema operativo como característica en **Activar o desactivar las características de Windows**.|  
|[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] SP1|Descarga disponible en [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HIPERVÍNCULO "http://www.microsoft.com/download/details.aspx?id=17331".|  
  
 **Notas**  
  
-   SharePoint Online o el adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] requieren Windows Identity Foundation (WIF) cuando se utilizan con el modelo de objetos de cliente (CSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. Concretamente:  
  
    |Opción de instalación|WIF requerido|  
    |-------------------------|------------------|  
    |Adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] con CSOM|Sí|  
    |SharePoint Online con CSOM|Sí|  
    |Servicio web del adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (obsoleto)|No|  
    |Sin SharePoint|No|  
  
-   En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se proporciona información específica sobre las opciones de instalación de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].  
  
##  <a name="BKMK_WSS"></a> Instalar y configurar Microsoft SharePoint  
 Instalar [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)  
  
 Instalar el [servicio SharePoint Online](http://technet.microsoft.com/library/jj819267.aspx)  
  
 Instalar [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)  
  
 Instalar [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)  
  
 **Notas**  
  
-   Si instala SharePoint, debe hacerlo antes de continuar con el resto de los requisitos previos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   La instalación y configuración de SharePoint consiste en los siguientes procedimientos:  
  
    -   Instalar SharePoint  
  
    -   Configurar SharePoint  
  
    -   Extender el sitio web predeterminado como un servidor virtual  
  
-   En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se describen las opciones de instalación del adaptador de SharePoint para BizTalk Server.  
  
-   Cuando se use el adaptador de SharePoint, se recomienda instalar la nueva opción CSOM en lugar del servicio web de SharePoint, que se describe en [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).  
  
##  <a name="BKMK_SharedMem"></a> Deshabilitar el protocolo de memoria compartida  
  
1.  Abra el **Administrador de configuración de SQL Server**.  
  
2.  En **Administrador de configuración de SQL Server**, expanda **Configuración de red de SQL Server** y seleccione **Protocolos de MSSQLSERVER**.  
  
3.  Haga clic con el botón derecho en **Memoria compartida** y seleccione **Deshabilitar**.  
  
4.  Seleccione **Servicios de SQL Server**, haga clic con el botón derecho en **SQL Server (MSSQLSERVER)** y elija **Detener**. Después de detener el servicio, haga clic de nuevo con el botón derecho en **SQL Server (MSSQLSERVER)** y elija **Iniciar**.  
  
5.  Cierre el **Administrador de configuración de SQL Server**.  
  
 **Notas**  
  
-   En ciertas condiciones de sobrecarga (como cuando los clientes tienen acceso a SQL Server desde el mismo equipo), el protocolo de memoria compartida de SQL Server puede reducir el rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para resolver este comportamiento, puede deshabilitar el uso del protocolo de red de memoria compartida en la configuración de red de SQL Server.  
  
-   ReplaceThisText  
  
##  <a name="BKMK_LocalAdmin"></a> Unirse al grupo de administradores local  
 **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx) (Windows Server 2012: cómo agregar una cuenta a un grupo de administradores local)  
  
 **Windows 8.1**: para abrir Usuarios y grupos locales en Windows 8, pulse la tecla Windows del teclado y escriba **grupos**. En la ventana Buscar, haga clic en **Configuración**. En la ventana Resultados, haga clic en **Editar usuarios y grupos locales**. Haga clic en **Grupos** y después haga doble clic en Administradores para agregar una cuenta.  
  
 **Windows 7 SP1**: haga clic en Inicio. En el cuadro de texto **Buscar**, escriba **Administración de equipos** y haga clic en él para abrirlo. Expanda **Usuarios y grupos locales**, elija **Grupos** y haga doble clic en Administradores para agregar una cuenta.  
  
 **Notas**  
  
-   Debe ser miembro del grupo de administradores local para instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##  <a name="BKMK_AppLog"></a> Configurar el registro de eventos de la aplicación  
  
1.  Abra el **Visor de eventos**:  
  
     **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: pulse la tecla Windows del teclado y escriba **Visor de eventos**. En la ventana Resultados, haga clic en **Visor de eventos**.  
  
     **Windows 8.1**: pulse la tecla Windows del teclado y escriba **Visor de eventos**. En la ventana Buscar, haga clic en **Configuración**. En la ventana Resultados, haga clic en **Ver registros de eventos**.  
  
     **Windows 7 SP1**: haga clic en Inicio. En el cuadro de texto **Buscar**, escriba **Visor de eventos** y haga clic en él para abrirlo.  
  
2.  Expanda **Registros de Windows**, haga clic con el botón derecho en **Aplicación** y haga clic en **Propiedades**. En **Propiedades del registro**:  
  
    -   Para determinar el espacio disponible, compare las propiedades **Tamaño del registro** y **Máximo tamaño de registro**.  
  
    -   Para proporcionar más espacio, especifique un número más alto en **Máximo tamaño de registro**.  
  
    -   Para habilitar la sobrescritura de los eventos antiguos cuando se llene el registro, seleccione **Sobrescribir eventos cuando sea necesario**.  
  
    -   Para borrar los eventos del registro, seleccione **Vaciar registro**.  
  
3.  Haga clic en **Aceptar** para cerrar el **Visor de eventos**.  
  
 **Notas**  
  
-   La instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mantiene un registro de eventos en el registro de eventos de aplicación. Según las características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instaladas, la cantidad de espacio necesario en el registro puede superar su límite. Si se agota el espacio del registro de eventos de aplicaciones durante la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ésta no se llevará a cabo. Este error se puede evitar cambiando la configuración del registro de eventos de aplicación.  
  
## <a name="next"></a>Siguiente  
 [Elegir características y componentes de BizTalk Server](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a>Ver también  
 [Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [Apéndice A: Instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md)   
 [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [Apéndice C: Archivos CAB redistribuibles](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
