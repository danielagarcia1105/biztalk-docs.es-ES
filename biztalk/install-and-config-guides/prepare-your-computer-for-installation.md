---
title: Preparar el equipo para la instalación | Documentos de Microsoft
ms.custom: ''
ms.date: 03/15/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c2e732073ccc787cad32984720d7fac422a8cb
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710463"
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
  
-   **Windows 8.1, Windows Server 2012 y Windows Server 2012 R2**: haga clic en el botón de Windows del teclado y escriba **Windows Update**. En los resultados de la búsqueda, haga clic en **Windows Update**.  
  
 Tras instalar las actualizaciones, puede ser necesario reiniciar el equipo.  
  
##  <a name="BKMK_IIS"></a> Habilitar Internet Information Services  
 Microsoft Internet Information Services (IIS) proporciona una infraestructura de aplicación Web para muchas características de BizTalk Server, como:  
  
-   adaptador de HTTP  
  
-   Adaptador de SOAP  
  
-   Adaptador de Windows Sharepoint Services  
  
-   Cifrado de Capa de sockets seguros (SSL)  
  
-   Portal de BAM  
  
#### <a name="install-iis"></a>Instalar IIS

Pasos de instalación para la dirección URL, vea: 

[Instalar IIS (Windows 8 y Windows Server 2012)](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012)

[Instalar IIS (Windows 7 y Windows Vista)](https://docs.microsoft.com/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)


Cuando se instala IIS, además de las opciones predeterminadas, compruebe también lo siguiente:  
  
- **Herramientas de administración web**: Seleccione también:  
  
    - Compatibilidad con la administración de IIS 6:  
  
        - Consola de administración de IIS 6  
  
        - Compatibilidad con la configuración de IIS 6 y metabase de IIS  
  
    - Consola de administración de IIS  
  
- **Servicios World Wide Web**: expanda **Seguridad** y seleccione también:  
  
    - Autenticación básica  
  
    - Autenticación de Windows  

Considere también los siguientes aspectos:  
  
- **Características de .net framework 3.5**: .NET Framework 4.5 y .NET Framework 3.5 pueden usarse para desarrollar aplicaciones de .net relacionadas con BizTalk Adapter Pack. Por lo general, **características de .NET Framework 4.5** ya está instalado. Si va a usar .NET Framework 3.5 para crear aplicaciones en el equipo y, a continuación, **características de .net Framework 3.5** también se puede instalar.  
  
- **Message Queue Server**: si usa el adaptador MSMQ, puede crear un almacén MSMQ local. Para ello, seleccione **Message Queue Server**.  
  
- **Servidor SMTP**: si usa el adaptador SMTP, puede crear un servidor SMTP local. Para ello, seleccione **Servidor SMTP**.  
  
- **Windows Identity Foundation 3.5**: el adaptador de SharePoint requiere Windows Identity Foundation (WIF) cuando se usa la opción de instalación CSOM. [Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describe la opción de instalación de CSOM para el adaptador de SharePoint.    
  
 
##  <a name="BKMK_XLS"></a> Instalar Microsoft Office Excel  
  
1.  Ejecute el programa de instalación de Microsoft Office.  
  
2.  Cuando llegue a la pantalla **Tipo de instalación**, seleccione **Instalación personalizada** y haga clic en **Siguiente**.  
  
3.  En la pantalla **Instalación personalizada**, seleccione **Excel** y haga clic en **Siguiente**.  
  
4.  Seleccione **Instalar**.  
  
5.  En **Instalación finalizada**, haga clic en **Finalizar**.  
  
 **Notas**  
  
-   BizTalk Server solo es compatible con la versión de 32 bits de Microsoft Office.  
  
-   Microsoft Office Excel es necesario por actividad de supervisión económica (BAM) en BizTalk Server. El libro de BAM de Office Excel se usa para definir los procesos empresariales que desee supervisar. El libro de Excel de BAM también se usa para definir el modo en que los usuarios empresariales ven los datos que BAM recopila.  
  
-   Para cargar correctamente BAM.xla en Excel, instale la opción **Visual Basic para Aplicaciones** de **Características compartidas de Office**. De lo contrario, puede obtener el error "Este libro ha perdido su proyecto de VBA, los controles de ActiveX y todas las demás características relacionadas con la programabilidad".  
  
##  <a name="BKMK_VS"></a> Instalar Visual Studio  
  
1.  Ejecute el programa de instalación de Visual Studio como administrador.  
  
2.  Acepte el contrato de licencia y haga clic en **Siguiente**.  
  
3.  En **Características opcionales para instalar**, seleccione las opciones que necesite y haga clic en **Instalar**. BizTalk Server no necesita ninguna característica opcional.  
  
4.  En la página **Finalizar**, cierre la ventana y haga clic en **Iniciar** para abrir Visual Studio.  
  
 **Notas**  
  
-   Si instala Visual Studio antes de instalar BizTalk Server y, a continuación, actualiza a Visual Studio Team Explorer, puede que necesite reparar la instalación de BizTalk Server desde el **el Panel de Control** / **programas**  opción.  
  
-   Visual Studio instala automáticamente Microsoft SQL Server Express, que BizTalk Server no usa. Como procedimiento recomendado, desinstale Microsoft SQL Server Express.  
  
-   Las herramientas de desarrollo de BizTalk Server se basan en Visual Studio. Como mínimo, debe instalar el componente de Microsoft Visual C#® .NET de Visual Studio antes de instalar el servidor BizTalk Server**SDK y herramientas de programadores**.  
  
-   Visual Studio es *no* necesario si va a instalar BizTalk Server en un equipo de producción (en tiempo de ejecución solo), en la aplicación que no se requiere el desarrollo o depuración.  
  
-   El tiempo de ejecución de BizTalk Server requiere .NET Framework 4.5. Si se instala el adaptador o el interceptor de Windows Communication Foundation (WCF), es necesario .NET Framework 3.0.  
  
##  <a name="BKMK_SQL"></a> Instalar SQL Server  
 Instalar [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)  
  
 Instalar [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)  
  
 Instalar [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)  
  
 Cuando se instala SQL Server, seleccione las siguientes características:  
  
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
  
-   BizTalk Server admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias. No se admiten intercalaciones binarias.  
  
-   Para un rendimiento óptimo, Microsoft recomienda usar Enterprise Edition de SQL Server. Consulte [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx) (Características compatibles con las ediciones de SQL Server 2008 R2), [Características compatibles con las ediciones de SQL Server 2012](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx) o [Características compatibles con las ediciones de SQL Server 2014](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).  
  
-   Se admiten y deben instalarse los Service Packs y las actualizaciones de Windows.  
  
-   Cuando BizTalk Server y SQL Server están en equipos independientes, Coordinador de transacciones distribuidas (MS DTC) controla las transacciones entre los equipos. La característica AlwaysOn de SQL Server no admite transacciones de MSDTC. No se admite la característica AlwaysOn de SQL Server.  
  
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
>  Si no aparece una versión específica de WebSphere MQ, como MQ 5.x, entonces no es compatible con esta versión de BizTalk Server.  
  
 **Notas**  
  
-   Como práctica recomendada, instale siempre el paquete de corrección de WebSphere MQ más reciente. Consulte [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).  
  
-   Si IBM WebSphere MQ está instalado en un equipo que no tiene Windows, instale la **aplicación MQSAgent COM+** (MQSConfigWiz.exe) y **MQSeries Server para Windows** en el mismo equipo. Si IBM WebSphere MQ está instalado en un equipo con Windows, no se usan la **aplicación MQSAgent COM+** y **MQSeries Server para Windows** y, por tanto, no son necesarios.  
  
     **MQSConfigWiz.exe** se incluye en los archivos de instalación de BizTalk Server.  
  
     **MQSeries Server para Windows** no es un programa de Microsoft y debe obtenerse con el programa IBM WebSphere MQ.  
  
-   En [Adaptador de MQSeries](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) se proporciona más información sobre este adaptador, incluida la configuración de los diferentes componentes. En [BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) (BizTalk Server: adaptadores MQSeries y MQSeries Client (MQSC)) se proporciona más información sobre estos adaptadores.  
  
-   IBM WebSphere no es un producto de Microsoft y, por tanto, Microsoft no ofrece soporte técnico para este producto. Microsoft no garantiza la idoneidad de este programa. Para obtener más información acerca de IBM WebSphere MQ, incluidas las instrucciones de descarga, vea www.ibm.com.  
  
##  <a name="BKMK_BAMAlerts"></a> Alertas de BAM  
 Las alertas de BAM con SQL Server 2012 y versiones más recientes usan correo electrónico de base de datos en SQL Server. Las alertas de BAM con SQL Server 2008 R2 y versiones anteriores usan SQL Notification Services. Antes de instalar o configurar las alertas de BAM, debe configurar los servicios de notificación o correo electrónico de base de datos en SQL Server.  
  
###  <a name="BKMK_DBMail"></a> Alertas de BAM con SQL Server 2012/2014  
 Configure [Correo electrónico de base de datos de SQL Server 2012](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).  
  
 Configure [Correo electrónico de base de datos de SQL Server 2014](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).  
  
 **Notas**  
  
-   Correo electrónico de base de datos usa un servidor SMTP para enviar las alertas de BAM. Servidor SMTP puede instalarse localmente en el servidor BizTalk Server o en otro servidor IIS. En [Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md) se enumeran los pasos necesarios para instalar y configurar un servidor SMTP.  
  
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
  
-   SQL Notification Services no deben configurarse; solo se instala en el servidor BizTalk Server.  
  
##  <a name="BKMK_WIF"></a> Windows Identity Foundation  
  
|||  
|-|-|  
|Windows 8.1, Windows Server 2012 y Windows Server 2012 R2|Windows Identity Foundation se incluye con el sistema operativo como característica en **Activar o desactivar las características de Windows**.|  
|Windows Vista SP1|Descarga disponible en [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HIPERVÍNCULO "http://www.microsoft.com/download/details.aspx?id=17331".|  
  
 **Notas**  
  
-   Windows Identity Foundation (WIF) es necesario para el adaptador de SharePoint o SharePoint Online cuando se usa con el modelo de objetos de SharePoint cliente (CSOM). Concretamente:  
  
    |Opción de instalación|WIF requerido|  
    |-------------------------|------------------|  
    |Adaptador de SharePoint con CSOM|Sí|  
    |SharePoint Online con CSOM|Sí|  
    |Servicio Web del adaptador de SharePoint (en desuso)|no|  
    |Sin SharePoint|no|  
  
-   [Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) proporciona información específica sobre las opciones de instalación de SharePoint.  
  
##  <a name="BKMK_WSS"></a> Instalar y configurar Microsoft SharePoint  
 Instalar [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)  
  
 Instalar el [servicio SharePoint Online](http://technet.microsoft.com/library/jj819267.aspx)  
  
 Instalar [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)  
  
 Instalar [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)  
  
 **Notas**  
  
-   Si va a instalar SharePoint, debe hacerlo antes de continuar con los demás requisitos previos de BizTalk Server.  
  
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
  
-   Bajo determinadas condiciones de sobrecarga (como, por ejemplo, cuando los clientes obtienen acceso al servidor SQL Server desde el mismo equipo), el protocolo de memoria compartida de SQL Server puede reducir el rendimiento de BizTalk Server. Para resolver este comportamiento, puede deshabilitar el uso del protocolo de red de memoria compartida en la configuración de red de SQL Server.  
  
-   ReplaceThisText  
  
##  <a name="BKMK_LocalAdmin"></a> Unirse al grupo de administradores local  
 **Windows Server 2012** : [de Windows Server 2012: cómo agregar una cuenta a un grupo de administradores Local](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)  
  
 **Windows 8.1**: para abrir Usuarios y grupos locales en Windows 8, pulse la tecla Windows del teclado y escriba **grupos**. En la ventana Buscar, haga clic en **Configuración**. En la ventana Resultados, haga clic en **Editar usuarios y grupos locales**. Haga clic en **Grupos** y después haga doble clic en Administradores para agregar una cuenta.  
  
 **Windows 7 SP1**: haga clic en Inicio. En el cuadro de texto **Buscar**, escriba **Administración de equipos** y haga clic en él para abrirlo. Expanda **Usuarios y grupos locales**, elija **Grupos** y haga doble clic en Administradores para agregar una cuenta.  
  
 **Notas**  
  
-   Debe ser miembro del grupo Administradores local para instalar y configurar el servidor BizTalk Server.  
  
##  <a name="BKMK_AppLog"></a> Configurar el registro de eventos de la aplicación  
  
1.  Abra el **Visor de eventos**:  
  
     **Windows Server 2012** : haga clic en el botón de Windows del teclado y escriba **Visor de eventos**. En la ventana Resultados, haga clic en **Visor de eventos**.  
  
     **Windows 8.1**: pulse la tecla Windows del teclado y escriba **Visor de eventos**. En la ventana Buscar, haga clic en **Configuración**. En la ventana Resultados, haga clic en **Ver registros de eventos**.  
  
     **Windows 7 SP1**: haga clic en Inicio. En el cuadro de texto **Buscar**, escriba **Visor de eventos** y haga clic en él para abrirlo.  
  
2.  Expanda **Registros de Windows**, haga clic con el botón derecho en **Aplicación** y haga clic en **Propiedades**. En **Propiedades del registro**:  
  
    -   Para determinar el espacio disponible, compare las propiedades **Tamaño del registro** y **Máximo tamaño de registro**.  
  
    -   Para proporcionar más espacio, especifique un número más alto en **Máximo tamaño de registro**.  
  
    -   Para habilitar la sobrescritura de los eventos antiguos cuando se llene el registro, seleccione **Sobrescribir eventos cuando sea necesario**.  
  
    -   Para borrar los eventos del registro, seleccione **Vaciar registro**.  
  
3.  Haga clic en **Aceptar** para cerrar el **Visor de eventos**.  
  
 **Notas**  
  
-   El programa de instalación de BizTalk Server mantiene un registro de eventos en el registro de eventos de aplicación. En función de las características de BizTalk Server instaladas, la cantidad de espacio necesaria en el registro puede superar su límite. Si el registro de eventos de aplicación se queda sin espacio durante la instalación de BizTalk Server, se produce un error en la instalación. Este error se puede evitar cambiando la configuración del registro de eventos de aplicación.  
  
## <a name="next"></a>Siguiente  
 [Elegir características y componentes de BizTalk Server](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [Apéndice A: Instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md)   
 [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [Apéndice C: Archivos CAB redistribuibles](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
