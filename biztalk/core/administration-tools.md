---
title: "Herramientas de administración y rendimiento | Documentos de Microsoft"
description: Herramientas comunes para administrar las tareas, el rendimiento y seguimiento de BizTalk Server
ms.custom: 
ms.date: 09/04/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.ops.admintools
ms.assetid: 932814f7-2ab3-45cb-8bbc-eaf00fcb24a0
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc7420fa6bd59e3653f510e96d41015d266bcebc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="administrative-and-performance-tools"></a>Herramientas de administración y rendimiento 

## <a name="tools-list"></a>Lista de herramientas
Utilice las siguientes herramientas para administrar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o grupos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], para administrar aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], para interactuar con socios comerciales y controlar el estado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   **Consola de administración de BizTalk Server**. La consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] constituye la herramienta de administración principal de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Proporciona una interfaz de usuario gráfica para realizar todas las operaciones de implementación de una aplicación de BizTalk. Por ejemplo, puede iniciar los asistentes para importación, instalación y exportación, así como agregar y quitar artefactos de una aplicación y realizar otras modificaciones en la aplicación.  
  
     Mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede usar datos de visualización en directo, de eventos de mensajes archivados o de instancias de servicio para realizar un seguimiento del estado de la implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], identificar cuellos de botella y realizar un seguimiento del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede ver los detalles técnicos de una orquestación, canalización o instancia de mensaje concreta, así como el flujo de un mensaje concreto que entre en el sistema.  
  
     Para obtener información sobre el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, consulte [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md).  
  
-   **Herramienta de línea de comandos de BTSTask**. BTSTask permite realizar un amplio número de tareas administrativas desde la línea de comandos. Para obtener más información sobre el uso de BTSTask, vea [referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md).  
  
-   **API de programación y secuencias de comandos**. Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
     El modelo de objetos de WMI expone y simplifica las API administrativas. Las API de toda la administración exponen alguna forma de las siguientes operaciones en todos los objetos que administran: crear, enumerar, modificar y eliminar. WMI expone esta funcionalidad de un modo coherente para todos los objetos de WMI.  
  
-   **Actividad económica (BAM) de supervisión.** BAM utiliza Microsoft [!INCLUDE[btsOfficeNoVersion](../includes/btsofficenoversion-md.md)] [!INCLUDE[btsExcel](../includes/btsexcel-md.md)] libro para ofrecer a los usuarios empresariales con una forma de ver una vista holística en tiempo real de los procesos empresariales. Para obtener más información acerca de BAM, consulte [usando Business Activity Monitoring](../core/using-business-activity-monitoring.md).  


-   [**BizTalk Health Monitor**](http://blogs.msdn.com/b/biztalkhealthmonitor/ "BizTalk Health Monitor ") creada por el equipo de soporte técnico de BizTalk para recopilar información acerca de un entorno de BizTalk, incluidos los problemas conocidos y uso de la tabla. Se genera un informe con posibles áreas problemáticas resaltadas. Considere la posibilidad de ejecutar esta herramienta y revisar la salida de forma regular para ayudar a mantener el entorno de BizTalk. Esto reemplaza el Visor de MsbBox de BizTalk.

-   [**Herramienta de terminador de BizTalk**](https://www.microsoft.com/download/en/details.aspx?id=2846 "BizTalk terminador Tool") creada por el equipo de soporte técnico de BizTalk para resolver problemas comunes de integridad de base de datos normalmente se encuentran en la salida del Visor de MsgBox de BizTalk. Tareas comunes incluyen quitar instancias y purga de tablas de gran tamaño. Para obtener más información acerca de la herramienta de terminador de BizTalk, vaya a [esta entrada](http://blogs.msdn.com/b/biztalkcpr/archive/2011/02/10/using-biztalk-terminator-to-resolve-issues-identified-by-biztalk-msgboxviewer.aspx) en un Blog de ingenieros de BizTalk.

-   [**Microsoft BizTalk LoadGen 2007**](https://www.microsoft.com/downloads/details.aspx?FamilyID=c8af583f-7044-48db-b7b9-969072df1689&displaylang=en "Microsoft BizTalk LoadGen 2007") genera cargas de transmisión de mensajes para ejecutar pruebas de esfuerzo para sus aplicaciones de Microsoft BizTalk Server y de rendimiento y proporciona contadores de rendimiento para supervisar el rendimiento de la infraestructura de BizTalk Server.

-   [**BizTalk Server Best Practices Analyzer**](https://www.microsoft.com/downloads/details.aspx?FamilyID=93d432fe-1370-4b6d-aaa8-a0c43c30f5ab "BizTalk Server Best Practices Analyzer") realiza la comprobación de nivel de configuración de lectura y creación de informes. Best Practices Analyzer recopila datos de orígenes de información diferente, como clases de Instrumental de administración de Windows (WMI) y las bases de datos de SQL Server, las entradas del registro. Best Practices Analyzer utiliza los datos para evaluar la configuración de implementación. El analizador de procedimientos recomendados no modifica cualquier configuración del sistema y no es una herramienta de optimización automática.

-   [**Análisis de rendimiento de registros (PAL)**](http://www.codeplex.com/PAL "análisis de rendimiento de registros (PAL)") es una herramienta eficaz que lee un registro de contador del monitor de rendimiento (cualquier formato conocido) y se analiza mediante complejo, pero conocidos umbrales (proporcionados). La herramienta genera un informe basada en HTML que ofrece un gráfico de los contadores de rendimiento importante gráficamente y genera alertas cuando se superan umbrales.

-   [**DebugView para Windows**](https://technet.microsoft.com/en-us/sysinternals/bb896647.aspx "DebugView para Windows") es una aplicación que le permite supervisar los resultados de la depuración en el sistema local o en cualquier equipo de la red que pueda llegar mediante TCP/IP. Es capaz de mostrar el modo de kernel y depuración de Win32 de salida, por lo que no es necesario un depurador para capturar la salida de depuración generan sus aplicaciones o controladores de dispositivos, ni es necesario modificar las aplicaciones o controladores para usar las API de salida de depuración no estándar.

-   [**Inicie sesión Parser 2.2**](https://www.microsoft.com/downloads/details.aspx?familyid=890CD06B-ABF8-4C25-91B2-F8D975CF8C07&displaylang=en "Log Parser 2.2") es una herramienta eficaz y versátil que proporciona acceso universal de consulta a datos basados en texto, como archivos de registro, archivos XML y archivos CSV, así como orígenes de datos clave en las ventanas sistema operativo, como el registro de eventos, el registro, el sistema de archivos y Active Directory.

-   [**Process Explorer**](https://technet.microsoft.com/en-us/sysinternals/bb896653.aspx "Process Explorer") es útil para hacer un seguimiento de problemas de versión del archivo DLL o pérdida de identificadores y proporcionar información sobre el modo en que Windows y aplicaciones funcionen.

-   [**Seguimiento de TCP**](http://www.pocketsoap.com/tcptrace/ "seguimiento TCP") se usa para supervisar el tráfico de red basado en texto entre cliente y servidor. Resulta útil al usar adaptadores como SOAP, HTTP, POP3 etcetera para ver el mensaje viaja a través de la conexión.

-   [**DTCPing**](https://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=5e325025-4dcd-4658-a549-1d549ac17644 "DTCPing") está diseñado para ayudar a solucionar problemas de Firewall de Microsoft DTC, que a menudo podrá ver en una implementación multiservidor de BizTalk.

  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones y herramientas de administración](../core/application-deployment-and-management-tools.md)