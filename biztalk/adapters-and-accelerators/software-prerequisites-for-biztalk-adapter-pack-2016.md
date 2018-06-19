---
title: Requisitos previos de software de 2016 de módulo de adaptador de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65a063ca-37ae-420b-9d48-e6730caf17e3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0b33203d1e8e5b36c9fb8a54167c111a427b244
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227124"
---
# <a name="software-prerequisites-for-biztalk-adapter-pack-2016"></a>Requisitos previos de software de 2016 de módulo de adaptador de BizTalk
Enumera los requisitos de software de Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] (BAP) incluido con [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].
  
El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] pueden consumir desde:  
  
-   Una aplicación .NET  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Una interfaz de ADO  
  
-   Un portal de Microsoft SharePoint  
  
 En función de cómo usar los adaptadores, que varía según el software necesario.  
  
## <a name="prerequisites-when-using-a-net-application"></a>Requisitos previos al usar una aplicación .NET  
Cuando se usa una aplicación .NET para consumir los adaptadores, se requiere el software siguiente en el equipo de desarrollo (el equipo donde va a crear la aplicación. NET). Instalar el software en el orden indicado.
  
|BizTalk Adapter Pack 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|
|Los clientes de aplicaciones de empresa y el software asociado. Vea **admite versiones de la aplicación de enterprise** (en este tema).|

## <a name="prerequisites-when-using-biztalk-server"></a>Requisitos previos cuando se usa BizTalk Server  
Cuando se usa un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para consumir los adaptadores, se requiere el siguiente software en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Instalar el software en el orden indicado.
 
|BizTalk Adapter Pack 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> Instalar el [!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]. Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].|
|[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]|
|Los clientes de aplicaciones de empresa y el software asociado. Vea **admite versiones de la aplicación de enterprise** (en este tema).|

## <a name="prerequisites-when-using-ado"></a>Requisitos previos al usar ADO  
 El  **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]**  y  **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]**  incluir una capa de ADO ( *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]*  y  *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]* ) que puede se usa para escribir un cliente ADO.NET para conectarse a un sistema SAP o el sistema Siebel. También puede utilizar la capa de ADO con SQL Server Integration Services (SSIS) para importar y exportar datos de la aplicación de LOB y SQL Server Reporting Services (SSRS) para generar informes para presentar datos de los sistemas LOB.  
  
> [!NOTE]
>  Usar el proveedor de ADO con SSRS solo se admite para la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].  
  
Se requiere el software siguiente en el equipo que usa la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] con una interfaz de ADO. Instalar el software en el orden indicado.  

|BizTalk Adapter Pack 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|
|<ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul> |
|Los clientes de aplicaciones de empresa y el software asociado. Vea **admite versiones de la aplicación de enterprise** (en este tema).|

## <a name="prerequisites-when-using-sharepoint"></a>Requisitos previos al usar SharePoint  
El objetivo del uso de los adaptadores con Microsoft SharePoint es mostrar datos de una aplicación de LOB en un portal de SharePoint.  
  
Una instalación típica con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] y SharePoint puede usar un único equipo o equipos diferentes para distintas tareas. En la tabla siguiente se enumera los requisitos previos de software para cada equipo. Si está utilizando un único equipo, todo el software debe instalarse en el equipo. Instalar el software en el orden indicado.  
  
|Equipo donde se ejecuta el Asistente de desarrollo del servicio de adaptador de WCF|Equipo que hospeda el servicio WCF|Equipo donde se puede utilizar el Diseñador de SharePoint para definir los tipos de contenido externos| 
|---|---|---|  
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.*x*</li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>Los clientes de aplicaciones de empresa y el software asociado. Vea **admite versiones de la aplicación de enterprise** (en este tema).</li></ul> | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.*x*</li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>Los clientes de aplicaciones de empresa y el software asociado. Vea **admite versiones de la aplicación de enterprise** (en este tema).</li><br /><br /><li>Versión de Internet Information Services (IIS) que se incluye con el sistema operativo. [KB 224609](https://support.microsoft.com/kb/224609) se enumeran las versiones.</li> </ul>| Kit de desarrollo de Software de SharePoint de Microsoft (SDK)|
  
<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>Versiones de la aplicación de enterprise admitidos  
Para ver las versiones específicas de sistema LOB que son compatibles con BizTalk Adapter Pack, vea  **[sistemas Supported Line-of-Business (LOB)](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**.

Esta sección enumera ninguna información adicional para cada adaptador, como los archivos DLL de cliente necesario para cada adaptador.  
  
### <a name="oracle-database-adapter"></a>Adaptador para base de datos de Oracle  
  
-   Opcional: Si utiliza transacciones distribuidas con la base de datos de Oracle, instale **Oracle Services para Microsoft Transaction Server** (forma parte de la instalación de cliente de Oracle) en el equipo que ejecuta el cliente de adaptador.  
  
-   Para que la aplicación para que funcione con la versión más reciente de ODP.NET, instale el **directiva dll** y registrar los archivos DLL en la GAC. Vea [proveedor de datos de Oracle para .NET preguntas más frecuentes sobre](http://www.oracle.com/technetwork/database/windows/faq-093106.html).  

### <a name="oracle-e-business-adapter"></a>Adaptador para Oracle E-Business  
  
-   Opcional: Para usar transacciones distribuidas con la base de datos de Oracle, instale **Oracle Services para Microsoft Transaction Server** (forma parte de la instalación de cliente de Oracle) en el equipo que ejecuta el cliente de adaptador.  
  
-   Para que la aplicación para que funcione con la versión más reciente de ODP.NET, instale el **directiva dll** y registrar los archivos DLL en la GAC. Vea [proveedor de datos de Oracle para .NET preguntas más frecuentes sobre](http://www.oracle.com/technetwork/database/windows/faq-093106.html).  
  
### <a name="sap-adapter"></a>SAP adapter  
  
-   El [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] requiere la versión Unicode de RFC SDK independientemente de si el sistema SAP es Unicode o no Unicode.  
  
-   **Controladores necesarios**: en la tabla siguiente se enumera los archivos DLL necesarias para la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para comunicarse con el sistema SAP:  
  
    |Versión del cliente SAP|Controladores necesarios|  
    |---|---|  
    |7.2|- **SAP RFC SDK 7.10 UNICODE**. Esta opción está disponible como parte de SNOTE<sup> * </sup> 27517. Las instrucciones para descargar el SDK están disponibles en [http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691). Después de haber descargado y extraído el SDK, copie todos los archivos DLL de las carpetas \rfcsdk\bin y \rfcsdk\lib a la ubicación pertinente mencionada anterior a esta tabla. <br /> <br /> -Dll están disponibles desde SAP como parte de **R3DLLINST.zip**. Esto contiene archivos DLL de tiempo de ejecución de Microsoft y se puede descargar desde el sitio SAP. Vea SNOTE<sup> * </sup> 684106 para obtener más información. Puede descargar el archivo .zip de [http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693). Este vínculo tiene una opción de "Datos adjuntos" desde donde puede descargar el paquete.<br /><br /> -Microsoft Visual C++ DLL en tiempo de ejecución necesarias para el cliente de SAP 7.1 están disponibles en los siguientes vínculos:<br /><br /> - **Para el cliente de SAP 7.1 de 32 bits**: Vcredist_x86.exe de [http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086).<br /><br /> -                                 **Para el cliente de SAP 7.1 de 64 bits**: Vcredist_x64.exe desde [http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087).<br /><br /> -Si usa las comunicaciones de red segura de SAP (SNC) para conectarse a un sistema SAP, también debe tener los archivos DLL pertinentes de SAP. Estos archivos DLL son diferentes para plataformas de 32 bits y 64 bits y están disponibles con SNOTE<sup> * </sup> 352295. Puede descargar los archivos DLL de [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032). Este vínculo tiene una opción de "Datos adjuntos" desde donde puede descargar el paquete. Los nombres de los archivos DLL son:<br /><br /> - **Para 32 bits**: gsskrb5.dll, gssntlm.dll<br /><br /> - **Para 64 bits x86**: gx64krb5.dll, gx64ntlm.dll|  
  
     > [!TIP]
     > SNOTEs son notas de la versión que acompañan a las revisiones publicadas por SAP.  

    La mayoría de los paquetes que contengan dichos archivos DLL debe descargarse desde el catálogo de soluciones de servicio de SAP. Para obtener descargas de Marketplace de servicio de SAP: 
  
    1.  Instalar al administrador de descargas disponibles desde el catálogo de soluciones de servicio de SAP.  
  
    2.  Configurar el Administrador de descargas con sus credenciales para el catálogo de soluciones de servicio de SAP.  
  
    3.  Autorización por el administrador SAP en su organización para descargar el software desde el sitio Web de servicio SAP. Esto es necesario porque el acceso al centro de distribución de Software de SAP está restringido por un objeto de autorización 'Descargar Software'. Esto garantiza que el software se descarga solo por usuarios autorizados.  
  
    4.  Instalar el programa SAPCAR, que es necesario para extraer los archivos de los paquetes que descargó desde el catálogo de soluciones de servicio de SAP. SAPCAR también está disponible en el catálogo de soluciones de servicio de SAP.  
  
     Para la versión de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], debe tener las versiones respectivas de 32 bits y 64 bits de estos archivos DLL.  
  
    -   En un equipo de 32 bits, la versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.  
  
    -   En un equipo de 64 bits, la versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\SysWow64. La versión de 64 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.  
    
    
### <a name="siebel-adapter"></a>Siebel adapter  
Ningún paso adicional.
  
### <a name="sql-adapter"></a>Adaptador de SQL  
  
**Controladores necesarios** para SQL Server 2014:  
  
-   Si usa los UDT incluidos con las versiones de SQL Server, por ejemplo, Geography, asegúrese de que los archivos DLL siguientes están presentes en el equipo donde se usa el adaptador para realizar operaciones en SQL Server. Por ejemplo, si crea proyectos de BizTalk para realizar operaciones en SQL Server, estos archivos DLL deben estar presentes en el equipo donde se está ejecutando el servidor BizTalk Server.  
  
    -   Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.  
  
    -   Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.    
        
    Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente.          
  
-   Si usa el adaptador para realizar operaciones en columnas de tipos de datos FILESTREAM, asegúrese de que tiene instalado el SDK de conectividad de cliente de SQL. Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccionar **SDK de conectividad de cliente de SQL** en el **selección de características** página del asistente. El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.  

-   Si crea su propio UDT en SQL Server, asegúrese de que los ensamblados correspondientes para los UDT se agregan a la GAC.

## <a name="64-bit-host-instance-support"></a>compatibilidad con la instancia de host de 64 bits

El adaptador es compatible con una instancia de host de 32 bits. No se admite para ejecutar el adaptador de Siebel en una instancia de host de 64 bits. 

Pueden ejecutar todos los adaptadores en una instancia de host de 32 bits o 64 bits. 
  
 Para obtener más información acerca de los escenarios de instalación admitidos para la instalación de los 32 bits y 64 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], consulte **escenarios de instalación de 32 bits y 64 bits** en [instalar BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md).  
 
## <a name="next-step"></a>Paso siguiente
[Instalar BizTalk Adapter Pack](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
