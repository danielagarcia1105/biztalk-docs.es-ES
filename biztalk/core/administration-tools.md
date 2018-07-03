---
title: Herramientas de rendimiento y la administración | Microsoft Docs
description: Herramientas comunes para administrar tareas, el rendimiento y seguimiento de BizTalk Server
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 932814f7-2ab3-45cb-8bbc-eaf00fcb24a0
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e345e001d354cf925a68bc33d43f09bb42ad2761
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980501"
---
# <a name="administrative-and-performance-tools"></a>Herramientas de administración y rendimiento 

## <a name="tools-list"></a>Lista de herramientas
Puede usar las siguientes herramientas para administrar BizTalk ServerBizTalk Server, para administrar grupos de BizTalk Server, para implementar aplicaciones de BizTalk Server, para interactuar con socios comerciales y para supervisar el estado del servidor BizTalk Server:  
  
- **Consola de administración de BizTalk Server**. La consola de administración de BizTalk Server es la principal herramienta de administración de BizTalk Server. Proporciona una interfaz de usuario gráfica para realizar todas las operaciones de implementación de una aplicación de BizTalk. Por ejemplo, puede iniciar los asistentes para importación, instalación y exportación, así como agregar y quitar artefactos de una aplicación y realizar otras modificaciones en la aplicación.  
  
   Mediante la consola de administración de BizTalk Server, puede usar datos de instancia de mensaje activo o archivado eventos o el servicio de vista para realizar un seguimiento del estado de su implementación de BizTalk Server, identificar cuellos de botella y supervisar el entorno de BizTalk Server. Puede ver los detalles técnicos de una orquestación, canalización o instancia de mensaje concreta, así como el flujo de un mensaje concreto que entre en el sistema.  
  
   Para obtener información sobre el uso de la consola de administración de BizTalk Server, vea [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md).  
  
- **Herramienta de línea de comandos BTSTask**. BTSTask permite realizar un amplio número de tareas administrativas desde la línea de comandos. Para obtener más información sobre el uso de BTSTask, vea [referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md).  
  
- **API de programación y secuencias de comandos**. Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas. Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
   El modelo de objetos de WMI expone y simplifica las API administrativas. API de toda la administración exponen alguna forma de las siguientes operaciones en todos los objetos que administran: crear, enumerar, modificar y eliminar. WMI expone esta funcionalidad de un modo coherente para todos los objetos de WMI.  
  
- **Actividad económica (BAM) de supervisión.** BAM utiliza un libro de Microsoft Office Excel para proporcionar a los usuarios empresariales una manera de ver una vista holística en tiempo real de los procesos empresariales. Para obtener más información acerca de BAM, consulte [utilizando la actividad económica](../core/using-business-activity-monitoring.md).  


- [**BizTalk Health Monitor**](http://blogs.msdn.com/b/biztalkhealthmonitor/ "BizTalk Health Monitor ") creada por el equipo de soporte técnico de BizTalk para recopilar información acerca de un entorno de BizTalk, incluidos los problemas conocidos y uso de la tabla. Se genera un informe con posibles áreas problemáticas resaltadas. Considere la posibilidad de ejecutar esta herramienta y revisar la salida de forma periódica para ayudar a mantener su entorno de BizTalk. Esto reemplaza el Visor de MsbBox de BizTalk.

- [**Herramienta de terminador de BizTalk**](https://www.microsoft.com/download/en/details.aspx?id=2846 "BizTalk terminador herramienta") creada por el equipo de soporte técnico de BizTalk para resolver problemas habituales de integridad de base de datos normalmente se encuentran en la salida del Visor de cuadro de mensaje de BizTalk. Tareas comunes incluyen la eliminación de instancias y purga las tablas grandes. Para obtener más información acerca de la herramienta de terminador de BizTalk, vaya a [esta publicación](http://blogs.msdn.com/b/biztalkcpr/archive/2011/02/10/using-biztalk-terminator-to-resolve-issues-identified-by-biztalk-msgboxviewer.aspx) en un Blog de ingenieros de BizTalk.

- [**Microsoft BizTalk LoadGen 2007** ](https://www.microsoft.com/download/details.aspx?id=14925) genera cargas de transmisión de mensajes para ejecutar las pruebas de esfuerzo para las aplicaciones de Microsoft BizTalk Server y el rendimiento y proporciona contadores de rendimiento para supervisar el rendimiento de la infraestructura de BizTalk Server.

- [**BizTalk Server Best Practices Analyzer**](https://www.microsoft.com/downloads/details.aspx?FamilyID=93d432fe-1370-4b6d-aaa8-a0c43c30f5ab "BizTalk Server Best Practices Analyzer") realiza la comprobación de nivel de configuración mediante la lectura y creación de informes. Best Practices Analyzer recopila datos de distintas fuentes de información, como las clases de Instrumental de administración de Windows (WMI), las bases de datos de SQL Server y las entradas del registro. Best Practices Analyzer usa los datos para evaluar la configuración de implementación. El analizador de procedimientos recomendados no modificar la configuración del sistema y no es una herramienta de ajuste automático.

- [**Análisis de rendimiento de los registros (PAL)** ](https://github.com/clinthuffman/PAL) es una herramienta eficaz que lee en un registro de contador del monitor de rendimiento (cualquier formato conocido) y lo analiza con umbrales complejos, pero conocidos (siempre). La herramienta genera un informe basada en HTML que gráficamente gráficos los contadores de rendimiento importante y genera alertas cuando se superan los umbrales.

- [**DebugView para Windows** ](https://docs.microsoft.com/sysinternals/downloads/debugview) es una aplicación que le permite supervisar los resultados de la depuración en el sistema local o en cualquier equipo en la red que se pueda llegar mediante TCP/IP. Es capaz de mostrar el modo de núcleo y depuración de Win32 de salida, por lo que no es necesario un depurador para capturar la salida de depuración generan sus aplicaciones o controladores de dispositivos, ni es necesario modificar las aplicaciones o controladores para usar las API de salida de depuración no estándar.

- [**Inicie sesión Parser 2.2** ](https://www.microsoft.com/download/details.aspx?id=24659) es una herramienta eficaz y versátil que ofrece acceso universal de consulta a datos basados en texto tales como archivos de registro, archivos XML y archivos CSV, así como orígenes de datos clave en el sistema operativo de Windows, como el registro de eventos, el Registro, el sistema de archivos y Active Directory.

- [**Process Explorer** ](https://docs.microsoft.com/sysinternals/downloads/process-explorer) es útil para localizar problemas de versión de DLL o pérdidas de identificadores y proporcionan información detallada sobre la manera en Windows y el trabajo de aplicaciones.

- [**Seguimiento de TCP**](http://www.pocketsoap.com/tcptrace/ "seguimiento TCP") se usa para supervisar el tráfico de red basado en texto entre cliente y servidor. Resulta útil al usar adaptadores como SOAP, HTTP, POP3 etcetera para ver el mensaje viaja a través de la conexión.

- [**DTCPing** ](https://www.microsoft.com/download/details.aspx?id=2868) está diseñado para ayudar a solucionar los problemas de Firewall de Microsoft DTC, que verá a menudo en una implementación multiservidor de BizTalk.

  
## <a name="see-also"></a>Vea también  
 [Herramientas de implementación y administración de aplicaciones](../core/application-deployment-and-management-tools.md)