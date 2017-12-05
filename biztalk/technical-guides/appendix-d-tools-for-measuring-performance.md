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
ms.openlocfilehash: 19953e021a2416f777d9b28c14b1eb8516c70c81
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="appendix-d-tools-for-measuring-performance"></a>Apéndice D: herramientas para medir el rendimiento
En este tema se describe varias herramientas que pueden utilizar para supervisar y evaluar el rendimiento de un entorno de BizTalk Server.  
  
## <a name="performance-analysis-of-logs-pal-tool"></a>Herramienta de análisis de registros (PAL) de rendimiento  
 El [herramienta PAL](https://github.com/clinthuffman/PAL) se usa para generar un informe basado en HTML que muestra gráficamente importante los contadores de monitor de rendimiento y genera alertas cuando se superan los umbrales de estos contadores. PAL es una herramienta excelente para identificar cuellos de botella en una solución de BizTalk Server para facilitar la asignación de recursos adecuada al optimizar el rendimiento de la solución. 
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="performance-monitor"></a>Monitor de rendimiento  
 El Monitor de rendimiento muestra los contadores de rendimiento de Windows integrados, bien en tiempo real o como una manera de revisar los datos históricos.  
  
## <a name="log-parser"></a>Analizador del registro  
 Analizador del registro es una herramienta eficaz y versátil que proporciona acceso universal de consulta a datos basados en texto, como archivos de registro, archivos XML y archivos CSV, así como orígenes de datos clave en el sistema de operativo Windows® como el registro de eventos, el registro, el sistema de archivos y Active Directory®. Descargar [Log Parser](https://www.microsoft.com/download/details.aspx?id=24659).
  
## <a name="relog"></a>Relog  
 La utilidad de volver a registrar se usa para extraer los contadores de rendimiento de registros creados por el Monitor de rendimiento y convertir los datos en otros formatos, como archivos de texto delimitado por tabulaciones (TSV texto), archivos de texto delimitado por comas (CSV de texto), archivos binarios y las bases de datos SQL. Estos datos, a continuación, se pueden analizar y consultan mediante otras herramientas, como el analizador del registro, para generar estadísticas de indicadores clave de rendimiento (KPI). 
  
## <a name="loadgen"></a>LoadGen  
 BizTalk LoadGen 2007 es una herramienta de generación de carga utilizada para ejecutar pruebas de esfuerzo y rendimiento en el servidor BizTalk Server. Descargar [BizTalk LoadGen 2007 herramientas](https://www.microsoft.com/download/details.aspx?id=14925).
  
## <a name="visual-studio-team-system-load-testing"></a>Pruebas de carga de Visual Studio Team System  
 Visual Studio Team System (VSTS) proporciona una herramienta para crear y ejecutar pruebas de carga. Vea [probar la aplicación](https://docs.microsoft.com/vsts/manual-test/overview).
  
## <a name="bizunit"></a>BizUnit  
 BizUnit es un marco de trabajo diseñada para las pruebas automatizadas de soluciones de BizTalk Server. BizUnit es una herramienta excelente para probar los escenarios de BizTalk Server-to-end. Vea [BizUnit](https://github.com/BizUnit/BizUnit).
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="iometer"></a>IOMeter  
 IOMeter es una herramienta de código abierto que se usa para medir rendimiento de E/S de disco. Vea [http://www.iometer.org](http://www.iometer.org/).
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  

## <a name="pathping"></a>Pathping  
 Pathping proporciona información acerca de la posible pérdida de datos en uno o varios saltos de enrutador en la forma de un host de destino. Para ello, pathping envía paquetes de protocolo de mensajes de Control de Internet (ICMP) a cada enrutador en la ruta de acceso. 
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>Herramientas de supervisión y optimización del rendimiento de SQL Server  
SQL Server proporciona varias herramientas para supervisar los eventos de SQL Server y para optimizar el diseño físico de la base de datos. Vea [supervisión de rendimiento y herramientas de optimización](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools). 
  
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