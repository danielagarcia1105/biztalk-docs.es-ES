---
title: "Base de datos de configuración previa Optimizations2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c525c3a-249c-4694-b287-a8c35a6aa524
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd8bb0ba839d656dd99959a3352ea8da42457d16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="pre-configuration-database-optimizations"></a>Optimizaciones de base de datos de configuración previa
Debido a la función crítica que SQL Server se reproduce en cualquier entorno de BizTalk Server, resulta de gran importancia que SQL Server sea configurado/optimizado para un rendimiento óptimo. Si SQL Server no está optimizado para llevar a cabo correctamente, las bases de datos usados por BizTalk Server se convertirá en un cuello de botella y se verá afectado el rendimiento general del entorno de BizTalk Server. En este tema se describe varias optimizaciones de rendimiento de SQL Server que hay que seguir antes de instalar a BizTalk Server y configurar las bases de datos de BizTalk Server.  
  
## <a name="set-ntfs-file-allocation-unit"></a>Establecer la unidad de asignación de archivo NTFS  
 SQL Server almacena sus datos en **extensiones**, que son colecciones de ocho páginas físicamente contiguas de 8 K o 64 KB. Por lo tanto, para optimizar el rendimiento de disco, establezca el tamaño de unidad de asignación de NTFS a 64KB como se describe en la sección "Prácticas recomendadas de configuración de disco" del artículo de prácticas recomendada de SQL Server ["Prácticas recomendadas de E/S antes de la implementación"](http://go.microsoft.com/fwlink/?LinkId=140818) (http:/ ¿/go.Microsoft.com/fwlink/? LinkId = 140818).  
  
## <a name="considerations-for-the-version-and-edition-of-sql-server"></a>Consideraciones para la versión y edición de SQL Server  
 Varias versiones y ediciones de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] proporcionan diferentes características que pueden afectar al rendimiento de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Por ejemplo, en condiciones de carga elevada, el número de bloqueos de base de datos que están disponibles para la versión de 32 bits de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] puede que se superara, que es negativo en el rendimiento de la solución de BizTalk. Considere la posibilidad de alojamiento de la base de datos de cuadro de mensajes en una versión de 64 bits de SQL Server si se producen errores de "sin bloqueo" en el entorno de prueba. El número de bloqueos disponible es significativamente superior en la versión de 64 bits de SQL Server.  
  
 Considere la siguiente tabla cuando se decida por las características del motor de base de datos que necesita para su entorno de BizTalk. Para gran escala, compatibilidad con soluciones de nivel de empresa que requieren la agrupación en clústeres, soporte técnico, de trasvase de registros de servidor BizTalk Server o Analysis Services admite y, a continuación, deberá [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] o [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] Enterprise Edition para alojar el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos.  
  
|Versión y edición de SQL Server|Compatibilidad con 64 bits|Compatibilidad con varias instancias|Compatibilidad con clústeres|Analysis Services|  
|---------------------------------------|---------------------|-----------------------------|------------------------|-----------------------|  
|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Enterprise Edition|Sí|Sí (50)|Sí|Sí|  
|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Standard Edition|Sí|Sí (16)|Sí (2 nodos)|Sí|  
|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Edición de grupo de trabajo|Sí|Sí (16)|No|No|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] Enterprise Edition|Sí|Sí|Sí|Sí|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] Standard Edition|Sí|Sí|Sí (2 nodos)|Sí|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]Edición de grupo de trabajo|No|Sí|No|No|  
  
 Para obtener una lista completa de las características admitidas por las ediciones de [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], consulte [características compatibles con las ediciones de SQL Server 2008 R2](http://go.microsoft.com/fwlink/?LinkId=140465) (http://go.microsoft.com/fwlink/?LinkId=140465) en el [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] documentación.  
  
## <a name="database-planning-considerations"></a>Consideraciones de planeación de la base de datos  
 Se recomienda que hospedan las bases de datos de SQL Server en almacenamiento rápido (por ejemplo, discos rápidos de SAN o discos SCSI rápidos). RAID 10 (1 + 0) en lugar de RAID 5 se recomienda ya que raid 5 es más lento en escritura. Discos de SAN más recientes tienen las memorias caché grandes cantidades de memoria, por lo que en estos casos no es tan importante la selección de raid. Para aumentar el rendimiento, las bases de datos y sus archivos de registro pueden residir en diferentes discos físicos.  
  
 Considere también la profundidad de cola host (HBA) del adaptador de bus de optimización si utiliza una red de área de almacenamiento (SAN). Esto puede afectar significativamente al rendimiento de E/S y cuadro fuera de los valores pueden ser suficientes para SQL Server. Es necesario para determinar el valor óptimo, realizar pruebas aunque la profundidad de cola de 64 suele aceptarse como un buen punto de partida en ausencia de las recomendaciones del proveedor específico  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>Instale el service pack más reciente y las actualizaciones acumulativas para SQL Server  
 Instalar el service Pack más recientes y las últimas actualizaciones acumulativas para [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] , así como la versión más reciente de .NET Framework, service Pack.  
  
## <a name="install-sql-service-packs-and-cumulative-updates-on-both-biztalk-server-and-sql-server"></a>Instalar Service Packs de SQL y las actualizaciones acumulativas en BizTalk Server y SQL Server  
 Al instalar el service Pack o actualizaciones acumulativas para SQL Server, instalar el service pack o actualización acumulativa en el equipo de servidor BizTalk Server. BizTalk Server utiliza los componentes de cliente de SQL que se actualizan mediante SQL Server service Pack y las actualizaciones acumulativas.  
  
## <a name="consider-using-a-fast-solid-state-drive-ssd-to-house-the-sql-server-tembdb"></a>Considere el uso de una unidad de estado rápido sólido (SSD) para alojar el tembdb de SQL Server  
 Considere el uso de una o varias unidades de disco de estado sólido (SSD) para alojar el TempDB. Las unidades SSD ofrecen ventajas de rendimiento importante sobre unidades de disco duro tradicionales y se quita rápidamente en el precio según va entrando en mercados estándar. Porque el rendimiento de TempDB a menudo es un factor clave completo [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rendimiento, el costo inicial de agregado de las unidades de disco se suelen rápidamente recuperar al aumenta el global [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rendimiento, especialmente cuando se ejecutan las aplicaciones empresariales para que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] el rendimiento resulta esencial.  
  
## <a name="consider-implementing-the-sql-server-2008-r2-data-collector-and-management-data-warehouse"></a>Considere la posibilidad de implementar el recopilador de datos de SQL Server 2008 R2 y el almacenamiento de datos de administración  
 SQL Server 2008 R2 permite el uso del nuevo recopilador de datos y almacenamiento de datos de administración para recopilar el rendimiento del entorno/base de datos relacionadas con datos de prueba y análisis de tendencias. El recopilador de datos conserva los datos de todos los recopilados en el almacén de datos de administración especificada. Aunque esto no es una optimización del rendimiento esto será útil para el análisis de los problemas de rendimiento.  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>Conceda a la cuenta que se usa para el bloqueo de Windows páginas de privilegio de memoria de SQL Server  
 Conceda el Windows privilegio Bloquear páginas en memoria a la cuenta de servicio de SQL Server. Esto debe hacerse para evitar que el sistema operativo Windows de paginación a la memoria del grupo de búferes del proceso de SQL Server bloqueando la memoria asignada para el grupo de búferes en la memoria física.  
  
 En nuestro entorno de laboratorio, la directiva de Windows **Lock Pages in Memory** opción estaba habilitada de forma predeterminada. Para obtener más información sobre cómo habilitar la **Lock Pages in Memory** opción, vea [Cómo: habilitar la opción Bloquear páginas en memoria (Windows)](http://go.microsoft.com/fwlink/?LinkID=208267) (http://go.microsoft.com/fwlink/?LinkID=208267).  
  
> [!IMPORTANT]  
>  Al conceder a la cuenta de servicio de SQL Server el Windows privilegio Bloquear páginas en memoria se aplican ciertas limitaciones. Consulte los siguientes artículos de Microsoft Knowledge base para obtener más información:  
>   
>  -   [918483, "Cómo reducir la paginación de memoria del grupo de búferes en la versión de 64 bits de SQL Server 2005"](http://go.microsoft.com/fwlink/?LinkID=148948) (http://go.microsoft.com/fwlink/?LinkID=148948).  
> -   [970070, "soporte para las páginas de bloqueado en sistemas SQL Server 2005 Standard Edition de 64 bits y en sistemas SQL Server 2008 Standard Edition de 64 bits"](http://go.microsoft.com/fwlink/?LinkId=160474) (http://go.microsoft.com/fwlink/?LinkId=160474).  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>Conceder el SE_MANAGE_VOLUME_NAME de derecha a la cuenta de servicio de SQL Server  
 Asegúrese de que la cuenta que ejecuta el servicio SQL Server tiene el privilegio de Windows 'Realizar tareas de mantenimiento de volumen' o asegúrese de que pertenece a un grupo que. Esto le permitirá instantánea de archivos inicialización garantizar un rendimiento óptimo si tiene una base de datos para el crecimiento automático.  
  
## <a name="set-min-and-max-server-memory"></a>Establecer Min y Max Server Memory  
 Los equipos que ejecutan a SQL Server que hospedan las bases de datos de BizTalk Server deben estar dedicados a ejecutar SQL Server. Cuando los equipos que ejecutan a SQL Server que hospedan las bases de datos de BizTalk Server se dedican a ejecutar SQL Server, se recomienda que la 'min server memory' y opciones de 'max server memory' en cada instancia de SQL Server se establecen para especificar la cantidad de memoria fija asignar a SQL Server. En este caso, debe establecer el "min server memory" y "max server memory" en el mismo valor (es igual a la cantidad máxima de memoria física que se va a usar SQL Server). Esto disminuirá la sobrecarga que utilizaría en caso contrario, SQL Server administrar dinámicamente estos valores. Ejecute los siguientes comandos de T-SQL en cada equipo que ejecuta SQL Server para especificar la cantidad fija de memoria para asignar a SQL Server:  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 Antes de configurar la cantidad de memoria para SQL Server, determine la configuración de memoria apropiada restando la memoria necesaria para Windows Server desde la memoria física total. Se trata de la cantidad máxima de memoria que puede asignar a SQL Server.  
  
> [!NOTE]  
>  Si los equipos que ejecutan a SQL Server que hospedan las bases de datos de BizTalk Server también hospedan el Enterprise Single Sign-On servidor secreto principal, a continuación, que necesite ajustar este valor para asegurarse de que hay suficiente memoria disponible para ejecutar la Enterprise Single Sign-On Servicio. No es una práctica poco habitual para ejecutar una instancia en clúster del servicio de Enterprise Single Sign-On en un clúster de SQL Server para proporcionar alta disponibilidad para el servidor secreto principal. Para obtener más información acerca de la Enterprise Single Sign-On servidor secreto principal de agrupación en clústeres, vea el tema [cómo agrupar el servidor secreto principal](http://go.microsoft.com/fwlink/?LinkId=158251) (http://go.microsoft.com/fwlink/?LinkId=158251) en la documentación de BizTalk Server.  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>Dividir la base de datos tempdb en varios archivos de datos del mismo tamaño en cada instancia de SQL Server utilizado por BizTalk Server  
 Es fundamental asegurarse de que los archivos de datos que se usan para tempdb del mismo tamaño, dado que el algoritmo de relleno proporcional utilizado por SQL Server se basa en el tamaño de los archivos de datos. Si se crean archivos de datos con diferentes tamaños, el algoritmo de relleno proporcional usará el archivo más grande más para las asignaciones de página GAM en lugar de repartir las asignaciones entre todos los archivos, evitando así la finalidad de crear varios archivos de datos. El número óptimo de archivos de datos tempdb depende del grado de contención de bloqueos temporales que se ve en tempdb. Como regla general, el número de archivos de datos debe ser menor o igual al número de núcleos de procesador/CPU que el número de CPU es 8. Para los servidores con más de 8 CPU, crear archivos de datos en la mitad el número de CPU (una vez más, solo tiene contención de bloqueos temporales).  
  
 En nuestro entorno de laboratorio, usamos el siguiente script para crear 8 archivos de datos de TempDB, cada uno de ellos tenía un tamaño de archivo de 1024 MB con el crecimiento de 100 MB y un archivo de registro de 512 MB con el crecimiento de 100 MB. Los archivos de datos se mueven a la unidad H: y archivo de registro se mueve a la unidad I:.  
  
> [!IMPORTANT]  
>  Esta secuencia de comandos está "tal cual", está diseñado para demostración o solo con fines educativos y debe utilizarse bajo su responsabilidad. Uso de esta secuencia de comandos no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este script.  
  
```  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
-- Use of included script samples are subject to the terms specified at   
-- http://www.microsoft.com/info/cpyright.htm  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
--***Instructions***  
-- 1. If running the script from a remote server, change the context in SSMS to target instance  
-- 2. Enable SQLCMD mode (add & click toolbar button or toggle by clicking Query > SQLCMD Mode)  
-- 3. Commence execution of scripts (recommend running statements discretely to more easily remedy potential problems)  
-- 4. Examine servername & temp configuration  
-- 5. If necessary, 1) Replace instance name in path to reflect target instance *all throughout script*  
      --            2) Modify root drives to reflect drives designated for data & log (folder creation *and* ALTER DB statements)  
-- 6. Resume script execution  
-- 7. If necessary, create new folders  
-- 8. Modify/Add data & log files   
-- 9. Recycle SQL service using sqlservermanager10.msc  
--10. Examine results & if appropriate, delete original tempdb data log files   
 --(if they were "moved", the original files aren't automatically deleted)  
  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
--1. If running the script from a remote server, change the context in SSMS to target instance  
--2. Enable SQLCMD mode (add & click toolbar button or toggle by clicking Query > SQLCMD Mode)  
--3. Commence execution of scripts (recommend running statements discretely to more easily remedy potential problems)  
--4. Examine servername & temp configuration  
SELECT @@SERVERNAME  
EXEC dbo.sp_helpdb tempdb  
--tempdev   1   C:\tempdb.mdf   PRIMARY  8192 KB  Unlimited  10%  data only  
--templog   2   C:\templog.ldf  NULL      512 KB  Unlimited  10%  log only  
GO  
--5. If necessary, 1) Replace instance name in path to reflect target instance *all throughout script*  
     --            2) Modify root drives to reflect drives designated for data & log (folder creation *and* ALTER DB statements)  
--6. Resume script execution  
--7. If necessary, create new folders  
--!!md H:\MSSQL10.<instance>  
--!!md H:\MSSQL10.<instance>\MSSQL  
--!!md H:\MSSQL10.<instance>\MSSQL\DATA  
GO  
-- 8. Modify/Add data & log files   
 --note: even if the out-of-box mdf is already where it needs to be,   
   --the first command is necessary to modify size & filegrowth  
ALTER DATABASE tempdb MODIFY FILE (NAME = tempdev  , FILENAME = 'H:\tempdb.mdf'   , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat2 , FILENAME = 'H:\tempdat2.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat3 , FILENAME = 'H:\tempdat3.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat4 , FILENAME = 'H:\tempdat4.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat5 , FILENAME = 'H:\tempdat5.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat6 , FILENAME = 'H:\tempdat6.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat7 , FILENAME = 'H:\tempdat7.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat8 , FILENAME = 'H:\tempdat8.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
GO  
ALTER DATABASE tempdb MODIFY FILE (NAME = templog , FILENAME = 'I:\templog.ldf', SIZE =  512MB , FILEGROWTH = 100MB)  
GO  
--8b. Modify log file:  modify drive & instance name to reflect designated destination for tempdb log   
--!!md I:\MSSQL10.<instance>  
--!!md I:\MSSQL10.<instance>\MSSQL  
--!!md I:\MSSQL10.<instance>\MSSQL\DATA  
GO  
  
-- 9. Recycle SQL service in SQL Server Services node of sqlservermanager10.msc  
    --note, if running script from a UNC share, SSMS will report an error,   
      --but SQL Server Configuration Manager will open if its location is in %path%  
!!sqlservermanager10.msc  
  
--10. Examine results & if appropriate, delete original tempdb data log files   
 --(if they were "moved", the original files aren't automatically deleted)  
EXEC dbo.sp_helpdb tempdb  
--!!del C:\tempdb.mdf     
--!!del C:\templog.ldf  
GO  
  
```  
  
 Utilice el Monitor de actividad de SQL Server 2008 o SQL Server 2005 rendimiento panel informes descritos en [supervisión de rendimiento de SQL Server](../technical-guides/monitoring-sql-server-performance.md) para identificar los problemas de contención de bloqueos temporales.  
  
## <a name="manually-set-sql-server-process-affinity"></a>Establecer manualmente la afinidad de proceso de SQL Server  
 La opción de afinidad de proceso puede proporcionar mejoras de rendimiento en entornos de SQL Server de tecnología avanzados, nivel de empresa que se ejecutan en equipos no NUMA con 16 CPU o más. Esto es especialmente cierto en entornos de BizTalk de alto rendimiento donde haya contención en tablas compartidas en la base de datos de cuadro de mensajes. Dado que los equipos de SQL Server que se utilizaron en nuestro entorno de laboratorio no habilitada para NUMA y tuvieron 16 núcleos, para optimizar el rendimiento, se usaron los siguientes comandos para establecer la afinidad de proceso:  
  
 **Para establecer manualmente la afinidad de proceso de SQL Server entre 0 y 15**  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU = 0 to 15  
```  
  
 Para obtener más información, consulte [ALTER SERVER CONFIGURATION (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkID=208269) (http://go.microsoft.com/fwlink/?LinkID=208269).  
  
## <a name="configure-msdtc"></a>Configurar MSDTC  
 Para facilitar las transacciones entre SQL Server y BizTalk Server, debe habilitar el Coordinador de transacciones distribuidas de Microsoft (MS DTC). Para configurar MSDTC en SQL Server, vea el tema [directrices generales para mejorar el rendimiento del sistema operativo](../technical-guides/general-guidelines-for-improving-operating-system-performance.md).  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>Habilitar T1118 de marca de seguimiento como un parámetro de inicio para todas las instancias de SQL Server  
 Implementar seguimiento marca – T1118 ayuda a reducir la contención en todas las instancias de SQL Server mediante la eliminación de casi todas las asignaciones de páginas individuales. Para obtener más información, vea el artículo de Microsoft Knowledge Base [328551, "PRB: mejoras de concurrencia para la base de datos tempdb"](http://go.microsoft.com/fwlink/?LinkID=153694) (http://go.microsoft.com/fwlink/?LinkID=153694).  
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>No cambie la configuración de SQL Server predeterminada de max degree of parallelism, las estadísticas de SQL Server, o si vuelve a generar el índice de base de datos y desfragmentación  
 Si una instancia de SQL Server hospedará las bases de datos de BizTalk Server, hay ciertas opciones de SQL Server que no se deben cambiar. En concreto, las estadísticas de SQL Server en la base de datos de cuadro de mensajes y las opciones para el índice de base de datos de la SQL Server max degree of parallelism, vuelve a generar y no debe modificarse la desfragmentación. Para obtener más información, vea el tema [SQL Server configuración que no se debería cambiar](http://go.microsoft.com/fwlink/?LinkId=160068) (http://go.microsoft.com/fwlink/?LinkId=160068) en la Guía de operaciones de BizTalk Server 2010.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento de la base de datos](../technical-guides/optimizing-database-performance.md)