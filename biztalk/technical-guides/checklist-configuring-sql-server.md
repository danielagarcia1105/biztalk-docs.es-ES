---
title: "Lista de comprobación: Configurar SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edd20f24-8a72-40b7-abee-81fbd3ceefda
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6c67fcdee26afd6ec9bb1016e86a98b1cf26e8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="checklist-configuring-sql-server"></a>Lista de comprobación: Configurar SQL Server
Pasos que deben seguirse al preparar SQL Server para usan en un entorno de producción de BizTalk Server.    
 
<a name="BKMK_Config"></a>   
## <a name="configuring-sql-server"></a>Configuración de SQL Server  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Supervisar y reducir la contención de E/S de disco de archivos de base de datos de BizTalk Server.|-Se recomienda supervisar de forma proactiva el uso de E/S de disco para los discos que almacenan los archivos de registro de transacciones y de datos.<br />-Se recomiendan que los archivos de datos y archivos de registro de transacciones para cada uno de ellos pueden colocarse en unidades dedicadas para reducir la probabilidad de contención de E/S de disco se convierta en un problema.<br />-Puede reducir la contención de E/S de disco mediante la separación de las bases de datos de cuadro de mensaje y seguimiento (DTA) y mediante la separación de los archivos de base de datos y archivos de registro de transacciones en discos físicos diferentes.<br /><br /> Para obtener más información, vea [supervisión y reducir contención de E/S de base de datos](monitoring-and-reducing-database-i-o-contention.md)|  
|Asegúrese de que SQL Server está configurado en las particiones de disco correctamente alineados|Correctamente alineados disco particiones pudieron dar lugar a importante disminución de la latencia y mejorar el rendimiento de SQL Server, lo que a su vez mejora el rendimiento de BizTalk Server. Por el contrario, las particiones de disco no alineado pueden afectar negativamente al rendimiento de E/S, lo que degradar el rendimiento de SQL Server y BizTalk Server.<br /><br /> Para obtener más información acerca de las particiones de disco cómo correctamente alineados positivamente puede afectar al rendimiento, consulte [alineación de prácticas recomendadas para SQL Server para la partición de disco](http://go.microsoft.com/fwlink/?LinkId=154073).|  
|Mantener los eventos que supervisar con el analizador de SQL Server|Usar a SQL Server Profiler para supervisar sólo los eventos en el que esté interesado. Si seguimientos son demasiado grandes, puede filtrar según la información que desee, por lo que se recopila sólo un subconjunto de los datos del evento. Si se supervisan demasiados eventos, aumentará la sobrecarga del servidor y el proceso de supervisión, y podría hacer que el archivo o la tabla de seguimiento crezcan demasiado, especialmente cuando el proceso de supervisión se realiza durante un período prolongado de tiempo.|  
|Supervisar y reducir la contención de E/S de disco del archivo de registro DTC.|[Supervisión y reducir la contención de E/S de disco del archivo de registro DTC](monitoring-and-reducing-dtc-log-file-disk-i-o-contention.md)|  
|Proporcionar una alta disponibilidad para las bases de datos de SQL Server.|[Planificación de la disponibilidad de la base de datos](planning-for-database-availability.md)|  
|Revise la configuración activo/activo del clúster de SQL Server para escenarios de conmutación por error.|[Revisar y probar la configuración de clúster de servidores SQL Server para escenarios de conmutación por error](reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)|  
|Usar configuración predeterminada para:<br /><br /> -Max Degree of Parallelism (MDOP).<br />-Estadísticas SQL Server en la base de datos de cuadro de mensajes de BizTalk Server.<br />: Vuelve a generar el índice de base de datos SQL Server y de la desfragmentación.|[Configuración de SQL Server que no se debe cambiar](sql-server-settings-that-should-not-be-changed.md)|  
|Habilitar la marca de seguimiento 1118 (TF1118) como un parámetro de inicio para todas las instancias de SQL Server.|Implementar TF1118 le ayuda a reducir la contención en todas las instancias de SQL Server mediante la eliminación de casi todas las asignaciones de páginas individuales. Para más información, consulte Microsoft Knowledge Base el artículo [mejoras de simultaneidad para la base de datos tempdb](https://support.microsoft.com/en-us/help/328551/concurrency-enhancements-for-the-tempdb-database). <br/><br/>**Nota:** para obtener más información sobre, consulte TF1118 [conceptos erróneos alrededor de TF1118](https://www.sqlskills.com/blogs/paul/misconceptions-around-tf-1118/). Tenga en cuenta que el contenido en este vínculo no es propiedad de Microsoft y Microsoft no garantiza la precisión del contenido.|  
|Dividir la base de datos tempdb en varios archivos de datos del mismo tamaño en cada instancia de SQL Server utilizado por BizTalk Server.|Asegúrese de que los archivos de datos que se usan para tempdb son del mismo tamaño. Esto es importante porque el algoritmo de relleno proporcional utilizado por SQL Server se basa en el tamaño de los archivos de datos. Si se crean archivos de datos con diferentes tamaños, el algoritmo de relleno proporcional utilizará el archivo más grande más para las asignaciones de mapa de asignación Global (GAM), en lugar de repartir las asignaciones entre todos los archivos, evitando así el propósito de crear varios archivos de datos. Como norma general, cree un archivo de datos para cada CPU en el servidor y, a continuación, ajuste el número de archivos hacia arriba o hacia abajo, según sea necesario. Tenga en cuenta que una CPU de doble núcleo se cuenta como dos CPU. En cualquier caso, el número de archivos de datos no debe ser mayor que 8 independientemente del número de núcleos adicionales están disponibles en el equipo. Para obtener más información acerca de los archivos de tempdb, vea [optimizar el rendimiento de tempdb](https://docs.microsoft.com/sql/relational-databases/databases/tempdb-database).|  
|Establecer el mínimo y instance(s) de memoria máxima del servidor en los mismos valores en el servidor SQL Server que hospedan las bases de datos de BizTalk Server.|Los equipos que ejecutan a SQL Server que hospedan las bases de datos de BizTalk Server deben estar dedicados a ejecutar SQL Server. Cuando los equipos que ejecutan SQL Server que hospedan el servidor BizTalk Server las bases de datos **son** dedicados a la ejecución de SQL Server, se recomienda que el 'min server memory' y 'max server memory' establecer para especificar opciones para cada instancia de SQL Server la cantidad fija de memoria para asignar a SQL Server. En este caso, debe establecer el 'min server memory' y 'max server memory' en el mismo valor (es igual a la cantidad máxima de memoria física que se va a usar SQL Server). Esto disminuirá la sobrecarga que utilizaría en caso contrario, SQL Server administrar dinámicamente estos valores. Ejecute los siguientes comandos de T-SQL en cada equipo que ejecuta SQL Server para especificar la cantidad fija de memoria para asignar a SQL Server:<br /><br /> sp_configure ' Max Server memory (MB)', (tamaño máximo en MB) de sp_configure 'Min Server memory (MB),' (min tamaño en MB)<br /><br /> Antes de configurar la cantidad de memoria para SQL Server, determine la configuración de memoria apropiada restando la memoria necesaria para Windows Server desde la memoria física total. Se trata de la cantidad máxima de memoria que puede asignar a SQL Server. **Nota:** si los equipos que ejecutan SQL Server que hospedan el servidor BizTalk Server las bases de datos también hospedan el secreto principal de Enterprise Single Sign-On, como se describe en el tema [el servidor secreto principal de agrupación en clústeres](clustering-the-master-secret-server.md) , a continuación, puede que necesite Para ajustar este valor para asegurarse de que hay suficiente memoria disponible para ejecutar el servicio de inicio de sesión único de empresa.|  
|Cuenta el tamaño de base de datos de seguimiento de BizTalk|-Al determinar el tamaño de los mensajes en la base de datos de seguimiento de BizTalk (DTA), agregue el tamaño medio del contexto del mensaje para el tamaño del mensaje si resulta significativo en comparación con el tamaño del mensaje.<br />-Para limitar el tamaño de los mensajes en la base de datos de seguimiento de BizTalk, limite el número de propiedades que se promoción.<br />-Si está habilitada la opción del depurador de orquestaciones, tenga en cuenta que el estado de cada forma en la orquestación se guarda en la base de datos de seguimiento de BizTalk.|  
  
<a name="BKMK_Maintain"></a>   
## <a name="performing-sql-server-maintenance-procedures"></a>Llevar a cabo procedimientos de mantenimiento SQL Server  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Definir la configuración de crecimiento automático de las bases de datos de BizTalk Server.|-Crecimiento automático base de datos debe establecerse en un número fijo de megabytes en lugar de un porcentaje, especialmente para el cuadro de mensajes y las bases de datos de seguimiento. Dependiendo de la aplicación de BizTalk Server y el rendimiento, el cuadro de mensajes y las bases de datos de seguimiento pueden ser bastante grandes. Si el crecimiento automático está establecido en un porcentaje, a continuación, el crecimiento automático puede ser sustancial así.<br />-Inicialización de archivos instantánea puede reducir considerablemente el impacto en el rendimiento de una operación de crecimiento de archivos.<br />-Idealmente, el tamaño de los archivos de compatibilidad con los grupos de archivos debe ser preasignado y si es posible, se establece en un tamaño estático.<br /><br /> Para obtener más información, consulte [definir la configuración de crecimiento automático para las bases de datos](defining-auto-growth-settings-for-databases.md).|  
|Hacer copia de seguridad de las bases de datos de BizTalk Server|-Se recomienda ejecutar el trabajo de copia de seguridad de BizTalk Server para evitar que los registros de transacciones de la base de datos de BizTalk Server crezca de forma ilimitada.<br />-Debe restaurar todo el entorno de BizTalk Server de forma periódica y detenidamente debe documentar el proceso.<br />-Se recomienda que no se archiven los archivos de copia de seguridad anteriores.<br /><br /> Para obtener más información, consulte [realizar una copia de seguridad de bases de datos](backing-up-databases.md).|  
|Supervisar los trabajos del agente de SQL Server de BizTalk.|Supervisar el estado de estos trabajos y asegúrese de que se ejecutan sin errores. Para obtener más información, consulte [trabajos del agente de supervisión de SQL Server](monitoring-sql-server-agent-jobs.md).|  
|Permitir que BizTalk Server seguimiento y el archivado|El trabajo del agente de SQL "DTA purgar y archivar" archiva y purga los datos antiguos de la base de seguimiento de BizTalk, evitando crezca sin control. Esto es esencial para un sistema de BizTalk Server correcto. Para obtener más información, consulte [purga y archivo de datos de seguimiento](purging-and-archiving-tracking-data.md).|  
  
<a name="BKMK_Backup"></a>   
## <a name="backing-up-the-biztalk-server-databases"></a>Copia de seguridad de las bases de datos de servidor BizTalk Server  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Compruebe que el trabajo de agente de SQL Server de BizTalk de copia de seguridad está configurado.|Vea [configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|Configurar el trabajo de copia de seguridad agente de SQL Server de BizTalk para eliminar archivos de copia de seguridad que sean más antiguos que el número de días especificado por el @DaysToKeep variable. Si no se eliminan los archivos de copia de seguridad pueden crecer sin enlazar con el tiempo que se llene los discos que contienen los archivos de copia de seguridad y causar problemas relacionados con poco espacio en disco.|Vea [configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|Compruebe que el trabajo de agente de SQL Server de BizTalk de copia de seguridad está habilitado y en ejecución.|[Supervisión de trabajos del Agente SQL Server](monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Disaster"></a>   
## <a name="using-sql-server-log-shipping-for-disaster-recovery"></a>Usar para la recuperación ante desastres de trasvase de registros SQL Server  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Compruebe que los servidores de recuperación ante desastres tienen la capacidad para administrar la carga de producción.|Consulte [con recuperación ante desastres de trasvase de registros de servidor BizTalk Server](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|Asegúrese de que los detalles de su rutina de recuperación ante desastres están bien documentados.|Consulte [con recuperación ante desastres de trasvase de registros de servidor BizTalk Server](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|Como parte de regular pruebas, práctica conmutación por error en el sitio de recuperación ante desastres, especialmente como nuevo de BizTalk se colocan las aplicaciones en producción.|Consulte [con recuperación ante desastres de trasvase de registros de servidor BizTalk Server](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
  
<a name="BKMK_Jobs"></a>   
## <a name="monitoring-biztalk-server-sql-agent-jobs"></a>Supervisión de trabajos del Agente SQL Server de BizTalk  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Compruebe que se está ejecutando el servicio Agente SQL Server.|Vea [supervisión de trabajos del Agente SQL Server](monitoring-sql-server-agent-jobs.md)|  
|Compruebe que los trabajos de agente SQL Server instalados por BizTalk Server están habilitado y ejecutándose correctamente.|Vea [supervisión de trabajos del Agente SQL Server](monitoring-sql-server-agent-jobs.md)|  
|Compruebe que se completan los trabajos del agente de SQL Server de BizTalk de forma puntual.|Vea [supervisión de trabajos del Agente SQL Server](monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Purge"></a>   
## <a name="purging-and-archiving-tracking-data"></a>Depuración y el archivo de datos de seguimiento  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Asegúrese de que el trabajo del Agente SQL "DTA purgar y archivar" está correctamente configurado, habilitado y se completan correctamente.|Vea [configurar la purga DTA y archivar trabajo](../core/how-to-configure-the-dta-purge-and-archive-job.md).|  
|Asegúrese de que el trabajo está capacitado para purgar los datos de seguimiento de velocidad a la que se generan el seguimiento de los datos entrantes.|Vea [medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)|  
|Revise la purga condicional y purga incondicional parámetros para asegurarse de mantiene los datos durante el período de tiempo óptimo.|Vea [archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md).|  
|Si solo necesita purgar los datos antiguos y no necesita archivar cambio en primer lugar, el Agente SQL trabajo que iba a llamar al procedimiento almacenado "dtasp_PurgeTrackingDatabase."|Vea [purgar los datos de la base de datos de seguimiento de BizTalk](../core/how-to-purge-data-from-the-biztalk-tracking-database.md).|  
  
## <a name="next"></a>Siguiente
  
-   [Configuración de SQL Server que no se debe cambiar](sql-server-settings-that-should-not-be-changed.md)  
  
-   [Supervisión y reducir la contención de E/S de base de datos](monitoring-and-reducing-database-i-o-contention.md)  
  
-   [Revisar y probar la configuración de clúster de servidores SQL Server para escenarios de conmutación por error](reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)  
  
-   [Definición de valores de crecimiento automático para bases de datos](defining-auto-growth-settings-for-databases.md)  
  
-   [Realizar copias de seguridad de bases de datos](backing-up-databases.md)  
  
-   [Uso del trasvase de registros de BizTalk Server para la recuperación ante desastres](using-biztalk-server-log-shipping-for-disaster-recovery.md)  
  
-   [Supervisión de trabajos del Agente SQL Server](monitoring-sql-server-agent-jobs.md)  
  
-   [Depuración y archivado de datos de seguimiento](purging-and-archiving-tracking-data.md)