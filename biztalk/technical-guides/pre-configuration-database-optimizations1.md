---
title: "Base de datos de configuración previa Optimizations1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebd0b32a-490d-4db2-a1fc-bf3bef93aeea
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1333f956afc4411ff8b105c777214467155ae7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="pre-configuration-database-optimizations"></a>Optimizaciones de base de datos de configuración previa
BizTalk Server es una aplicación de base de datos consume que requieran la creación de hasta 13 bases de datos independientes en Microsoft SQL Server. Debido a la función crítica que SQL Server se reproduce en cualquier entorno de BizTalk Server, resulta de gran importancia que SQL Server está configurado y optimizado para un rendimiento óptimo. Si SQL Server no está optimizado para llevar a cabo correctamente, las bases de datos usados por BizTalk Server se convertirá en un cuello de botella y se verá afectado el rendimiento general del entorno de BizTalk Server. En este tema se describe varias optimizaciones de rendimiento de SQL Server que hay que seguir antes de instalar a BizTalk Server y configurar las bases de datos de BizTalk Server.  
  
## <a name="set-ntfs-file-allocation-unit"></a>Establecer la unidad de asignación de archivo NTFS  
 SQL Server almacena sus datos en **extensiones**, que son grupos de ocho páginas de 8 KB. Por lo tanto, para optimizar el rendimiento de disco, establezca el tamaño de unidad de asignación de NTFS a 64KB como se describe en la sección "Prácticas recomendadas de configuración de disco" de SQL Server "Antes de la implementación E/S prácticas recomendadas" disponible en el artículo prácticas recomendadas [http:// ¿go.Microsoft.com/fwlink/? LinkId = 140818](http://go.microsoft.com/fwlink/?LinkId=140818). Para obtener más información acerca de las páginas de SQL Server y las extensiones, consulte el [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] tema libros en pantalla [descripción de páginas y extensiones](http://go.microsoft.com/fwlink/?LinkId=148939) (HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=148939" http://go.microsoft.com/fwlink/?LinkId=148939).  
  
## <a name="database-planning-considerations"></a>Consideraciones de planeación de la base de datos  
 Se recomienda hospedar su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de almacenamiento rápido (por ejemplo, discos rápidos de SAN o discos SCSI rápidos). RAID 10 (1 + 0) en lugar de RAID 5 se recomienda porque es más lento en escritura raid 5. Discos de SAN más recientes tienen las memorias caché grandes cantidades de memoria, en que estos casos, la selección de RAID no es tan importante. Para aumentar el rendimiento, las bases de datos y sus archivos de registro pueden residir en diferentes discos físicos.  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>Instale el service pack más reciente y las actualizaciones acumulativas para SQL Server  
 Instale los últimos service packs y las últimas actualizaciones acumulativas para SQL Server 2005 y SQL Server 2008, así como los service Pack más recientes de .NET Framework.  
  
## <a name="install-sql-service-packs-on-both-biztalk-server-and-sql-server"></a>Instalar Service Packs de SQL en el servidor BizTalk Server y SQL Server  
 Al instalar el service Pack para SQL Server, instalar el service pack en el equipo de servidor BizTalk Server. BizTalk Server utiliza los componentes de cliente de SQL que actualizan los service packs de SQL Server.  
  
## <a name="consider-implementing-the-sql-server-2008-data-collector-and-management-data-warehouse"></a>Considere la posibilidad de implementar el recopilador de datos de SQL Server 2008 y almacenamiento de datos de administración  
 SQL Server 2008 permite el uso del nuevo recopilador de datos y almacenamiento de datos de administración para recopilar el rendimiento del entorno/base de datos relacionadas con datos de prueba y análisis de tendencias. El recopilador de datos conserva los datos de todos los recopilados en el almacén de datos de administración especificada. Aunque esto no es una optimización del rendimiento, esto será útil para el análisis de los problemas de rendimiento.  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>Conceda a la cuenta que se usa para el bloqueo de Windows páginas de privilegio de memoria de SQL Server  
 Conceda el privilegio "Lock Pages in Memory" de Windows para la cuenta de servicio de SQL Server. Esto debe hacerse para evitar que el sistema operativo Windows de paginación a la memoria del grupo de búferes del proceso de SQL Server bloqueando la memoria asignada para el grupo de búferes en la memoria física. Para obtener más información, consulte Microsoft Knowledge Base artículo 914483 "How to reducir la paginación de memoria del grupo de búferes en la versión de 64 bits de SQL Server 2005" en [http://go.microsoft.com/fwlink/?LinkId=148948](http://go.microsoft.com/fwlink/?LinkId=148948).  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>Conceder el SE_MANAGE_VOLUME_NAME a la cuenta de servicio de SQL Server  
 Asegúrese de que la cuenta que ejecuta el servicio SQL Server tiene el privilegio de Windows "Realizar tareas de mantenimiento de volumen" o asegúrese de que pertenece a un grupo de seguridad que realiza. Esto permitirá que la inicialización instantánea de archivos permite garantizar un rendimiento óptimo si tiene una base de datos para el crecimiento automático.  
  
## <a name="set-min-and-max-server-memory"></a>Establecer Min y Max Server Memory  
 Los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que hospedan las bases de datos de BizTalk Server deben estar dedicados a ejecutar SQL Server. Se recomienda que se establecen las opciones de "max server memory" en cada instancia de SQL Server y "min server memory" para especificar la cantidad fija de memoria para asignar a SQL Server. En este caso, debe establecer el "min server memory" y "max server memory" en el mismo valor (es igual a la cantidad máxima de memoria física que se va a usar SQL Server). Esto disminuirá la sobrecarga que utilizaría en caso contrario, SQL Server administrar dinámicamente estos valores. Ejecute los siguientes comandos de T-SQL en cada equipo de SQL Server para especificar la cantidad fija de memoria para asignar a SQL Server:  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 Antes de configurar la cantidad de memoria para SQL Server, determine la configuración de memoria apropiada restando la memoria necesaria para Windows Server desde la memoria física total. Se trata de la cantidad máxima de memoria que puede asignar a SQL Server.  
  
> [!NOTE]  
>  Si los equipos que ejecutan a SQL Server que hospedan las bases de datos de BizTalk Server también hospedan el Enterprise Single Sign-On servidor secreto principal, a continuación, que necesite ajustar este valor para asegurarse de que hay suficiente memoria disponible para ejecutar la Enterprise Single Sign-On Servicio. No es una práctica poco habitual para ejecutar una instancia en clúster del servicio de Enterprise Single Sign-On en un clúster de SQL Server para proporcionar alta disponibilidad para el servidor secreto principal. Para obtener más información sobre el Enterprise Single Sign-On servidor secreto principal de agrupación en clústeres, vea el tema "How to Cluster the Master secreto Server" en la [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]documentación en [http://go.microsoft.com/fwlink/?LinkID=106874](http://go.microsoft.com/fwlink/?LinkID=106874).  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>Dividir la base de datos tempdb en varios archivos de datos del mismo tamaño en cada instancia de SQL Server utilizado por BizTalk Server  
 Asegurarse de que los archivos de datos que se usan para tempdb del mismo tamaño es fundamental, ya que usa el algoritmo de relleno proporcional [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se basa en el tamaño de los archivos de datos. Este algoritmo intenta asegurarse de que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rellena cada archivo en proporción al espacio libre restante en ese archivo para que lleguen a su capacidad máxima en aproximadamente al mismo tiempo. Si se crean archivos de datos con diferentes tamaños, el algoritmo de relleno proporcional usará el archivo más grande más para las asignaciones de página GAM en lugar de repartir las asignaciones entre todos los archivos, evitando así la finalidad de crear varios archivos de datos. El número de archivos de datos de la base de datos tempdb debe configurarse para que sea al menos igual que el número de procesadores asignados para SQL Server.  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>Habilitar T1118 de marca de seguimiento como un parámetro de inicio para todas las instancias de SQL Server  
 Implementar seguimiento marca – T1118 ayuda a reducir la contención en todas las instancias de SQL Server mediante la eliminación de casi todas las asignaciones de páginas individuales. Para obtener más información, vea el artículo 328551 de Microsoft Knowledge Base "PRB: mejoras de concurrencia para la base de datos tempdb" en [http://go.microsoft.com/fwlink/?LinkID=103713](http://go.microsoft.com/fwlink/?LinkID=103713).  
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>No cambie la configuración de SQL Server predeterminada de max degree of parallelism, las estadísticas de SQL Server, o si vuelve a generar el índice de base de datos y desfragmentación  
 Si una instancia de SQL Server hospedará las bases de datos de BizTalk Server, ciertas opciones de configuración de SQL Server no deben cambiarse. En concreto, las estadísticas de SQL Server en la base de datos de cuadro de mensajes y las opciones para el índice de base de datos de la SQL Server max degree of parallelism, vuelve a generar y no debe modificarse la desfragmentación. Para obtener más información, vea el tema "SQL Server configuración que no se debería cambiar" en la Guía de operaciones de BizTalk Server en [http://go.microsoft.com/fwlink/?LinkId=114358](http://go.microsoft.com/fwlink/?LinkId=114358).