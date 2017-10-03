---
title: "Introducción al soporte técnico de 64 bits para que BizTalk Server | Documentos de Microsoft"
description: "compatibilidad con 64 bits en los adaptadores, procesos, administración de BizTalk, herramientas de BAM, ensamblados, orquestaciones etc. en BizTalk Server"
ms.custom: 
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52ae9037-a7af-48e4-b6a3-bff7600802de
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaf155bac387f613725023feb015f8f9a1894a2d
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2017
---
# <a name="biztalk-server-64-bit-support"></a>Compatibilidad de BizTalk Server con 64 bits
Este tema responde a algunas preguntas frecuentes sobre la compatibilidad de 64 bits de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="which-versions-of-64-bit-windows-are-supported"></a>¿Qué versiones de Windows de 64 bits son compatibles?  
 Todas las ediciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite la ejecución de 32 bits y la ejecución de 64 bits nativa en los sistemas operativos compatibles. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]incluye opciones de configuración de 32 bits y 64 bits. 
 
  [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016)  
  
 [Requisitos de hardware y Software para BizTalk Server 2013 y 2013 R2](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)  
  
## <a name="is-there-an-extra-cost-for-64-bit-support"></a>¿Supone la compatibilidad con 64 bits algún costo adicional?  
 No. compatibilidad con 64 bits se incluye sin cargo adicional.  
  
## <a name="is-itanium-based-hardware-supported"></a>¿Existe compatibilidad con el hardware basado en Itanium?  
 Para el tiempo de ejecución de BizTalk, no. Para las bases de datos de BizTalk, sí.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] requiere hardware de CPU compatible con AMD64 o EM64T. Como resultado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se admite en Windows que se ejecuta en las CPU de 64 bits basados en Itanium. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Sí permite la ejecución con basado en Itanium [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Por lo tanto, todas las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se admiten en CPU de 64 bits de Itanium.  
  
## <a name="which-biztalk-server-processes-run-in-64-bit-mode"></a>¿Qué procesos de BizTalk Server se ejecutan en modo de 64 bits?  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]los archivos ejecutables se alojan en varios tiempos de ejecución de servidor diferente. En la tabla siguiente enumera las [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesos se ejecutan en modo de 64 bits.  
  
|Procesar|compatibilidad con 32 bits|Compatibilidad con 64 bits|  
|-------------|---------------------|---------------------|  
|Adaptadores basados en HTTP (IIS)|Sí|Parcial|  
|Instancias de host de BizTalk|Sí|Sí|  
|SSO empresarial|Sí|Sí|  
|Portal de BAM (IIS)|Sí|No|  
|SQL Server|Sí|Sí|  
  
##### <a name="http-based-adapters-iis"></a>Adaptadores basados en HTTP (IIS)  
 Los componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como los adaptadores de HTTP y SOAP se hospedan y ejecutan en Internet Information Services (IIS). Todos los adaptadores son compatibles con el modo de 32 bits de IIS. Algunos adaptadores se pueden ejecutar en el modo de 64 bits de IIS. Para obtener una lista completa de adaptadores de 64 bits, consulte la lista de adaptadores que se incluye más adelante.  
  
##### <a name="biztalk-host-instances"></a>Instancias de host de BizTalk  
 Un “host” de BizTalk es un grupo lógico de servidores denominados “instancia de host”. Cada instancia de host se implementa como un servicio NT basado en BTSNTSvc.exe. Las orquestaciones y los adaptadores de tipo en curso se cargan y se ejecuta en instancias de host. Instancias de host pueden configurarse para ejecutarse en modo de 32 bits o 64 bits mediante el uso de la **sólo de 32 bits** opción de casilla de verificación en la **propiedades de Host** cuadro de diálogo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
##### <a name="enterprise-sso"></a>SSO empresarial  
 El inicio de sesión único de Microsoft Enterprise Single Sign-On (SSO) se ejecuta en un servicio de NT dedicado (ENTSSO.exe). Es nativo de 32 bits en 32 bits [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] y 64 bits nativo en 64 bits [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)].  
  
##### <a name="bam-portal-iis"></a>Portal de BAM (IIS)  
 Componentes del portal Business Activity Monitoring (BAM) deben ejecutar en IIS con ASP.NET 3.5 de 32 bits. El portal de BAM se ejecutará en hardware de 64 bits en modo WOW. Consulte "Ejecutar el portal de BAM en un entorno de 64 bits" en [personalizar la configuración del Portal de BAM](../core/customizing-the-bam-portal-configuration.md).  
  
##### <a name="sql-server"></a>SQL Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se comunica con Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] mediante protocolos de transporte nativo que pueden interoperar entre versiones de 32 bits y 64 bits de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Por lo tanto, los archivos ejecutables de 32 y 64 bits de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueden comunicarse con las versiones de 32 o 64 bits de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Todos los procedimientos almacenados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son compatibles en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] de 32 y 64 bits.  
  
## <a name="what-about-32-bit64-bit-support-in-non-server-processes"></a>¿Y la compatibilidad con 32 y 64 bits en procesos que no son de servidor?  
 **Microsoft Visual Studio**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]los ejecutables del diseñador se alojan en 32 bits [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] IDE. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]admite el desarrollo de proyectos de 64 bits mediante Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)], que se puede implementar en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 **Microsoft Management Console (MMC)**  
  
 La consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits, incluso en [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] de 64 bits. SSO empresarial es compatible con MMC de 32 y 64 bits.  
  
 **Internet Explorer**  
  
 El cliente de BAM requiere Internet Explorer de 32 bits instalar y usar en 64 bits [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)].  
  
## <a name="how-do-i-enable-native-64-bit-execution-of-orchestrations"></a>¿Cómo se habilita la ejecución de 64 bits de orquestaciones?  
 Asigne la orquestación para que se ejecute en una instancia de host que tiene la **sólo de 32 bits** propiedad desactivada. La instancia de host se debe ejecutar en un equipo con Windows x64.  
  
## <a name="can-i-build-net-assemblies-that-run-in-64-bit-orchestrations"></a>¿Se pueden crear ensamblados .NET que se ejecuten en orquestaciones de 64 bits?  
 Sí. Mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)], un programador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede crear ensamblados compatibles con la ejecución de 64 bits. Estos ensamblados se pueden implementar con orquestaciones y ejecutarse en instancias de host configuradas para la ejecución de 64 bits nativa.  
  
## <a name="will-net-framework-20-compiled-assemblies-jit-compile-properly-in-both-32-bit-and-64-bit"></a>¿Los ensamblados compilados por .NET Framework 2.0 realizarán la compilación JIT adecuadamente tanto en sistemas de 32 bits como de 64?  
 Sí. Si el ensamblado se compiló con la [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 2.0 y **AnyCPU** marca, una única DLL se desee a la compilación JIT correctamente en CLR de 32 bits o 64 bits.  
  
## <a name="can-i-install-both-32-bit-and-64-bit-components-in-a-single-biztalk-msi-package"></a>¿Se pueden instalar componentes de 32 y 64 bits en un único paquete de MSI de BizTalk?  
 Sí. Un administrador puede crear un archivo de paquete MSI desde una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El archivo MSI puede contener archivos .dll y .exe de 32 y 64 bits que se han agregado a la aplicación de BizTalk. En Windows de 32 bits, solo se instalarán los archivos .dll y .exe de 32 bits. En [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] x64, se instalarán los archivos .dll y .exe de 32 y 64 bits.  
  
## <a name="how-do-32-bit-biztalk-server-executables-run-on-windows-x64"></a>¿Cómo se ejecutan los archivos ejecutables de BizTalk Server de 32 bits en Windows x64?  
 Windows x64 proporciona la capacidad de ejecutar archivos ejecutables de 32 y 64 bits en el mismo equipo. Los archivos ejecutables de 32 utilizan el servicio de WOW64 para emular un entorno de 32 bits en tiempo de ejecución.  
  
## <a name="will-32-bit-biztalk-server-executables-have-4gb-of-addressable-process-memory-on-windows-x64"></a>¿Tendrán los archivos ejecutables de BizTalk Server de 32 bits 4 GB de memoria de proceso disponible en Windows x64?  
 Sí. En [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] x64, los procesos IIS y BTSNTSVC de 32 bits se ejecutan bajo WOW64 y pueden utilizar los 4 GB de memoria virtual. Esto es una mejora respecto al espacio de direcciones de 2 GB predeterminado de las versiones de 32 bits de Windows.  
  
 Puede establecer el umbral de limitación en el porcentaje (%) disponible o en un valor absoluto. Por ejemplo:  
  
-   Si usa un porcentaje disponible (0-100), el valor que inserte será un porcentaje de 2048 MB.  
  
-   Si usa un valor absoluto, el valor que inserte puede ser cualquier valor en MB de hasta 4096 MB (límite de 32 bits). En hosts de 64 bits, puede especificar un valor superior hasta el límite direccional de 64 bits teórico de 2 TB.  
  
## <a name="which-adapters-are-capable-of-running-in-64-bit-mode"></a>¿Qué adaptadores se pueden ejecutar en modo de 64 bits?  
 De forma predeterminada, todos los adaptadores pueden ejecutar en modo de 32 bits en 32 bits [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] y en WOW64 en 64 bits [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]. Los siguientes adaptadores se pueden ejecutar en modo de 64 bits nativo (en IIS o en BTSNTSVC como el proceso de host):  
  
-   Archivo  
  
-   HTTP  
  
-   MSMQ  
  
-   MQSeries  
  
-   SFTP  
  
-   SMTP  
  
-   SOAP  
  
-   WCF  
  
> [!NOTE]
>  El adaptador de MQ Series es compatible con procesos de 32 y 64 bits. El adaptador tiene un MQSeries Agent que se ejecuta en IBM WebSphere MQ Server en Windows. [Preparar el equipo para la instalación](../install-and-config-guides/prepare-your-computer-for-installation.md) se enumeran los requisitos de MQ.  
  
> [!NOTE]
>  Si su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones conectarse a un equipo de Windows Server 2003 (como SSO, SQL adaptador, MQSeries, MQSAgent, Oracle etc.), tendrá que instalar [934016](http://support.microsoft.com/kb/934016) y [934849](http://support.microsoft.com/kb/934849) en estos servidores de Windows servidores de 2003.  
  
> [!NOTE]
>  No se admite la ejecución del adaptador de FTP o POP3, o del descodificador MIME en instancias de host de 64 bits.  
  
## <a name="are-persisted-biztalk-orchestrations-dependent-on-32-bit-or-64-bit-runtimes"></a>¿Son las orquestaciones guardadas de BizTalk dependientes de motores de tiempo de ejecución de 32 o 64 bits?  
 No. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]conserva los componentes en tiempo de ejecución usando los formatos que son independientes de los tiempos de ejecución de 32 bits o 64 bits. Esto incluye orquestaciones, mensajes y puertos. Este modelo de persistencia permite a un administrador cambiar la configuración de host entre 32 y 64 bits sin crear incompatibilidades en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] datos.  
  
## <a name="when-i-upgrade-to-biztalk-server-will-my-biztalk-hosts-run-as-64-bit-by-default"></a>Al actualizar a la versión de BizTalk Server, ¿se ejecutan los hosts de BizTalk en modo de 64 bits de forma predeterminada?  
 No. De forma predeterminada, se actualiza a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] marcar todas las instancias de host de BizTalk como de 32 bits sólo. Un administrador debe crear nuevas instancias de host en equipos con Windows x64 y configurar las aplicaciones para que las usen.  
  
## <a name="can-i-have-a-mixed-biztalk-server-group-that-includes-both-32-bit-and-64-bit-biztalk-runtimes"></a>¿Se puede tener un grupo de BizTalk Server “mixto” que incluya tiempos de ejecución de BizTalk tanto de 32 como de 64 bits?  
 Sí.  
  
## <a name="what-languages-are-supported-on-64-bit-runtimes"></a>¿Qué idiomas son compatibles con tiempos de ejecución de 64 bits?  
 Todos los idiomas compatibles son compatibles con los motores de tiempo de ejecución de 32 y 64 bits.  
  
## <a name="what-64-bit-sql-server-components-are-required-to-configure-bam-tools"></a>¿Qué componentes de SQL Server de 64 bits son necesarios para configurar las herramientas de BAM?  
 El Asistente para configuración es un proceso de 32 bits; por lo tanto, necesita ciertos componentes que le permite comunicarse con 64 bits [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Debe instalar las siguientes [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] componentes de cliente para habilitar la configuración de herramientas de BAM:  
  
-   Componentes de conectividad  
  
-   Herramientas de administración  
  
-   Componentes heredados  
  
## <a name="see-also"></a>Vea también  
 [Planeación de capacidad y rendimiento](../core/performance-and-capacity-planning.md)
