---
title: Herramientas de rendimiento | Documentos de Microsoft
description: Investigar los problemas de rendimiento de BizTalk Server con herramientas BizUnit, IOMeter, generador de perfiles de orquestación, analizador del registro, LoadGen y SQL
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d26c17a-3eb9-41a5-b0dc-31b974bf3d9b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5cff86a15aed9a131ed16086d1aebb33739f5f2
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848940"
---
# <a name="performance-tools"></a>Herramientas de rendimiento
En este tema se proporciona información sobre herramientas que puede usar para evaluar el rendimiento de una solución de BizTalk Server. Las herramientas descritas en este tema tienen fines diferentes; Algunos están diseñados para evaluar el rendimiento de extremo a extremo mientras que otras se centran en evaluar el rendimiento de un aspecto determinado de una solución de BizTalk Server.  
 
## <a name="bizunit-and-bizunit-designer"></a>Diseñador de BizUnit y BizUnit  
 BizUnit es un marco de trabajo diseñada para las pruebas automatizadas de soluciones de BizTalk. BizUnit es una herramienta excelente para probar los escenarios de BizTalk Server-to-end. Realización de las pruebas automatizadas de soluciones de BizTalk con BizUnit es el objetivo principal de la [implementar las pruebas automatizadas](../technical-guides/implementing-automated-testing.md) sección de esta guía. Vea [BizUnit](https://github.com/BizUnit/BizUnit).
  
 Diseñador de BizUnit es una interfaz gráfica de usuario que permite la rápida creación de casos de prueba de BizUnit que puede usarse para pruebas unitarias o pruebas de aplicaciones distribuidas del sistema. La herramienta está disponible en [BizUnit diseñador](http://go.microsoft.com/fwlink/?LinkID=117917).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="iometer"></a>IOMeter  
 IOMeter es una herramienta de código abierto que se usa para medir rendimiento de E/S de disco. Vea [ http://www.iometer.org ](http://www.iometer.org/).
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="log-parser"></a>Analizador del registro  
 Analizador del registro es una herramienta eficaz y versátil que proporciona acceso universal de consulta a datos basados en texto, como archivos de registro, archivos XML y archivos CSV, así como orígenes de datos clave en el sistema de operativo Windows® como el registro de eventos, el registro, el sistema de archivos y Active Directory®. Descargar [Log Parser](https://www.microsoft.com/download/details.aspx?id=24659).
  
## <a name="microsoft-biztalk-loadgen"></a>Microsoft BizTalk LoadGen  
 BizTalk LoadGen es una herramienta de generación de carga utilizada para ejecutar pruebas de esfuerzo y rendimiento en el servidor BizTalk Server. Descargar [BizTalk LoadGen 2007 herramientas](https://www.microsoft.com/download/details.aspx?id=14925).
  
## <a name="pathping"></a>Pathping  
 Pathping proporciona información acerca de la posible pérdida de datos en uno o varios saltos de enrutador en la forma de un host de destino. Para ello, pathping envía paquetes de protocolo de mensajes de Control de Internet (ICMP) a cada enrutador en la ruta de acceso. Pathping.exe está disponible con todas las versiones de Windows desde Windows 2000 Server.  
  
## <a name="performance-analysis-of-logs-pal"></a>Análisis de rendimiento de registros (PAL)  
 La herramienta de la PAL se usa para generar un informe basado en HTML que gráficamente gráficos los contadores de rendimiento importante y genera alertas cuando se superan los umbrales de estos contadores. PAL es una herramienta excelente para identificar cuellos de botella en una solución de BizTalk Server para facilitar la asignación de recursos adecuada al optimizar el rendimiento de la solución.  
  
 Para obtener más información acerca de la herramienta de análisis de rendimiento de registros (PAL), consulte [herramienta de análisis de rendimiento de registros (PAL)](https://github.com/clinthuffman/PAL).
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="performance-monitor"></a>Monitor de rendimiento  
 El Monitor de rendimiento muestra los contadores de rendimiento de Windows integrados, bien en tiempo real o como una manera de revisar los datos históricos.  
  
## <a name="relog"></a>Relog  
 La utilidad de volver a registrar se usa para extraer los contadores de rendimiento de registros creados por el Monitor de rendimiento y convertir los datos en otros formatos, como archivos de texto delimitado por tabulaciones (TSV texto), archivos de texto delimitado por comas (CSV de texto), archivos binarios y las bases de datos SQL. Estos datos, a continuación, se pueden analizar y consultan mediante otras herramientas, como el analizador del registro, para generar estadísticas de indicadores clave de rendimiento (KPI). 
  
## <a name="visual-studio---testing-the-application"></a>Visual Studio - probar la aplicación  
 Microsoft Visual Studio Ultimate y Professional incluye pruebas para ayudarle a definir y administrar el trabajo de pruebas usando planes de pruebas. Vea [probar la aplicación](https://docs.microsoft.com/vsts/manual-test/overview).
  
## <a name="visual-studio-profiling-tools"></a>Herramientas de generación de perfiles de Visual Studio  
 Las herramientas de generación de perfiles de Visual Studio le permite generar perfiles de .NET personalizado componentes (componentes de canalización personalizados, los componentes de aplicación auxiliar invocados las orquestaciones o de canalizaciones, los functoids personalizados). Ver, [analizar el rendimiento de la aplicación mediante herramientas de generación de perfiles](https://docs.microsoft.com/visualstudio/profiling/performance-explorer).
  
## <a name="windows-performance-analysis-tools"></a>Herramientas de análisis de rendimiento de Windows  
Herramientas de rendimiento de Windows se ha diseñado para el análisis de una amplia gama de problemas de rendimiento, incluidos los tiempos de inicio de aplicación, problemas de arranque, llamadas a procedimientos aplazados y actividad (DPC e ISR), sistema la capacidad de respuesta de interrupción emite, recursos de aplicación uso y los aluviones de interrupción.  
  
Vea [análisis de rendimiento de Windows](https://docs.microsoft.com/windows-hardware/test/weg/performance-tools).
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>Herramientas de supervisión y optimización del rendimiento de SQL Server  
 SQL Server proporciona varias herramientas para supervisar los eventos de SQL Server y para optimizar el diseño físico de la base de datos. Vea [supervisión de rendimiento y herramientas de optimización](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools). 
  
### <a name="sql-profiler"></a>SQL Profiler  
 Microsoft SQL Server Profiler puede usarse para capturar instrucciones Transact-SQL que se envían a SQL Server y conjuntos de resultados de SQL Server de estas instrucciones. Dado que SQL Server está totalmente integrado con SQL Server, el análisis de una traza del analizador de SQL Server puede ser una herramienta útil para analizar problemas que pueden producirse en BizTalk Server al leer y escribir en las bases de datos de SQL Server. Vea [mediante SQL Server Profiler](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler-templates-and-permissions).
  
> [!IMPORTANT]  
>  Hay una sobrecarga considerable asociada con el analizador de SQL en ejecución. Por lo tanto, SQL Profiler es ideal para su uso en entornos de desarrollo o de prueba. Si utiliza a SQL Profiler para solucionar problemas de un entorno de producción, tenga en cuenta los costes generales asociados y limitar el uso del analizador de SQL en consecuencia.  
> 
>  Cuando se usa a SQL Profiler para capturar instrucciones Transact-SQL, configurar el analizador de SQL para generar una salida en una unidad local en lugar de una unidad de encontrarse en un recurso compartido de red remota u otro dispositivo lenta, por ejemplo, un dispositivo de memoria USB local.  
  
### <a name="sql-trace"></a>Seguimiento de SQL  
 SQL Server proporciona procedimientos almacenados del sistema de Transact-SQL para crear seguimientos en una instancia de motor de base de datos de SQL Server. Estos procedimientos almacenados del sistema pueden utilizarse desde sus propias aplicaciones para crear seguimientos manualmente, en lugar de usar SQL Server Profiler. Esto permite escribir aplicaciones personalizadas específicas para las necesidades de la organización. Vea [seguimiento de SQL](https://docs.microsoft.com/sql/relational-databases/sql-trace/sql-trace). 
  
> [!NOTE]  
>  Al utilizar seguimiento de SQL para capturar instrucciones Transact-SQL, configurar el seguimiento de SQL para generar la salida a una unidad local en lugar de una unidad que se encuentra en un recurso compartido de red remota u otro dispositivo lenta, como una unidad flash USB.  
  
### <a name="sql-activity-monitor"></a>Monitor de actividad SQL  
Monitor de actividad de SQL Server proporciona información acerca de los procesos de SQL Server y cómo estos procesos afectan a la instancia actual de SQL Server. Vea [Monitor de actividad](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor), y [Cómo: abrir el Monitor de actividad (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio). 
  
### <a name="sql-server-data-collection"></a>Recopilación de datos SQL Server  
SQL Server proporciona un recopilador de datos que puede usar para obtener y guardar los datos recopilados de varios orígenes. El recopilador de datos permite usar contenedores de recopilación de datos, lo que permite determinar el ámbito y la frecuencia de recopilación de datos en un equipo que ejecuta SQL Server. Vea [la recopilación de datos](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection).
  
### <a name="sqlio"></a>SQLIO  
 La herramienta SQLIO fue desarrollada por Microsoft para evaluar la capacidad de E/S de una configuración determinada. Como indica el nombre de la herramienta, SQLIO es una valiosa herramienta para medir el impacto de E/S del sistema de archivos en el rendimiento de SQL Server. Descargar [SQLIO](https://www.microsoft.com/download/details.aspx?id=20163).
  
## <a name="see-also"></a>Vea también  
 [Búsqueda y eliminación de cuellos de botella](../technical-guides/finding-and-eliminating-bottlenecks.md)