---
title: Instalar BizTalk adaptador Pack 2013 R2 y 2013 | Documentos de Microsoft
description: Requisitos previos y los pasos para instalar BAP 2013 R2 y 2013 BAP incluidos con BizTalk Server
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9980953a-8d38-476f-af38-4f4214ba61f2
caps.latest.revision: 107
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8bc1ebbdaf2973f4749da6c0832d49204588b6c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25968034"
---
# <a name="install-biztalk-adapter-pack-2013-r2-and-2013"></a>Instalar 2013 y BizTalk adaptador Pack 2013 R2
Este documento enumeran los requisitos de software y los pasos para instalar Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] (BAP) incluidos con BizTalk Server 2013 o [!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)].  
  
## <a name="change-log"></a>Registro de cambios  
  
|Date|Cambiar|  
|---|---|  
|Marzo de 2016|En **después de instalar...** , agregar los pasos para configurar el adaptador de base de datos de Oracle para que use la versión más reciente de Oracle.DataAccess.dll.|  
  
<a name="BKMK_Prereqs"></a>   
## <a name="software-prerequisites"></a>Requisitos previos de software  
 El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] pueden consumir desde:  
  
-   Una aplicación .NET  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Una interfaz de ADO  
  
-   Un portal de Microsoft SharePoint  
  
 En función de cómo usar los adaptadores, que varía según el software necesario.  
  
### <a name="prerequisites-when-using-a-net-application"></a>Requisitos previos al usar una aplicación .NET  
Cuando se usa una aplicación .NET para consumir los adaptadores, se requiere el software siguiente en el equipo de desarrollo (el equipo donde va a crear la aplicación. NET). Instalar el software en el orden indicado.
  
|BizTalk adaptador Pack 2013 R2|BizTalk Adapter Pack 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|Los clientes de aplicaciones de empresa y el software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).|Los clientes de aplicaciones de empresa y el software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).|  

### <a name="prerequisites-when-using-a-biztalk-server"></a>Requisitos previos cuando se usa un servidor BizTalk Server  
Al utilizar un servidor de BizTalk para consumir los adaptadores, se requiere el software siguiente en el servidor BizTalk Server. Instalar el software en el orden indicado.
  
|BizTalk adaptador Pack 2013 R2|BizTalk Adapter Pack 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> Instalar el [!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]. Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> Instalar el [!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]. Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].|  
|BizTalk Server 2013 R2|BizTalk Server 2013|  
|Los clientes de aplicaciones de empresa y el software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).|Los clientes de aplicaciones de empresa y el software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).|  

### <a name="prerequisites-when-using-ado"></a>Requisitos previos al usar ADO  
 El **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** y **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** incluir una capa de ADO (*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* y *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]*). Esta capa de ADO puede utilizarse para escribir un cliente ADO.NET para conectarse a un sistema SAP o el sistema Siebel. También puede utilizar la capa de ADO con SQL Server Integration Services (SSIS) para importar y exportar datos de la aplicación de LOB y SQL Server Reporting Services (SSRS) para generar informes para presentar datos de los sistemas LOB.  
  
> [!NOTE]
>  Usar el proveedor de ADO con SSRS solo se admite para la *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]*.  
  
Se requiere el software siguiente en el equipo que usa la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] con una interfaz de ADO. Instalar el software en el orden indicado.
  
|BizTalk adaptador Pack 2013 R2|BizTalk Adapter Pack 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)], [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]|[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]|  
|Los clientes de aplicaciones de empresa y el software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).|Los clientes de aplicaciones de empresa y el software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).|  

### <a name="prerequisites-when-using-microsoft-sharepoint"></a>Requisitos previos al usar Microsoft SharePoint  
 El objetivo del uso de los adaptadores con Microsoft SharePoint es mostrar datos de una aplicación de LOB en un portal de SharePoint.  
  
Una instalación típica con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] y SharePoint puede ser un único equipo o utiliza equipos diferentes para distintas tareas. En la tabla siguiente se resume los requisitos previos de software para cada equipo. Si está utilizando un único equipo, es necesario todo el software en ese equipo. Instalar el software en el orden indicado.  
  
|Equipo donde se ejecuta el Asistente de desarrollo del servicio de adaptador de WCF|Equipo que hospeda el servicio WCF|Equipo donde se puede utilizar el Diseñador de SharePoint para definir los tipos de contenido externos|Equipo donde usa SharePoint para presentar la información de una aplicación de LOB|  
|---|---|---|---|  
|**BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li> Visual Studio 2013</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>Clientes de aplicaciones de empresa respectivos y software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).</li></ul> **BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>Visual Studio 2012</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>Clientes de aplicaciones de empresa respectivos y software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).</li></ul>|**BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>Clientes de aplicaciones de empresa respectivos y software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).</li><li>Versión de Internet Information Services (IIS) que se incluye con el sistema operativo. KB 224609 enumera las versiones.</li></ul>**BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>Clientes de aplicaciones de empresa respectivos y software asociado. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).</li><li>Versión de Internet Information Services (IIS) que se incluye con el sistema operativo. KB 224609 enumera las versiones.</li></ul>|Kit de desarrollo de Software (SDK) de Microsoft Office SharePoint Server|Actualización de la infraestructura de servidores de Microsoft Office. Descargar en [ http://go.microsoft.com/fwlink/?LinkId=128344 ](http://go.microsoft.com/fwlink/?LinkId=128344).|  
  
<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>Versiones de la aplicación de enterprise admitidos  

Para ver las versiones específicas de sistema LOB que son compatibles con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], consulte  **[sistemas Supported Line-of-Business (LOB)](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**. 

Esta sección enumera ninguna información adicional para cada adaptador, como los archivos DLL de cliente necesario para cada adaptador.  
  
### <a name="oracle-database-adapter"></a>Adaptador para base de datos de Oracle  
  
-   Opcional: Si utiliza transacciones distribuidas con la base de datos de Oracle, instale **Oracle Services para Microsoft Transaction Server** (forma parte de la instalación de cliente de Oracle) en el equipo que ejecuta el cliente de adaptador.  
  
-   Para que la aplicación para que funcione con la versión más reciente de ODP.NET, instale el **directiva dll** y registrar los archivos DLL en la GAC. Vea [proveedor de datos de Oracle para .NET preguntas más frecuentes sobre](http://www.oracle.com/technetwork/database/windows/faq-093106.html).  

### <a name="oracle-e-business-adapter"></a>Adaptador para Oracle E-Business  
  
-   Opcional: Para usar transacciones distribuidas con la base de datos de Oracle, instale **Oracle Services para Microsoft Transaction Server** (forma parte de la instalación de cliente de Oracle) en el equipo que ejecuta el cliente de adaptador.  
  
-   Para que la aplicación para que funcione con la versión más reciente de ODP.NET, instale el **directiva dll** y registrar los archivos DLL en la GAC. Vea [proveedor de datos de Oracle para .NET preguntas más frecuentes sobre](http://www.oracle.com/technetwork/database/windows/faq-093106.html).  
  
### <a name="sap-adapter"></a>SAP adapter  
  
-   El [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] requiere la versión Unicode de RFC SDK independientemente de si el sistema SAP es Unicode o no Unicode.  
  
-   **Controladores necesarios**: en la tabla siguiente se enumera los archivos DLL necesarias para la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para comunicarse con el sistema SAP. La mayoría de los paquetes que contengan dichos archivos DLL debe descargarse desde el catálogo de soluciones de servicio de SAP. Para obtener descargas de Marketplace de servicio de SAP: 
  
    1.  Instalar al administrador de descargas disponibles desde el catálogo de soluciones de servicio de SAP.  
  
    2.  Configurar el Administrador de descargas con sus credenciales para el catálogo de soluciones de servicio de SAP.  
  
    3.  Autorización por el administrador SAP en su organización para descargar el software desde el sitio Web de servicio SAP. Esto es necesario porque el acceso al centro de distribución de Software de SAP está restringido por un objeto de autorización 'Descargar Software'. Esto garantiza que el software se descarga solo por usuarios autorizados.  
  
    4.  Instalar el programa SAPCAR, que es necesario para extraer los archivos de los paquetes que descargó desde el catálogo de soluciones de servicio de SAP. SAPCAR también está disponible en el catálogo de soluciones de servicio de SAP.  
  
     Para la versión de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], debe tener las versiones respectivas de 32 bits y 64 bits de estos archivos DLL.  
  
    -   En un equipo de 32 bits, la versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.  
  
    -   En un equipo de 64 bits, la versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\SysWow64. La versión de 64 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.  
  
    |Versión del cliente SAP|Controladores necesarios|  
    |------------------------|----------------------|  
    |6.4|**BizTalk Adapter Pack 2013 solo**<br /><br /> - **SAP RFC SDK 6.40 UNICODE**. Esta opción está disponible como parte de SNOTE<sup> * </sup> 27517. Las instrucciones para descargar el SDK están disponibles en [ http://go.microsoft.com/fwlink/?LinkId=94691 ](http://go.microsoft.com/fwlink/?LinkId=94691). Después de haber descargado y extraído el SDK, copie todos los archivos DLL de las carpetas \rfcsdk\bin y \rfcsdk\lib a la ubicación pertinente mencionada anterior a esta tabla. <br /> <br /> -Dll están disponibles desde SAP como parte de **R3DLLINST.zip**. Esto contiene archivos DLL de tiempo de ejecución de Microsoft y se puede descargar desde el sitio SAP. Vea SNOTE<sup> * </sup> 684106 para obtener más información. Puede descargar el archivo .zip de [ http://go.microsoft.com/fwlink/?LinkId=94693 ](http://go.microsoft.com/fwlink/?LinkId=94693). Este vínculo tiene una opción de "Datos adjuntos" desde donde puede descargar el paquete.<br /><br /> -Si usa las comunicaciones de red segura de SAP (SNC) para conectarse a un sistema SAP, también debe tener los archivos DLL pertinentes de SAP. Estos archivos DLL son diferentes para plataformas de 32 bits y 64 bits y están disponibles con SNOTE<sup> * </sup> 352295. Puede descargar los archivos DLL de [ http://go.microsoft.com/fwlink/?LinkId=104032 ](http://go.microsoft.com/fwlink/?LinkId=104032). Este vínculo tiene una opción de "Datos adjuntos" desde donde puede descargar el paquete. Los nombres de los archivos DLL son:<br /><br /> - **Para 32 bits**: gsskrb5.dll, gssntlm.dll<br /><br /> -  **Para 64 bits x86**: gx64krb5.dll, gx64ntlm.dll|  
    |7.0|- **SAP RFC SDK 7.00 UNICODE**. Esta opción está disponible como parte de SNOTE<sup> * </sup> 27517. Las instrucciones para descargar el SDK están disponibles en [ http://go.microsoft.com/fwlink/?LinkId=94691 ](http://go.microsoft.com/fwlink/?LinkId=94691). Después de haber descargado y extraído el SDK, copie todos los archivos DLL de las carpetas \rfcsdk\bin y \rfcsdk\lib y a la ubicación pertinente mencionado anterior a esta tabla. <br /> <br /> -Dll están disponibles desde SAP como parte de **R3DLLINST.zip**. Esto contiene archivos DLL de tiempo de ejecución de Microsoft y se puede descargar desde el sitio SAP. Vea SNOTE<sup> * </sup> 684106 para obtener más información. Puede descargar el archivo .zip de [ http://go.microsoft.com/fwlink/?LinkId=94693 ](http://go.microsoft.com/fwlink/?LinkId=94693). Este vínculo tiene una opción de "Datos adjuntos" desde donde puede descargar el paquete.<br /><br /> -Si usa las comunicaciones de red segura de SAP (SNC) para conectarse a un sistema SAP, también debe tener los archivos DLL pertinentes de SAP. Estos archivos DLL son diferentes para plataformas de 32 bits y 64 bits y están disponibles con SNOTE<sup> * </sup> 352295. Puede descargar los archivos DLL de [ http://go.microsoft.com/fwlink/?LinkId=104032 ](http://go.microsoft.com/fwlink/?LinkId=104032). Este vínculo tiene una opción de "Datos adjuntos" desde donde puede descargar el paquete. Los nombres de los archivos DLL son:<br /><br /> - **Para 32 bits**: gsskrb5.dll, gssntlm.dll<br /><br /> - **Para 64 bits x86**: gx64krb5.dll, gx64ntlm.dll|  
    |7.1|- **SAP RFC SDK 7.10 UNICODE**. Esta opción está disponible como parte de SNOTE<sup> * </sup> 27517. Las instrucciones para descargar el SDK están disponibles en [ http://go.microsoft.com/fwlink/?LinkId=94691 ](http://go.microsoft.com/fwlink/?LinkId=94691). Después de haber descargado y extraído el SDK, copie todos los archivos DLL de las carpetas \rfcsdk\bin y \rfcsdk\lib a la ubicación pertinente mencionada anterior a esta tabla. <br /> <br /> -Dll están disponibles desde SAP como parte de **R3DLLINST.zip**. Esto contiene archivos DLL de tiempo de ejecución de Microsoft y se puede descargar desde el sitio SAP. Vea SNOTE<sup> * </sup> 684106 para obtener más información. Puede descargar el archivo .zip de [ http://go.microsoft.com/fwlink/?LinkId=94693 ](http://go.microsoft.com/fwlink/?LinkId=94693). Este vínculo tiene una opción de "Datos adjuntos" desde donde puede descargar el paquete.<br /><br /> -Microsoft Visual C++ DLL en tiempo de ejecución necesarias para el cliente de SAP 7.1 están disponibles en los siguientes vínculos:<br /><br /> - **Para el cliente de SAP 7.1 de 32 bits**: Vcredist_x86.exe de [ http://go.microsoft.com/fwlink/?LinkId=107086 ](http://go.microsoft.com/fwlink/?LinkId=107086).<br /><br /> -                                 **Para el cliente de SAP 7.1 de 64 bits**: Vcredist_x64.exe desde [ http://go.microsoft.com/fwlink/?LinkId=107087 ](http://go.microsoft.com/fwlink/?LinkId=107087).<br /><br /> -Si usa las comunicaciones de red segura de SAP (SNC) para conectarse a un sistema SAP, también debe tener los archivos DLL pertinentes de SAP. Estos archivos DLL son diferentes para plataformas de 32 bits y 64 bits y están disponibles con SNOTE<sup> * </sup> 352295. Puede descargar los archivos DLL de [ http://go.microsoft.com/fwlink/?LinkId=104032 ](http://go.microsoft.com/fwlink/?LinkId=104032). Este vínculo tiene una opción de "Datos adjuntos" desde donde puede descargar el paquete. Los nombres de los archivos DLL son:<br /><br /> - **Para 32 bits**: gsskrb5.dll, gssntlm.dll<br /><br /> - **Para 64 bits x86**: gx64krb5.dll, gx64ntlm.dll|  
  
     * SNOTEs son notas de la versión que acompañan a las revisiones publicadas por SAP.  

### <a name="siebel-adapter"></a>Siebel adapter  
Ningún paso adicional.
  
### <a name="sql-adapter"></a>Adaptador de SQL  
  
**Controladores necesarios**:  
  
-   **Para SQL Server 2005**: si crea tipos definidos por el usuario (UDT) en SQL Server, asegúrese de que los ensamblados correspondientes para los UDT se agregan a la GAC.  
  
-   **Para SQL Server 2014, SQL Server 2012, SQL Server 2008 R2, SQL Server 2008 SP1**:  
  
    -   Si usa los UDT incluidos con las versiones de SQL Server, por ejemplo, Geography, asegúrese de que los archivos DLL siguientes están presentes en el equipo donde se usa el adaptador para realizar operaciones en SQL Server. Por ejemplo, si crea proyectos de BizTalk para realizar operaciones en SQL Server, estos archivos DLL deben estar presentes en el equipo donde se está ejecutando el servidor BizTalk Server.  
  
        -   Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.  
  
        -   Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.    
        
        Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente.          
  
    -   Si usa el adaptador para realizar operaciones en columnas de tipos de datos FILESTREAM, asegúrese de que tiene instalado el SDK de conectividad de cliente de SQL. Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccionar **SDK de conectividad de cliente de SQL** en el **selección de características** página del asistente. El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.  

    -   Si crea su propio UDT en SQL Server, asegúrese de que los ensamblados correspondientes para los UDT se agregan a la GAC.

## <a name="64-bit-support"></a>Compatibilidad con 64 bits

El adaptador es compatible con una instancia de host de 32 bits. No se admite para ejecutar el adaptador de Siebel en una instancia de host de 64 bits. 

Pueden ejecutar todos los adaptadores en una instancia de host de 32 bits o 64 bits. 


  
 Para obtener más información acerca de los escenarios de instalación admitidos para la instalación de los 32 bits y 64 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], consulte [escenarios para la instalación de BizTalk Adapter Pack en plataformas de 32 bits y 64 bits](#BKMK_Install_Scenarios).  
  
<a name="BKMK_Install_Adap"></a>   
## <a name="installing-the-biztalk-adapter-pack"></a>Instalar BizTalk Adapter Pack  
 Asegúrese de que todas las [requisitos previos de software](#BKMK_Prereqs) instalado antes de instalar la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Puede instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] de las dos maneras siguientes:  
  
-   **En el modo interactivo**: ejecutar el Asistente para la instalación  
  
-   **En modo silencioso**: usar la línea de comandos  
  
    > [!IMPORTANT]
    >  Debe tener privilegios administrativos en el equipo donde se instala el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], independientemente de si está instalando utilizando el asistente o la línea de comandos.  

### <a name="typical-vs-custom-installation"></a>Instalación personalizada de vs típico  
Esta sección enumeran los tipos de instalación y las características que se instalan con cada opción:  
  
-   El **típica** y **completar** opciones instalación todos los adaptadores, con los proveedores de datos asociados. No tiene la posibilidad de elegir un adaptador específico para instalar.  
  
-   El **personalizado** opción instala uno o varios adaptadores, con los proveedores de datos asociados. Puede elegir qué adaptadores para instalar. Si decide instalar a un proveedor de datos, también debe instalar al adaptador correspondiente. Sin embargo, puede instalar a un adaptador sin necesidad de instalar al proveedor de datos correspondiente. Esto se hace al expandir el **ADO proveedores** nodo y, a continuación, seleccione los proveedores que no desea instalar. Vea [instalar BizTalk Adapter Pack en modo interactivo](#BKMK_Install_wizard).  
  
     Por ejemplo, si instala el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], también debe instalar la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]. Sin embargo, puede instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] sin necesidad de instalar la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-32-bit-and-64-bit-platforms"></a>Escenarios para la instalación de BizTalk Adapter Pack en plataformas de 32 bits y 64 bits  
 Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] puede utilizarse para: 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] tiempo de diseño (cuándo generar metadatos para las operaciones en las aplicaciones LOB)
  
-   Tiempo de diseño de consola de administración de BizTalk Server (para la creación de puertos físicos)
  
    > [!NOTE]
    >  Consola de administración de BizTalk Server se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits.  
  
-   Tiempo de ejecución de BizTalk (al enviar y recibir mensajes desde aplicaciones de LOB)

Puede usar un único equipo para todos estos tardará entre o utiliza equipos diferentes. Dado que ambos [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y MMC de BizTalk son procesos de 32 bits, debe instalar el 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en el equipo donde se realizarán las tareas de tiempo de diseño. 

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-32-bit-platform"></a>Escenarios para la instalación de BizTalk Adapter Pack en una plataforma de 32 bits  
 Los escenarios admitidos en una plataforma de 32 bits se incluyen:  
  
|Para tiempo de diseño de Visual Studio|MMC de BizTalk para tiempo de diseño|Tiempo de ejecución de BizTalk|Para el diseño de Visual Studio de hora o tiempo de diseño de BizTalk MMC + BizTalk tiempo de ejecución|  
|---|---|---|---|  
|-Instalar 32 bits [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|-Instalar 32 bits [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|-Instalar 32 bits [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|-Instalar 32 bits [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|  
  
#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-64-bit-platform"></a>Escenarios para la instalación de BizTalk Adapter Pack en una plataforma de 64 bits  
 Los escenarios admitidos en una plataforma de 64 bits incluyen:  
  
|Para tiempo de diseño de Visual Studio|MMC de BizTalk para tiempo de diseño|Tiempo de ejecución de BizTalk|Para el diseño de Visual Studio de hora o tiempo de diseño de BizTalk MMC + BizTalk tiempo de ejecución|  
|---|---|---|---|  
|-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|**Para un proceso de BizTalk de 32 bits**:<br /><br /> -Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.<br /><br /> **Para un proceso de BizTalk de 64 bits**:<br /><br /> -Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 64 bits de LOB y otro archivos DLL necesarios.|**Para un proceso de BizTalk de 32 bits**:<br /><br /> -Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.<br /><br /> **Para un proceso de BizTalk de 64 bits**:<br /><br /> -Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 64 bits de LOB y otro archivos DLL necesarios.<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|  
  
> [!NOTE]
>  En cualquier equipo donde desea realizar tareas de tiempo de diseño, utilizando [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] o MMC de BizTalk, debe instalar lo 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-interactive-mode"></a>Instalar BizTalk Adapter Pack en modo interactivo  
Complete los pasos siguientes para instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] mediante el Asistente para la instalación.  
  
1.  Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] medio de instalación, ejecute **Setup.exe**.  
  
2.  Seleccione **instalar adaptadores de Microsoft BizTalk**. En la ventana siguiente, seleccione **instalar Microsoft BizTalk Adapter Pack** o **instalar Microsoft BizTalk Adapter Pack (x64)**, en función de la plataforma.  
  
    > [!NOTE]
    >  Si va a instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en una máquina virtual, el Asistente para la instalación no puede continuar más allá de un cuadro de diálogo que le informa de que el programa de instalación comprueba si hay espacio disponible en disco. En tales casos, se recomienda que utilice la opción de instalación silenciosa. Vea [instalar BizTalk Adapter Pack en modo silencioso](#BKMK_SilentInst) (en este tema).  
  
3.  En la pantalla de bienvenida, seleccione **siguiente**.  
  
4.  Acepte el contrato de licencia para el usuario final (CLUF) y, a continuación, seleccione **siguiente**.  
  
5.  En **Elegir tipo de instalación**:  
  
    -   Para instalar las características más comunes, seleccione **típica**.  
  
    -   Para seleccionar los adaptadores que desea instalar, seleccione **personalizada**y, a continuación, continúe con el paso siguiente.  
  
    -   Para instalar todas las características, seleccione **completar**.  
  
        > [!IMPORTANT]
        >  Para instalar sólo el adaptador que usa para comunicarse con la aplicación de empresa, seleccione la **personalizado** instalación.  
  
6. **Necesario** sólo si eligió la instalación personalizada. Si ha elegido el **típica** o **completar** instalación, a continuación, omita este paso y vaya al paso 7.  
  
    1.  En **personalizada**, expanda **Base adaptadores** para ver el número de adaptadores disponible.  
  
    2.  Para los adaptadores que no desea, seleccione el icono al lado del adaptador y, a continuación, seleccione **característica completa no estará disponible**.  
  
    3.  Expanda **ADO proveedores**y, a continuación, seleccione los proveedores que no desea instalar.  
  
    4.  Seleccione **Siguiente**.  
  
7.  Seleccione **Instalar**.  
  
8.  En **Customer Experience Improvement Program**, puede elegir para inscribirse. Si inscribe, puede compartir los siguientes datos con Microsoft:  
  
    -   Datos relacionados con el hardware del equipo en el que va a instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
  
    -   Datos relacionados con las versiones de aplicación de empresa que usa con la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
  
     Seleccione **Aceptar**. [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) proporciona más información.  
  
    > [!NOTE]
    >  Siempre puede cambiar esta configuración mediante la ejecución de la instalación en modo de reparación de **programas**.  
  
9. Seleccione **Finalizar**.  
  
<a name="BKMK_SilentInst"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-silent-mode"></a>Instalar BizTalk Adapter Pack en modo silencioso  
 Use la **msiexec** comando para realizar una instalación silenciosa. Como parte del comando msiexec, escriba los componentes individuales que desea instalar. En la tabla siguiente se enumera los valores para cada componente en el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Utilice estos valores para instalar componentes específicos (o quitar). Para instalar (o quitar) más de un componente, puede usar una combinación de estos valores separados por punto y coma.  
  
|Nombre de componente|Valor correspondiente para las propiedades de línea de comandos|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|DbFeature|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|OracleEBSFeature|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|SapBaseAdapterFeature|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|SiebelBaseAdapterFeature|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|SqlFeature|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|SapAdoFeature<br /><br /> **Tenga en cuenta**: debe proporcionar este valor solo si va a instalar la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] también.|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|SiebelAdoFeature<br /><br /> **Tenga en cuenta**: debe proporcionar este valor solo si va a instalar la [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] también.|  
|Todos los componentes|ALL|  
  
> [!IMPORTANT]
>  Los nombres de función distinguen mayúsculas de minúsculas.  
  
 Los pasos siguientes muestran cómo realizar una instalación silenciosa de [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para los distintos componentes.  
  
##### <a name="install-in-silent-mode"></a>Instalar en modo silencioso  
  
1.  Abra un símbolo del sistema y vaya a la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] raíz en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación.  
  
2.  Ejecute los comandos siguientes en función de lo que va a instalar:  
  
    > [!NOTE]
    >  Para realizar una instalación silenciosa en una plataforma basada en x64, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi` en los siguientes comandos.  
  
    -   Para llevar a cabo una instalación completa, que se instala todos los adaptadores incluidos los proveedores de datos de .NET Framework, escriba:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   Para instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] junto con [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   Para instalar el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] junto con [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   Para instalar a todos los adaptadores de base, escriba:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   Para instalar a los dos proveedores de datos de .NET Framework, escriba:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   Cualquier tipo de instalación personalizada mediante la separación de los componentes por una coma. Por ejemplo, para instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] con el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]y el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   También puede optar por inscribirse en CEIP como parte de la instalación silenciosa. Tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         De forma predeterminada, la opción es false. 
  
        > [!IMPORTANT]
        >  Al instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] versión de evaluación en modo silencioso, la opción predeterminada para el CEIP es true.  
  
     Para obtener más información sobre el tipo de comando msiexec `msiexec` en la línea de comandos y presione `ENTER`. O vaya a [ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199).
  
<a name="BKMK_PostInst"></a>   
### <a name="after-installing-the-biztalk-adapter-pack"></a>Después de instalar BizTalk Adapter Pack  
 Puede que necesite realizar las tareas siguientes después de instalar la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], en función de las operaciones que desea hacer con cada adaptador:  
  
-   [Configure el adaptador de base de datos de Oracle para utilizar una versión más reciente de Oracle.DataAccess.dll](#BKMK_ConfigNewOracleDLL) en el archivo de configuración OracleDB.  
  
-   [Crear objetos de base de datos de SQL Server (solo para el adaptador SAP)](#BKMK_CreateSQLServer) para invocar RFC transaccional (tRFCs) en un sistema SAP.  
  
-   [Registrar los enlaces del adaptador](#BKMK_Register_Bindings) y los proveedores de datos de .NET Framework si se produce un error en el Asistente para instalación hacerlo.  
  
-   [Determinar la clave pública y la versión](#BKMK_PubKey) de los archivos de adaptador diferentes.  
  
-   [Instalar las RFC personalizada](#BKMK_InstallCustomRFC) si decide instalar la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].  
  
<a name="BKMK_ConfigNewOracleDLL"></a>   
#### <a name="configure-the-oracle-database-adapter-to-use-a-newer-oracledataaccessdll-version"></a>Configure el adaptador de base de datos de Oracle para utilizar una versión más reciente de Oracle.DataAccess.dll  
 Cuando se configura un puerto para usar el adaptador de WCF-OracleDB o usar Visual Studio para consumir un adaptador generado, muestra un mensaje que el adaptador necesita Oracle.DataAccess.dll versión 2.111.7.0. Para resolver este mensaje, instale una versión compatible de Oracle.DataAccess.dll (vea [admite lista versión](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)) y, a continuación, actualice el `bindingRedirect` elemento en el archivo de configuración OracleDB. Pasos:  
  
1.  En el servidor BizTalk Server, vaya a las siguientes carpetas:  
  
     *unidad*: \Program BizTalk Adapter Pack (x64) \bin  
  
     *unidad*: \Program archivos (x86) \Microsoft BizTalk Adapter Pack\bin  
  
2.  Abra el archivo Microsoft.Adapters.OracleDB.config.  
  
3.  Busque la sección siguiente y copie y pegue lo siguiente:  
  
    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  
  
    ```  
  
    > [!NOTE]
    >  En este ejemplo, establecemos *newVersion* a 2.112.1.00. Establezca este valor en la versión que tenga instalada.  
  
> [!IMPORTANT]
>  -   Si hay varios servidores de BizTalk de este grupo, realizar el cambio en todos los servidores de BizTalk del grupo.  
> -   El *newVersion* valor debe actualizarse según la versión del archivo Oracle.DataAccess.dll instalado en el equipo.  Oracle.DataAccess.dll se incluye con el cliente de Oracle que se instala desde Oracle.  Solo se debe instalar una versión de cliente de Oracle [compatibles con BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).  
  
<a name="BKMK_CreateSQLServer"></a>   
#### <a name="create-sql-server-database-objects-only-for-the-sap-adapter"></a>Crear objetos de base de datos de SQL Server (solo para el adaptador SAP)  
 Para invocar tRFCs en un sistema SAP, ejecute el *SapAdapter-DbScript-Install.sql* secuencia de comandos SQL. Esta secuencia de comandos se instala con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación y crea objetos de base de datos en SQL Server. La secuencia de comandos se instala normalmente en \<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Puede ejecutar este script en cualquier base de datos de SQL Server, como especificar ese nombre de base de datos al usar el adaptador para invocar tRFCs.  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-adapter-bindings"></a>Registrar los enlaces del adaptador  
 Durante el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación, el Asistente para instalación puede fallar registrar los enlaces del adaptador o el proveedor de datos de .NET Framework para mySAP Business Suite, pero el programa de instalación continúa con la instalación del adaptador. Esto podría producir debido a problemas con la instalación de Windows Communication Foundation (WCF), [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] instalación o el archivo machine.config está dañado.  
  
Siga estos pasos *sólo* si se produce un error en el Asistente para instalación registrar los enlaces del adaptador o proveedores de datos de .NET Framework en el archivo machine.config.  
  
###### <a name="register-the-adapter-bindings-or-the-net-framework-data-providers"></a>Registrar los enlaces del adaptador o los proveedores de datos de .NET Framework  
  
1.  Vaya al archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.  
  
2.  Abra el archivo con un editor de texto.  
  
3.  Registrar los enlaces del adaptador:  
  
    1.  Busque la `system.serviceModel` elemento y agregue lo siguiente en él:  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  Busque la `bindingElementExtensions` elemento bajo system.serviceModel\extensions.  
  
    3.  Busque el enlace del adaptador que falta. Agregue las siguientes secciones en el `bindingElementExtensions` nodo, dependiendo del enlace del adaptador que falta. Debe registrar todos los enlaces si se produce un error en el Asistente para instalación registrar cualquiera.  
  
         Para el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], agregue:  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], agregue:  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], agregue:  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para el [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], agregue:  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para el [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], agregue:  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  Busque la `bindingExtensions` elemento bajo system.serviceModel\extensions.  
  
    5.  Busque el enlace del adaptador que falta. Agregue las siguientes secciones en el `bindingExtensions` nodo, dependiendo del enlace del adaptador que falta. Debe registrar todos los enlaces si se produce un error en el Asistente para instalación registrar cualquiera.  
  
         Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], agregue:  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], agregue:  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], agregue:  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], agregue:  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], agregue:  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  Para obtener información sobre cómo determinar la clave pública, consulte [determinar la clave pública y la versión](#BKMK_PubKey).  
  
4.  Registre los proveedores de datos de .NET Framework:  
  
    1.  Busque la `DbProviderFactories` elemento bajo el nodo system.data.  
  
    2.  Busque los proveedores de datos de .NET Framework que falta. Agregue las siguientes secciones en el `DbProviderFactories` nodo, en función del proveedor que faltan. Debe registrar todos los proveedores de si se produce un error en el Asistente para instalación registrar cualquiera.  
  
         Para el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], agregue:  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para el [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], agregue:  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  Guarde y cierre el archivo machine.config.  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determine-the-public-key-and-version"></a>Determinar la clave pública y la versión  
 Complete los pasos siguientes para determinar la clave pública y la versión de un adaptador o el proveedor de datos de .NET Framework.  
  
###### <a name="determine-the-public-key"></a>Determinar la clave pública  
  
1.  Vaya al directorio de Windows, normalmente C:\WINDOWS\assembly.  
  
2.  Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**. En la tabla siguiente se muestra el nombre de los archivos DLL para cada adaptador y el proveedor:  
  
    |Proveedor de datos de adaptador/.NET Framework|Nombre de la DLL|  
    |---|---|  
    |[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|Microsoft.Adapters.SAP|  
    |[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|Microsoft.Adapters.Siebel|  
    |[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|Microsoft.Adapters.OracleDB|  
    |[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|Microsoft.Adapters.OracleEBS|  
    |[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|Microsoft.Adapters.Sql.dll|  
    |[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|Microsoft.Data.SAPClient|  
    |[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|Microsoft.Data.SiebelClient|  
  
3.  En el **General** ficha, el **Token de clave pública** valores es la clave pública para el archivo DLL. El **versión** valor es el número de versión para el archivo DLL.  
  
4.  Copie la clave pública y, a continuación, seleccione **cancelar**.  
  
<a name="BKMK_InstallCustomRFC"></a>   
#### <a name="install-the-custom-rfcs"></a>Instalar las RFC personalizadas  
 Basta con realizar esta tarea si desea usar el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]. Para obtener instrucciones acerca de cómo instalar RFC personalizadas, consulte [instalar personalizado RFC](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) en el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentación. 
  
> [!IMPORTANT]
>  Si está utilizando una versión anterior de los documentos de RFC personalizadas proporcionada con la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], a continuación, debe actualizarlos a las RFC proporcionadas con esta versión. Hacer esto mediante la eliminación de los documentos de RFC anterior y, a continuación, instalar las RFC incluidos en esa versión.  

## <a name="installing-the-enterprise-applications"></a>Instalar las aplicaciones de empresa  
Para los pasos e instrucciones para instalar los sistemas LOB empresarial diferente, se le guía recommendnd usar su instalación específica. También consulte su documentación del adaptador para los cambios de configuración específica, si existe.   

## <a name="installation-and-post-installation-checklist"></a>Lista de comprobación de instalación y posteriores a la instalación  
  
-   Asegúrese de que ha instalado todo el [requisitos previos de software](#BKMK_Prereqs) con la opción de instalación correcta.
  
-   Asegúrese de que tiene la versión admitida de las aplicaciones de LOB de enterprise instalado en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Vea [admite versiones de la aplicación de Enterprise](#BKMK_SuppLOB).  
  
-   Para instalar sólo el adaptador para la empresa sistema LOB al que desea conectarse, asegúrese de que ha instalado el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] mediante la **personalizado** opción de instalación. Asegúrese de que no tiene instalado el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] mediante la **completar** opción de instalación. Vea [instalar BizTalk Adapter Pack](#BKMK_Install_Adap).  
  
-   Si desea realizar llamadas de tRFC al sistema SAP mediante el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], asegúrese de crear las tablas necesarias en una base de datos de SQL Server. Vea [después de instalar BizTalk Adapter Pack](#BKMK_PostInst).
  
-   Mientras se ejecuta el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Asistente para la instalación, puede obtener un mensaje de error que indica que el programa de instalación no pudo registrar los enlaces. Si es así, registrarlos manualmente. Vea [después de instalar BizTalk Adapter Pack](#BKMK_PostInst).  
  
-   Si decide instalar la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación, asegúrese de instalar las RFC personalizadas en el sistema SAP. Vea [después de instalar BizTalk Adapter Pack](#BKMK_PostInst).  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="change-the-biztalk-adapter-pack-installation"></a>Cambie la instalación de BizTalk Adapter Pack  
 Complete los pasos siguientes para cambiar la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación. Asegúrese de que tiene la [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación.  
  
 Puede modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación en modo interactivo (el Asistente para la instalación), o en modo silencioso (la línea de comandos).
  
#### <a name="change-the-bap-installation-in-interactive-mode"></a>Cambie la instalación de BAP en modo interactivo  
  
1.  Inicie sesión con una cuenta que sea miembro del grupo Administradores de BizTalk Server.  
  
2.  En **programas y características**, seleccione **desinstalar un programa**.  
  
3.  Haga clic en **Microsoft BizTalk Adapter Pack**y, a continuación, seleccione **cambio**.  
  
4.  En la pantalla de bienvenida, seleccione **siguiente**.  
  
5.  En **cambiar, reparar o quitar instalación**:  
  
    -   Para seleccionar los componentes que desea instalar, seleccione **cambio** y vaya al paso 6.  
  
    -   Para reparar los errores en la instalación más reciente, seleccione **reparar** y vaya al paso 7.  
  
    -   Para quitar Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en el equipo, seleccione **quitar** y, a continuación, vaya al paso 10.  
  
6.  Si decide modificar la instalación:  
  
    -   Expanda el **Microsoft BizTalk Adapter Pack** nodo optar por instalar los adaptadores de base, los proveedores de datos de .NET Framework o ambos.  
  
    -   Expanda el **Base adaptadores** nodo optar por instalar todos los adaptadores o adaptadores específicos.  
  
    -   Expanda el **ADO proveedores** nodo optar por instalar todos los proveedores o proveedores específicos.  
  
    -   Seleccione **Siguiente**.  
  
    -   Seleccione **cambio**y, a continuación, seleccione **finalizar**.  
  
7.  Si decide reparar la instalación, en la **preparado para reparar Microsoft BizTalk Adapter Pack** cuadro de diálogo, seleccione **reparar**. Inicia el Asistente para reparar la instalación.  
  
8.  Si es necesario, cambie las preferencias en relación con la aceptación de CEIP y, a continuación, seleccione **Aceptar**. 
  
9. Seleccione **Finalizar**.  
  
10. Si decide quitar los adaptadores, en el **listo para quitar Microsoft BizTalk Adapter Pack** cuadro de diálogo, seleccione **quitar**y, a continuación, seleccione **finalizar**.  
  
#### <a name="change-the-bap-installation-in-silent-mode"></a>Cambie la instalación de BAP en modo silencioso  
  
1.  Abra un símbolo del sistema y vaya al directorio raíz de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalador.  
  
2.  Ejecute un comando similar al siguiente:  
  
    > [!NOTE]
    >  Para modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi`.  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     Este comando quita el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]e instala el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].  
  
     Mediante el uso de valores diferentes para la `REMOVE` y `ADDLOCAL` propiedades, puede agregar o quitar componentes específicos. Hacer referencia a la tabla de [instalar BizTalk Adapter Pack en modo silencioso](#BKMK_SilentInst) (en este tema) para obtener información acerca de los valores que puede usar para estas propiedades.  
  
     También puede hacer una reparación silenciosa mediante la opción/f como parte del comando msiexec. Por ejemplo:  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     Puede utilizar diversas combinaciones diferentes con la opción/f. Para obtener más información sobre el tipo de comando msiexec `msiexec` en la línea de comandos y presione `ENTER`. O vaya a [ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199).  
  
    > [!IMPORTANT]
    >  Al modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación en modo silencioso, no se puede cambiar sus preferencias para participar o excluir el CEIP. Las preferencias que seleccionó durante la instalación se conserva, incluso si se establece explícitamente el CEIP_OPTIN en true o false.  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="removing-the-biztalk-adapter-pack"></a>Quitar BizTalk Adapter Pack  
  
> [!IMPORTANT]
>  Si ha creado las tablas en la base de datos de SQL Server para que funcione con la característica de tRFC de la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], debe quitarlos manualmente antes de quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación copia un archivo SapAdapter-DbScript-Uninstall.sql normalmente en \<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Ejecute este archivo para quitar las tablas que creó.  
  
Complete los pasos siguientes para quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] desde su equipo. Asegúrese de que tiene el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para quitar los adaptadores.  
  
 Puede quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo interactivo (Asistente para la instalación), o en modo silencioso (línea de comandos).
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-interactive-mode"></a>Desinstalar BizTalk Adapter Pack en modo interactivo  
  
1.  En **programas y características**, seleccione **desinstalar un programa**.  
  
2.  Haga clic en **Microsoft BizTalk Adapter Pack**y, a continuación, seleccione **desinstalar**.  
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-silent-mode"></a>Desinstalar BizTalk Adapter Pack en modo silencioso  
  
1.  Abra un símbolo del sistema y vaya al directorio raíz de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalador.  
  
2.  Ejecute el siguiente comando:  
  
    > [!NOTE]
    >  Para quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi`.  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     Este comando quita el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] desde el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación.  
  
     Al proporcionar valores diferentes para la `REMOVE` propiedad, puede quitar los componentes específicos de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación. Hacer referencia a la tabla de [instalar BizTalk Adapter Pack en modo silencioso](#BKMK_SilentInst) (en este tema) para obtener información acerca de los valores que puede usar para esta propiedad.  
  
     Para quitar completamente el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], ejecute el comando siguiente:  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     Para obtener más información sobre el tipo de comando msiexec `msiexec` en la línea de comandos y presione `ENTER`. O vaya a [ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199).
  
<a name="BKMK_PostRemove"></a>   
### <a name="after-removing-the-biztalk-adapter-pack"></a>Después de quitar el módulo de adaptador de BizTalk  
 Puede que necesite realizar los pasos siguientes después de quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:  
  
-   Quitar los enlaces del adaptador o el registro de proveedor de datos de .NET Framework, si el Asistente para la instalación no ha podido hacerlo
  
-   Quitar las RFC personalizadas, si decide instalar la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="remove-the-bindings-or-the-net-framework-data-provider-registration"></a>Quitar los enlaces o el registro del proveedor de datos de .NET Framework  
 Siga estos pasos *sólo* si se produce un error en el Asistente para la instalación quitar los enlaces del adaptador o el registro del proveedor de datos de .NET Framework desde el archivo machine.config.  
  
###### <a name="remove-the-adapter-bindings-or-net-framework-data-provider-registration"></a>Quitar los enlaces del adaptador o el registro del proveedor de datos de .NET Framework  
  
1.  Vaya al archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.  
  
2.  Abra el archivo con un editor de texto.  
  
3.  Quitar el registro de enlace del adaptador:  
  
    1.  Busque la `system.serviceModel` elemento y quitar lo siguiente en el elemento:  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  Busque la `bindingElementExtensions` elemento bajo system.serviceModel\extensions.  
  
    3.  Quitar las siguientes secciones en el `bindingElementExtensions` nodo, dependiendo del enlace del adaptador disponible. Si el Asistente para la instalación no puede quitar cualquiera, debe quitar todos los enlaces.  
  
         Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], quitar:  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], quitar:  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], quitar:  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], quitar:  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], quitar:  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  Busque la `bindingExtensions` elemento bajo system.serviceModel\extensions.  
  
    5.  Quitar las siguientes secciones en el `bindingExtensions` nodo, dependiendo del enlace del adaptador disponible. Si el Asistente para la instalación no puede quitar cualquiera, debe quitar todos los enlaces.  
  
         Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], quitar:  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], quitar:  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], quitar:  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], quitar:  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], quitar:  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  Quitar el registro del proveedor de datos de .NET Framework:  
  
    -   Busque la `DbProviderFactories` elemento bajo el nodo system.data.  
  
    -   Busque los proveedores de datos de .NET Framework que todavía están registrados. Quitar las siguientes secciones en el `DbProviderFactories` nodo, en función de los proveedores de datos existente de .NET Framework. Si existen, debe quitar todos los proveedores.  
  
         Para [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], quitar:  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], quitar:  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  Guarde y cierre el archivo machine.config.  
  
<a name="BKMK_Remove_SAP_Pro"></a>   
#### <a name="remove-the-custom-rfcs"></a>Quitar las RFC personalizadas  
Complete este paso para quitar las RFC personalizadas que ha instalado en el sistema SAP. Vea [instalar o quitar las solicitudes de cambio personalizadas](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).  
  
## <a name="troubleshoot-biztalk-adapter-pack-installation"></a>Solucionar problemas de instalación de BizTalk Adapter Pack  
 Estos son algunos problemas que puede enfrentarse al instalar [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Para obtener una lista completa de los problemas relacionados con la instalación, consulte **diagrama** para cada adaptador.  
  
-   **Ejecuta la instalación en un equipo de 64 bits podría producir un error al obtener acceso al archivo de esquema**  
  
     El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] el programa de instalación produce un error al obtener acceso a la **Microsoft.Adapters. *\<AdapterName\>*_schema.xml** archivo, pero continúa con la instalación del adaptador.  
  
     **Cause**  
  
     Si las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] están instalados en el mismo equipo, el archivo de esquema de destino utilizado es el mismo. Como resultado, se instala el archivo de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] podría estar utilizando IIS cuando el programa de instalación de 64 bits intenta tener acceso a él.  
  
     **Resolución**  
  
     Copie manualmente el **Microsoft.Adapters. *\<AdapterName\>*_schema.xml** archivo `C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`"a `C:\Windows\System32\inetsrv\config\schema`.  