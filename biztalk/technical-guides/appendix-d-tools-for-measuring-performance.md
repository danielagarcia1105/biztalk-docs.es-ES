---
title: "Apéndice D: herramientas para medir el rendimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 024f4a08-f3fd-4786-8549-0da5463c0bb9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 887272c841aacc0eaa85c197854067133166f783
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-d-tools-for-measuring-performance"></a>Apéndice D: herramientas para medir el rendimiento
En este tema se describe varias herramientas que pueden utilizar para supervisar y evaluar el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
## <a name="performance-analysis-of-logs-pal-tool"></a>Herramienta de análisis de registros (PAL) de rendimiento  
 La herramienta de la PAL se usa para generar un informe basado en HTML que gráficamente gráficos los contadores del monitor de rendimiento importante y genera alertas cuando se superan los umbrales de estos contadores. PAL es una herramienta excelente para identificar cuellos de botella en un [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] solución para facilitar la asignación de recursos adecuada al optimizar el rendimiento de la solución. Para obtener más información acerca de la herramienta de análisis de rendimiento de registros (PAL), consulte [http://go.microsoft.com/fwlink/?LinkID=98098](http://go.microsoft.com/fwlink/?LinkID=98098).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="performance-monitor"></a>Monitor de rendimiento  
 El Monitor de rendimiento muestra los contadores de rendimiento de Windows integrados, bien en tiempo real o como una manera de revisar los datos históricos.  
  
## <a name="log-parser"></a>Analizador del registro  
 Analizador del registro es una herramienta eficaz y versátil que proporciona acceso universal de consulta a datos basados en texto, como archivos de registro, archivos XML y archivos CSV, así como orígenes de datos clave en el sistema de operativo Windows® como el registro de eventos, el registro, el sistema de archivos y Active Directory®. Analizador del registro está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkID=100882](http://go.microsoft.com/fwlink/?LinkID=100882).  
  
## <a name="relog"></a>Relog  
 La utilidad de volver a registrar se usa para extraer los contadores de rendimiento de registros creados por el Monitor de rendimiento y convertir los datos en otros formatos, como archivos de texto delimitado por tabulaciones (TSV texto), archivos de texto delimitado por comas (CSV de texto), archivos binarios y las bases de datos SQL. Estos datos, a continuación, se pueden analizar y consultan mediante otras herramientas, como el analizador del registro, para generar estadísticas de indicadores clave de rendimiento (KPI). Se proporciona la utilidad de volver a registrar con [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] y versiones posteriores.  
  
## <a name="loadgen"></a>LoadGen  
 BizTalk LoadGen 2007 es una herramienta de generación de carga utilizada para ejecutar el rendimiento y pruebas de esfuerzo en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. La herramienta Microsoft BizTalk LoadGen 2007 está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).  
  
## <a name="visual-studio-team-system-2008-load-testing"></a>Pruebas de carga de 2008 del sistema de equipo de Visual Studio  
 El Visual Studio Team System (VSTS) 2008 proporciona una herramienta para crear y ejecutar pruebas de carga. Para obtener más información acerca de cómo trabajar con pruebas de carga, consulte [http://go.microsoft.com/fwlink/?LinkId=141486](http://go.microsoft.com/fwlink/?LinkId=141486).  
  
## <a name="bizunit"></a>BizUnit  
 BizUnit es un marco que se ha diseñado para automatizar las pruebas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] soluciones. BizUnit es una herramienta excelente para las pruebas to-end [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] escenarios. Para obtener más información acerca de BizUnit 3.0, consulte [http://go.microsoft.com/fwlink/?LinkID=85168](http://go.microsoft.com/fwlink/?LinkID=85168).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="iometer"></a>IOMeter  
 IOMeter es una herramienta de código abierto que se usa para medir rendimiento de E/S de disco. Para obtener más información acerca de IOMeter, consulte [http://go.microsoft.com/fwlink/?LinkId=122412](http://go.microsoft.com/fwlink/?LinkId=122412).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="biztalk-server-orchestration-profiler"></a>Generador de perfiles de orquestación de BizTalk Server  
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] el generador de perfiles de orquestación se utiliza para obtener una vista consolidada de orquestación de datos de seguimiento para un período de tiempo especificado. Esto proporciona a los desarrolladores una visión general de cómo se procesan las orquestaciones y el nivel de cobertura de pruebas que se aplican. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orquestación perfil ayuda a identificar posibles problemas con las excepciones de ruta de acceso de latencia y el código resaltado de larga ejecución y error propensas a formas de orquestación, que son fundamentales para pruebas de rendimiento efectivo. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está disponible para su descarga en el generador de perfiles de orquestación [http://go.microsoft.com/fwlink/?LinkID=102209](http://go.microsoft.com/fwlink/?LinkID=102209).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="pathping"></a>Pathping  
 Pathping proporciona información acerca de la posible pérdida de datos en uno o varios saltos de enrutador en la forma de un host de destino. Para ello, pathping envía paquetes de protocolo de mensajes de Control de Internet (ICMP) a cada enrutador en la ruta de acceso. Pathping.exe está disponible con todas las versiones de Windows desde Windows 2000 Server.  
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>Herramientas de supervisión y optimización del rendimiento de SQL Server  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]proporciona varias herramientas para supervisar los eventos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y para optimizar el diseño físico de la base de datos. Estas herramientas se describen en el tema "Herramientas de supervisión y optimización del rendimiento" en la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla en [http://go.microsoft.com/fwlink/?LinkId=146357](http://go.microsoft.com/fwlink/?LinkId=146357). Información sobre herramientas específicas que se usan para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] a continuación se proporciona supervisión y optimización del rendimiento:  
  
### <a name="sql-profiler"></a>SQL Profiler  
 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] generador de perfiles puede usarse para capturar instrucciones Transact-SQL que se envían a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] conjuntos de resultados de estas instrucciones. Dado que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] está totalmente integrado con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], el análisis de un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] traza del analizador puede ser una herramienta útil para analizar problemas que pueden producirse en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] al leer y escribir en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos. Para obtener información sobre cómo usar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] generador de perfiles, vea "Usar el analizador de SQL Server" en la [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] libros en pantalla en [http://go.microsoft.com/fwlink/?linkid=104423](http://go.microsoft.com/fwlink/?linkid=104423).  
  
> [!IMPORTANT]  
>  Hay una sobrecarga considerable asociada con el analizador de SQL en ejecución. Por lo tanto, SQL Profiler es ideal para su uso en entornos de desarrollo o de prueba. Si utiliza a SQL Profiler para solucionar problemas de un entorno de producción, tenga en cuenta los costes generales asociados y limitar el uso del analizador de SQL en consecuencia.  
  
> [!NOTE]  
>  Cuando se usa a SQL Profiler para capturar instrucciones Transact-SQL, configurar el analizador de SQL para generar una salida en una unidad local en lugar de una unidad de encontrarse en un recurso compartido de red remota u otro dispositivo lenta, por ejemplo, un dispositivo de memoria USB local.  
  
### <a name="sql-trace"></a>Seguimiento de SQL  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Proporciona procedimientos almacenados del sistema de Transact-SQL para crear seguimientos en una instancia de motor de base de datos de SQL Server. Estos procedimientos almacenados del sistema pueden utilizarse desde sus propias aplicaciones para crear seguimientos manualmente, en lugar de usar SQL Server Profiler. Esto permite escribir aplicaciones personalizadas específicas para las necesidades de la organización. Para obtener más información acerca del uso de seguimiento de SQL, vea "Introducing SQL Trace en la [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] libros en pantalla en [http://go.microsoft.com/fwlink/?LinkId=146354](http://go.microsoft.com/fwlink/?LinkId=146354).  
  
> [!NOTE]  
>  Al utilizar seguimiento de SQL para capturar instrucciones Transact-SQL, configurar el seguimiento de SQL para generar la salida a una unidad local en lugar de una unidad que se encuentra en un recurso compartido de red remota u otro dispositivo lenta, como una unidad flash USB.  
  
### <a name="sql-activity-monitor"></a>Monitor de actividad SQL  
 [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]Monitor de actividad proporciona información acerca de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] procesos y cómo estos procesos afectan a la instancia actual de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información acerca de [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] Monitor de actividad, vea "Monitor de actividad" en la [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] libros en pantalla en [http://go.microsoft.com/fwlink/?LinkId=146355](http://go.microsoft.com/fwlink/?LinkId=146355). Para obtener información acerca de cómo abrir el Monitor de actividad de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio, vea "Cómo: abrir el Monitor de actividad ([!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio) en el [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] libros en pantalla en [http://go.microsoft.com/fwlink/?LinkId=135094](http://go.microsoft.com/fwlink/?LinkId=135094).  
  
### <a name="sql-server-2008-data-collection"></a>Recopilación de datos SQL Server 2008  
 [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] proporciona un recopilador de datos que puede utilizar para obtener y guardar datos recopilados de varios orígenes. El recopilador de datos permite usar contenedores de recopilación de datos, que permiten determinar el ámbito y la frecuencia de recopilación de datos en un equipo que está ejecutando [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]. Para obtener más información acerca de cómo implementar [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] recopilación de datos, vea "Recopilación de datos" en la [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] libros en pantalla en [http://go.microsoft.com/fwlink/?LinkId=146356](http://go.microsoft.com/fwlink/?LinkId=146356).  
  
### <a name="sql-server-2005-performance-dashboard-reports"></a>Informes de panel de rendimiento de SQL Server 2005  
 [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]Informes del panel de rendimiento se utilizan para supervisar y solucionar problemas de rendimiento en su [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] servidor de base de datos. Para obtener más información acerca de [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] informes del panel de rendimiento, consulte [http://go.microsoft.com/fwlink/?LinkID=118673](http://go.microsoft.com/fwlink/?LinkID=118673).  
  
### <a name="sqlio"></a>SQLIO  
 La herramienta SQLIO fue desarrollada por Microsoft para evaluar la capacidad de E/S de una configuración determinada. Como indica el nombre de la herramienta, SQLIO es una herramienta útil para medir el impacto de E/S del sistema de archivos en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rendimiento. SQLIO puede descargarse desde [http://go.microsoft.com/fwlink/?LinkId=115176](http://go.microsoft.com/fwlink/?LinkId=115176).