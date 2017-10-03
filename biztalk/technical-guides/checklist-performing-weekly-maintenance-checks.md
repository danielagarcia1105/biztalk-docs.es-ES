---
title: "Lista de comprobación: Realización de comprobaciones de mantenimiento semanal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b13e43ba-4bac-4d4b-aaf8-46d60c0561bf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb754c0cfd7f153e4cefa3cd610ef1633ef1e073
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-performing-weekly-maintenance-checks"></a>Lista de comprobación: Realización de comprobaciones de mantenimiento semanal
En este tema se describe los pasos necesarios para realizar las comprobaciones de mantenimiento de la confiabilidad, la administración, la seguridad y el rendimiento de cada semana un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Asegúrese de que cada host tiene una instancia que se ejecuta en al menos dos servidores físicos de BizTalk (comprobación de confiabilidad).|[Alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|Asegúrese de que cada ubicación de recepción es redundante (comprobación de confiabilidad).|[El escalado de Hosts de recepción](../technical-guides/scaling-out-receiving-hosts.md)|  
|Asegúrese de que el servicio Agente SQL Server se ejecuta en el servidor de SQL server (comprobación de administración).|-   [Cómo: iniciar el Agente SQL Server](http://go.microsoft.com/fwlink/p/?LinkId=154672) (http://go.microsoft.com/fwlink/p/?LinkId=154672).<br />-   [Agente SQL Server](http://go.microsoft.com/fwlink/p/?LinkId=106728) (http://go.microsoft.com/fwlink/p/?LinkId=106728).|  
|Asegúrese de que todos los trabajos de SQL Server relacionadas con BizTalk Server estén funcionando correctamente (comprobación de administración).|[Supervisión de trabajos del Agente SQL Server](../technical-guides/monitoring-sql-server-agent-jobs.md)<br /><br /> Si no se ejecutan los trabajos del Agente SQL Server, se verá afectado el rendimiento del sistema con el tiempo. Para obtener más información sobre el Agente SQL Server trabajos que proporciona BizTalk Server para ayudar a administrar las bases de datos de BizTalk Server, consulte [estructura de base de datos y trabajos](http://go.microsoft.com/fwlink/p/?LinkID=153451) (http://go.microsoft.com/fwlink/p/?LinkID=153451).|  
|Asegúrese de que los trabajos de SQL Server responsables de la copia de seguridad de bases de datos de BizTalk Server se ejecutan con normalidad (comprobación de administración).|-   [Cómo configurar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/p/?LinkID=153813) (http://go.microsoft.com/fwlink/p/?LinkID=153813)<br />-   [Cómo programar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/p/?LinkId=154674) (http://go.microsoft.com/fwlink/p/?LinkId=154674)|  
|Asegúrese de que se instalan las actualizaciones de seguridad más recientes (comprobación de seguridad).|Sitio de Microsoft Update en [http://update.microsoft.com/microsoftupdate/v6/default.aspx](http://update.microsoft.com/microsoftupdate/v6/default.aspx)|  
|Analizar el rendimiento semanal supervisar los registros en la línea de base y los umbrales (comprobación de rendimiento).|-   [Usar el análisis de rendimiento de la herramienta de registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)<br />-   [Solución de problemas de rendimiento de los clientes3](../technical-guides/troubleshooting-performance-issues3.md)|  
|Asegúrese de que el sistema no está experimentando frecuente crecimiento automático de bases de datos de BizTalk Server (comprobación de rendimiento).|-   [Definir los valores de crecimiento automático de las bases de datos](../technical-guides/defining-auto-growth-settings-for-databases.md)<br />-   [Directrices de ajuste de tamaño de la base de datos de seguimiento](http://go.microsoft.com/fwlink/p/?LinkId=154677) (http://go.microsoft.com/fwlink/p/?LinkId=154677).<br />-   [Identificar cuellos de botella en el nivel de base de datos](http://go.microsoft.com/fwlink/p/?LinkId=154678) (http://go.microsoft.com/fwlink/p/?LinkId=154678).<br />-   [La inicialización de archivos de base de datos](http://go.microsoft.com/fwlink/p/?LinkID=101579) (http://go.microsoft.com/fwlink/p/?LinkID=101579).<br />-   [Llevar a cabo procedimientos de mantenimiento SQL Server](~/technical-guides/checklist-configuring-sql-server.md)|  
|Ejecutar a SQL Server Profiler durante la carga alta para comprobar si los largos tiempos de respuesta y el uso elevado de recursos (comprobación de rendimiento).|[Usar SQL Server Profiler](http://go.microsoft.com/fwlink/p/?LinkID=106720) (http://go.microsoft.com/fwlink/p/?LinkID=106720).|  
|Asegúrese de que el procesamiento por lotes de mensajes para todos los adaptadores es apropiado para el consumo de recursos o la latencia (comprobación de rendimiento).|-   [Configurar el procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md)<br />-   [Cómo diseñar un adaptador de rendimiento](http://go.microsoft.com/fwlink/p/?LinkId=154679) (http://go.microsoft.com/fwlink/p/?LinkId=154679).|  
|Asegúrese de que el umbral de mensajes de gran tamaño es adecuado para el consumo de recursos (comprobación de rendimiento).|[Cómo BizTalk Server procesa los mensajes de gran tamaño](http://go.microsoft.com/fwlink/p/p/?LinkId=154680) (http://go.microsoft.com/fwlink/p/p/?LinkId=154680).|  
|Archivar archivos de copia de seguridad y especifique los equipos apropiados para copia de seguridad|Para evitar la posible pérdida de datos, debe especificar un equipo para la copia de seguridad que es distinto del equipo con los datos originales y para \<ruta de acceso de destino > debe especificar un equipo para almacenar los registros de base de datos que es diferente de la equipo con los registros de base de datos original.<br /><br /> Para obtener más información sobre los procedimientos recomendados para la copia de seguridad, consulte [prácticas recomendadas para realizar copias de seguridad y restaurar bases de datos](http://go.microsoft.com/fwlink/p/p/?LinkID=151391) (http://go.microsoft.com/fwlink/p/p/?LinkID=151391).|  
  
## <a name="see-also"></a>Vea también  
 [Tareas rutinarias de supervisión](../technical-guides/routine-monitoring-tasks.md)