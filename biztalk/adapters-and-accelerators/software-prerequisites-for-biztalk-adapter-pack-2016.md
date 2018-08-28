---
title: Requisitos previos de software para el módulo de adaptador de BizTalk 2016 | Microsoft Docs
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
ms.openlocfilehash: 2832333e7c38b824fb26f988ec01423e519a83d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973277"
---
# <a name="software-prerequisites-for-biztalk-adapter-pack-2016"></a>Requisitos previos de software para el módulo de adaptador de BizTalk 2016
Enumera los requisitos de software de Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] (BAP) incluido con [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].

El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] pueden utilizarse desde:  

- Una aplicación .NET  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  

- Una interfaz de ADO  

- Un portal de Microsoft SharePoint  

  En función de cómo usar los adaptadores, el software necesario varía.  

## <a name="prerequisites-when-using-a-net-application"></a>Requisitos previos al usar una aplicación .NET  
Cuando se usa una aplicación .NET para consumir los adaptadores, se requiere el software siguiente en el equipo de desarrollo (el equipo donde va a crear la aplicación. NET). Instalar el software en el orden mostrado.


|                                                   BizTalk Adapter Pack 2016                                                    |
|--------------------------------------------------------------------------------------------------------------------------------|
|         <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>          |
|                                                     .NET Framework 4.6.*x*                                                     |
|                                                       Visual Studio 2015                                                       |
|                              [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                              |
| Los clientes de la aplicación de empresa y el software asociado. Consulte **admite versiones de la aplicación enterprise** (en este tema). |

## <a name="prerequisites-when-using-biztalk-server"></a>Requisitos previos al usar BizTalk Server  
Cuando se usa un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para consumir los adaptadores, se requiere el siguiente software en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Instalar el software en el orden mostrado.


|                                                                                                                                                                                                                                              BizTalk Adapter Pack 2016                                                                                                                                                                                                                                               |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                                    <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>                                                                                                                                                                                                     |
|                                                                                                                                                                                                                                                .NET Framework 4.6.*x*                                                                                                                                                                                                                                                |
|                                                                                                                                                                                                                                                  Visual Studio 2015                                                                                                                                                                                                                                                  |
| [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> Instalar el [!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]. Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]. |
|                                                                                                                                                                                                                                  [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]                                                                                                                                                                                                                                   |
|                                                                                                                                                                                            Los clientes de la aplicación de empresa y el software asociado. Consulte **admite versiones de la aplicación enterprise** (en este tema).                                                                                                                                                                                            |

## <a name="prerequisites-when-using-ado"></a>Requisitos previos al usar ADO  
 El **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** y **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** incluir una capa de ADO (*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* y *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]*) que puede se utiliza para escribir un cliente de ADO.NET para conectarse a un sistema SAP o Siebel. También puede usar la capa de ADO con SQL Server Integration Services (SSIS) para importar y exportar datos de la aplicación de LOB y SQL Server Reporting Services (SSRS) para generar informes para presentar los datos de los sistemas de LOB.  

> [!NOTE]
>  Usar el proveedor de ADO con SSRS solo se admite para la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].  

Se requiere el software siguiente en el equipo que usa el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] con una interfaz de ADO. Instalar el software en el orden mostrado.  


|                                                   BizTalk Adapter Pack 2016                                                    |
|--------------------------------------------------------------------------------------------------------------------------------|
|         <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>          |
|                                                     .NET Framework 4.6.*x*                                                     |
|                                                       Visual Studio 2015                                                       |
|                              [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                              |
|                       <ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul>                        |
| Los clientes de la aplicación de empresa y el software asociado. Consulte **admite versiones de la aplicación enterprise** (en este tema). |

## <a name="prerequisites-when-using-sharepoint"></a>Requisitos previos al uso de SharePoint  
El objetivo del uso de los adaptadores con Microsoft SharePoint es mostrar datos de una aplicación LOB en un portal de SharePoint.  

Una instalación típica con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] y SharePoint puede usar un único equipo o equipos diferentes para distintas tareas. En la tabla siguiente se enumera los requisitos previos de software para cada equipo. Si usa un único equipo, todo el software debe instalarse en el equipo. Instalar el software en el orden mostrado.  


|                                                                                                                                                                                                                                             Equipo donde se ejecuta el Asistente para desarrollo de servicio de adaptador de WCF                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                  Equipo que hospeda el servicio de WCF                                                                                                                                                                                                                                                                                                                                                   | Equipo donde se puede usar SharePoint Designer para definir los tipos de contenido externo |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.<em>x</em></li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>Los clientes de la aplicación de empresa y el software asociado. Consulte <strong>admite versiones de la aplicación enterprise</strong> (en este tema).</li></ul> | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.<em>x</em></li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>Los clientes de la aplicación de empresa y el software asociado. Consulte <strong>admite versiones de la aplicación enterprise</strong> (en este tema).</li><br /><br /><li>Versión de Internet Information Services (IIS) que se incluye con el sistema operativo. [KB 224609](https://support.microsoft.com/kb/224609) se enumeran las versiones.</li> </ul> |                   Kit de desarrollo de Software de Microsoft SharePoint (SDK)                    |

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>Versiones de la aplicación enterprise compatible  
Para ver las versiones específicas de sistema LOB que son compatibles con BizTalk Adapter Pack, consulte  **[sistemas admitidos línea de negocio (LOB)](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**.

Esta sección enumeran cualquier información adicional para cada adaptador, como los archivos DLL de cliente necesarios para cada adaptador.  

### <a name="oracle-database-adapter"></a>Adaptador para base de datos de Oracle  

-   Opcional: Si usa transacciones distribuidas con la base de datos de Oracle, instalar **Oracle Services para Microsoft Transaction Server** (parte de la instalación del cliente de Oracle) en el equipo que ejecuta el cliente del adaptador.  

-   Para que la aplicación para que funcione con la versión más reciente de ODP.NET, instale el **directiva dll** y registrar los archivos DLL en la GAC. Consulte [proveedor de datos de Oracle para .NET preguntas más frecuentes sobre](http://www.oracle.com/technetwork/database/windows/faq-093106.html).  

### <a name="oracle-e-business-adapter"></a>Adaptador para Oracle E-Business  

-   Opcional: Para usar transacciones distribuidas con la base de datos de Oracle, instale **Oracle Services para Microsoft Transaction Server** (parte de la instalación del cliente de Oracle) en el equipo que ejecuta el cliente del adaptador.  

-   Para que la aplicación para que funcione con la versión más reciente de ODP.NET, instale el **directiva dll** y registrar los archivos DLL en la GAC. Consulte [proveedor de datos de Oracle para .NET preguntas más frecuentes sobre](http://www.oracle.com/technetwork/database/windows/faq-093106.html).  

### <a name="sap-adapter"></a>SAP adapter  

- El [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] requiere la versión Unicode de RFC SDK con independencia de si el sistema SAP que no son Unicode o Unicode.  

- **Controladores necesarios**: en la tabla siguiente se enumera los archivos DLL necesarios por la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para interactuar con el sistema SAP:  


  | Versión de cliente SAP |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Controladores necesarios                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
  |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |        7.2         | - **SAP RFC SDK 7.10 UNICODE**. Esta opción está disponible como parte de SNOTE<sup> * </sup> 27517. Están disponibles en las instrucciones para descargar el SDK [ http://go.microsoft.com/fwlink/?LinkId=94691 ](http://go.microsoft.com/fwlink/?LinkId=94691). Una vez que ha descargado y extraído el SDK, copie todos los archivos DLL de las carpetas \rfcsdk\bin y \rfcsdk\lib a la ubicación pertinente mencionada anterior de esta tabla. <br /> <br /> -Dll están disponibles desde SAP como parte de \* \*R3DLLINST.zip*<em>. Esto contiene los archivos DLL de tiempo de ejecución de Microsoft y puede descargarse desde el sitio SAP. Consulte SNOTE<sup> </em> </sup> 684106 para obtener más información. Puede descargar el archivo .zip desde [ http://go.microsoft.com/fwlink/?LinkId=94693 ](http://go.microsoft.com/fwlink/?LinkId=94693). Este vínculo tiene una opción de "Attachments" desde donde puede descargar el paquete.<br /><br /> -Microsoft Visual C++ archivos DLL de tiempo de ejecución necesarios para el cliente de SAP 7.1 están disponibles desde los vínculos siguientes:<br /><br /> - **Para el cliente de 32 bits SAP 7.1**: Vcredist_x86.exe desde [ http://go.microsoft.com/fwlink/?LinkId=107086 ](http://go.microsoft.com/fwlink/?LinkId=107086).<br /><br /> -                                 **Para el cliente de SAP 7.1 de 64 bits**: Vcredist_x64.exe desde [ http://go.microsoft.com/fwlink/?LinkId=107087 ](http://go.microsoft.com/fwlink/?LinkId=107087).<br /><br /> -Si usa las comunicaciones de red seguro de SAP (SNC) para conectarse a un sistema SAP, también debe tener los archivos DLL pertinentes de SAP. Estos archivos DLL son diferentes para plataformas de 32 bits y 64 bits y están disponibles con SNOTE<sup> * </sup> 352295. Puede descargar los archivos DLL de [ http://go.microsoft.com/fwlink/?LinkId=104032 ](http://go.microsoft.com/fwlink/?LinkId=104032). Este vínculo tiene una opción de "Attachments" desde donde puede descargar el paquete. Los nombres de los archivos DLL son:<br /><br /> - \*\*para 32 bits*<em>: gsskrb5.dll, gssntlm.dll<br /><br /> - \*\*Para 64 bits x86</em>\*: gx64krb5.dll, gx64ntlm.dll |

   > [!TIP]
   > SNOTEs son las notas de la versión que acompañan a las revisiones publicadas por SAP.  

  La mayoría de los paquetes que contienen estos archivos DLL se debe descargar desde SAP Service Marketplace. Para obtener descargas de SAP Service Marketplace: 

  1. Instalar al administrador de descargas disponibles desde SAP Service Marketplace.  

  2. Configurar el Administrador de descargas con sus credenciales de SAP Service Marketplace.  

  3. Autorización mediante el administrador SAP de su organización para descargar software desde el sitio Web de servicio SAP. Esto es necesario porque el acceso al centro de distribución de Software de SAP está restringido por un objeto de autorización 'Descargar Software'. Esto garantiza que el software se descarga solo los usuarios autorizados.  

  4. Instalar el programa SAPCAR, que es necesario para extraer los archivos de los paquetes que descargan desde SAP Service Marketplace. SAPCAR también está disponible desde SAP Service Marketplace.  

     Para la versión de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], debe tener las versiones respectivas de 32 bits y 64 bits de estos archivos DLL.  

  -   En un equipo de 32 bits, la versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.  

  -   En un equipo de 64 bits, la versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\SysWow64. La versión de 64 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.  


### <a name="siebel-adapter"></a>Siebel adapter  
No hay pasos adicionales.

### <a name="sql-adapter"></a>Adaptador de SQL  

**Controladores necesarios** para SQL Server 2014:  

-   Si usa los UDT se incluye con las versiones de SQL Server, por ejemplo, Geography, asegúrese de que los archivos DLL siguientes están presentes en el equipo donde se usa el adaptador para realizar operaciones en SQL Server. Por ejemplo, si crea proyectos de BizTalk para realizar operaciones en SQL Server, estos archivos DLL deben estar presentes en el equipo donde se ejecuta BizTalk Server.  

    -   Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.  

    -   Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.    

    Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente.          

-   Si usa el adaptador para realizar operaciones en las columnas de tipos de datos FILESTREAM, asegúrese de que tiene instalado el SDK de conectividad de cliente de SQL. Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccione **SDK de conectividad de cliente SQL** en el **selección de características** página del asistente. El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.  

-   Si crea su propio UDT en SQL Server, asegúrese de que los ensamblados respectivos para los UDT se agregan a la GAC.

## <a name="64-bit-host-instance-support"></a>compatibilidad con instancia de host de 64 bits

El adaptador de Siebel es compatible con una instancia de host de 32 bits. No se admite para ejecutar el adaptador de Siebel en una instancia de host de 64 bits. 

Todos los adaptadores pueden ejecutar en una instancia de host de 32 bits o 64 bits. 

 Para obtener más información acerca de los escenarios de instalación admitidos para la instalación de los 32 bits y 64 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], consulte **escenarios de instalación de 32 bits y 64 bits** en [instalar BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md).  

## <a name="next-step"></a>Paso siguiente
[Instalar BizTalk Adapter Pack](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
