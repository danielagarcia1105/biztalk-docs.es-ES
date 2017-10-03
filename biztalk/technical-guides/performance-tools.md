---
title: Herramientas de rendimiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d26c17a-3eb9-41a5-b0dc-31b974bf3d9b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c53894ca4dcf1b1541c020e14a83542a7ce56d56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="performance-tools"></a>Herramientas de rendimiento
En este tema se proporciona información sobre herramientas que puede usar para evaluar el rendimiento de una solución de BizTalk Server. Las herramientas descritas en este tema tienen fines diferentes; Algunos están diseñados para evaluar el rendimiento de extremo a extremo mientras que otras se centran en evaluar el rendimiento de un aspecto determinado de una solución de BizTalk Server.  
  
## <a name="biztalk-server-orchestration-profiler"></a>Generador de perfiles de orquestación de BizTalk Server  
 El generador de perfiles de orquestación de BizTalk Server sirve para ver los datos de seguimiento para un período de tiempo especificado de orquestación y es útil para determinar donde existen cuellos de botella de rendimiento en las orquestaciones.  
  
 Para obtener más información sobre el generador de perfiles de orquestación de BizTalk Server, vea [analizador de orquestación de BizTalk Server 2006](http://go.microsoft.com/fwlink/?LinkId=102209) (http://go.microsoft.com/fwlink/?LinkId=102209).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad. Tenga en cuenta que esta utilidad se diseñó para funcionar con BizTalk Server 2006 y, por tanto, podrían no funcionar según lo previsto en BizTalk Server 2010.  
  
## <a name="bizunit-30-and-bizunit-designer"></a>BizUnit 3.0 y el Diseñador de BizUnit  
 BizUnit es un marco de trabajo diseñada para las pruebas automatizadas de soluciones de BizTalk. BizUnit es una herramienta excelente para probar los escenarios de BizTalk Server-to-end. Realización de las pruebas automatizadas de soluciones de BizTalk con BizUnit es el objetivo principal de la [implementar las pruebas automatizadas](../technical-guides/implementing-automated-testing.md) sección de esta guía. Para obtener más información acerca de BizUnit 3.0, consulte [BizUnit - marco de trabajo para automatizar pruebas de sistemas distribuidos](http://go.microsoft.com/fwlink/?LinkID=85168) (http://go.microsoft.com/fwlink/?LinkID=85168).  
  
 Diseñador de BizUnit es una interfaz gráfica de usuario que permite la rápida creación de casos de prueba de BizUnit que puede usarse para pruebas unitarias o pruebas de aplicaciones distribuidas del sistema. La herramienta está disponible en [BizUnit diseñador](http://go.microsoft.com/fwlink/?LinkID=117917) (http://go.microsoft.com/fwlink/?LinkID=117917).  
  
> [!IMPORTANT]  
>  Al redactar esta guía, los casos de prueba generados por el diseñador BizUnit 1.x sólo son compatibles con BizUnit 2.x.  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="iometer"></a>IOMeter  
 IOMeter es una herramienta de código abierto que se usa para medir rendimiento de E/S de disco. Para obtener más información acerca de IOMeter, consulte [http://www.iometer.org](http://go.microsoft.com/fwlink/?LinkId=122412) (http://go.microsoft.com/fwlink/?LinkId=122412).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="log-parser"></a>Analizador del registro  
 Analizador del registro es una herramienta eficaz y versátil que proporciona acceso universal de consulta a datos basados en texto, como archivos de registro, archivos XML y archivos CSV, así como orígenes de datos clave en el sistema de operativo Windows® como el registro de eventos, el registro, el sistema de archivos y Active Directory®. Analizador del registro está disponible para su descarga en [Log Parser 2.2](http://go.microsoft.com/fwlink/?LinkID=100882) (http://go.microsoft.com/fwlink/?LinkID=100882).  
  
## <a name="microsoft-biztalk-loadgen-2007"></a>Microsoft BizTalk LoadGen 2007  
 BizTalk LoadGen 2007 es una herramienta de generación de carga utilizada para ejecutar el rendimiento y pruebas de esfuerzo en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
 Para obtener más información acerca de la herramienta de Microsoft BizTalk LoadGen 2007, consulte [herramientas de Microsoft BizTalk LoadGen 2007](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841).  
  
## <a name="pathping"></a>Pathping  
 Pathping proporciona información acerca de la posible pérdida de datos en uno o varios saltos de enrutador en la forma de un host de destino. Para ello, pathping envía paquetes de protocolo de mensajes de Control de Internet (ICMP) a cada enrutador en la ruta de acceso. Pathping.exe está disponible con todas las versiones de Windows desde Windows 2000 Server.  
  
## <a name="performance-analysis-of-logs-pal"></a>Análisis de rendimiento de registros (PAL)  
 La herramienta de la PAL se usa para generar un informe basado en HTML que gráficamente gráficos los contadores de rendimiento importante y genera alertas cuando se superan los umbrales de estos contadores. PAL es una herramienta excelente para identificar cuellos de botella en una solución de BizTalk Server para facilitar la asignación de recursos adecuada al optimizar el rendimiento de la solución.  
  
 Para obtener más información acerca de la herramienta de análisis de rendimiento de registros (PAL), consulte [herramienta de análisis de rendimiento de registros (PAL)](http://go.microsoft.com/fwlink/?LinkID=98098) (http://go.microsoft.com/fwlink/?LinkID=98098).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="performance-monitor"></a>Monitor de rendimiento  
 El Monitor de rendimiento muestra los contadores de rendimiento de Windows integrados, bien en tiempo real o como una manera de revisar los datos históricos.  
  
## <a name="relog"></a>Relog  
 La utilidad de volver a registrar se usa para extraer los contadores de rendimiento de registros creados por el Monitor de rendimiento y convertir los datos en otros formatos, como archivos de texto delimitado por tabulaciones (TSV texto), archivos de texto delimitado por comas (CSV de texto), archivos binarios y las bases de datos SQL. Estos datos, a continuación, se pueden analizar y consultan mediante otras herramientas, como el analizador del registro, para generar estadísticas de indicadores clave de rendimiento (KPI). Se proporciona la utilidad de volver a registrar con [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] y versiones posteriores.  
  
## <a name="visual-studio-2010---testing-the-application"></a>Visual Studio 2010 - probar la aplicación  
 Microsoft Visual Studio 2010 Ultimate y Visual Studio Test Professional 2010 ahora incluyen una nueva aplicación denominada Microsoft Test Manager para ayudarle a definir y administrar el trabajo de pruebas usando planes de pruebas. Para obtener más información sobre cómo trabajar con pruebas de carga, consulte [probar la aplicación](http://go.microsoft.com/fwlink/?LinkID=205342) (http://go.microsoft.com/fwlink/?LinkID=205342).  
  
## <a name="visual-studio-2010-profiling-tools"></a>Herramientas de generación de perfiles de Visual Studio 2010  
 Las herramientas de generación de perfiles de Visual Studio le permite generar perfiles de .NET personalizado componentes (componentes de canalización personalizados, los componentes de aplicación auxiliar invocados las orquestaciones o de canalizaciones, los functoids personalizados). Para obtener más información sobre herramientas de generación de perfiles de Visual Studio, vea [análisis de rendimiento de la aplicación mediante herramientas de generación de perfiles](http://go.microsoft.com/fwlink/?LinkID=210555) (http://go.microsoft.com/fwlink/?LinkID=210555).  
  
## <a name="windows-performance-analysis-tools"></a>Herramientas de análisis de rendimiento de Windows  
 Herramientas de rendimiento de Windows se ha diseñado para el análisis de una amplia gama de problemas de rendimiento, incluidos los tiempos de inicio de aplicación, problemas de arranque, llamadas a procedimientos aplazados y actividad (DPC e ISR), sistema la capacidad de respuesta de interrupción emite, recursos de aplicación uso y los aluviones de interrupción.  
  
 Para obtener más información acerca de las herramientas de análisis de rendimiento de Windows, vea [análisis de rendimiento de Windows](http://go.microsoft.com/fwlink/?LinkId=139763) (http://go.microsoft.com/fwlink/?LinkId=139763).  
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>Herramientas de supervisión y optimización del rendimiento de SQL Server  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]proporciona varias herramientas para supervisar los eventos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y para optimizar el diseño físico de la base de datos. Estas herramientas se describen en la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] tema libros en pantalla [herramientas para la supervisión de rendimiento y optimización](http://go.microsoft.com/fwlink/?LinkId=146357) (http://go.microsoft.com/fwlink/?LinkId=146357). Información sobre herramientas específicas que se usan para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] a continuación se proporciona supervisión y optimización del rendimiento:  
  
### <a name="sql-profiler"></a>SQL Profiler  
 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] generador de perfiles puede usarse para capturar instrucciones Transact-SQL que se envían a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] conjuntos de resultados de estas instrucciones. Dado que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] está totalmente integrado con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], el análisis de un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] traza del analizador puede ser una herramienta útil para analizar problemas que pueden producirse en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] al leer y escribir en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos. Para obtener información sobre cómo usar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler, vea el [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] tema libros en pantalla [utilizando SQL Server Profiler](http://go.microsoft.com/fwlink/?linkid=104423) (http://go.microsoft.com/fwlink/?linkid=104423).  
  
> [!IMPORTANT]  
>  Hay una sobrecarga considerable asociada con el analizador de SQL en ejecución. Por lo tanto, SQL Profiler es ideal para su uso en entornos de desarrollo o de prueba. Si utiliza a SQL Profiler para solucionar problemas de un entorno de producción, tenga en cuenta los costes generales asociados y limitar el uso del analizador de SQL en consecuencia.  
  
> [!NOTE]  
>  Cuando se usa a SQL Profiler para capturar instrucciones Transact-SQL, configurar el analizador de SQL para generar una salida en una unidad local en lugar de una unidad de encontrarse en un recurso compartido de red remota u otro dispositivo lenta, por ejemplo, un dispositivo de memoria USB local.  
  
### <a name="sql-trace"></a>Seguimiento de SQL  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Proporciona procedimientos almacenados del sistema de Transact-SQL para crear seguimientos en una instancia de motor de base de datos de SQL Server. Estos procedimientos almacenados del sistema pueden utilizarse desde sus propias aplicaciones para crear seguimientos manualmente, en lugar de usar SQL Server Profiler. Esto permite escribir aplicaciones personalizadas específicas para las necesidades de la organización. Para obtener más información acerca del uso de seguimiento de SQL, vea el [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] tema libros en pantalla [Introducción a SQL Trace](http://go.microsoft.com/fwlink/?LinkId=146354) (http://go.microsoft.com/fwlink/?LinkId=146354).  
  
> [!NOTE]  
>  Al utilizar seguimiento de SQL para capturar instrucciones Transact-SQL, configurar el seguimiento de SQL para generar la salida a una unidad local en lugar de una unidad que se encuentra en un recurso compartido de red remota u otro dispositivo lenta, como una unidad flash USB.  
  
### <a name="sql-activity-monitor"></a>Monitor de actividad SQL  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Monitor de actividad proporciona información acerca de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] procesos y cómo estos procesos afectan a la instancia actual de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información acerca de [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Monitor de actividad, consulte la [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] tema libros en pantalla [Monitor de actividad](http://go.microsoft.com/fwlink/?LinkId=146355) (http://go.microsoft.com/fwlink/?LinkId=146355). Para obtener información acerca de cómo abrir el Monitor de actividad de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio, consulte el [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] tema libros en pantalla [Cómo: abrir el Monitor de actividad (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094).  
  
### <a name="sql-server-2008-r2-data-collection"></a>Recopilación de datos SQL Server 2008 R2  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] proporciona un recopilador de datos que puede utilizar para obtener y guardar datos recopilados de varios orígenes. El recopilador de datos permite usar contenedores de recopilación de datos, que permiten determinar el ámbito y la frecuencia de recopilación de datos en un equipo que está ejecutando [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]. Para obtener más información acerca de cómo implementar [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] recopilación de datos, vea el [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] tema libros en pantalla [la recopilación de datos](http://go.microsoft.com/fwlink/?LinkId=146356) (http://go.microsoft.com/fwlink/?LinkId=146356).  
  
### <a name="sqlio"></a>SQLIO  
 La herramienta SQLIO fue desarrollada por Microsoft para evaluar la capacidad de E/S de una configuración determinada. Como indica el nombre de la herramienta, SQLIO es una herramienta útil para medir el impacto de E/S del sistema de archivos en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rendimiento. SQLIO puede descargarse desde [herramienta de prueba comparativa de subsistema de disco de SQLIO](http://go.microsoft.com/fwlink/?LinkId=115176) (http://go.microsoft.com/fwlink/?LinkId=115176).  
  
## <a name="see-also"></a>Vea también  
 [Buscar y eliminar los cuellos de botella](../technical-guides/finding-and-eliminating-bottlenecks.md)