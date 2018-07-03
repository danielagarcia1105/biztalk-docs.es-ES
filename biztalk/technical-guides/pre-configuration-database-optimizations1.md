---
title: Base de datos de configuración previa Optimizations1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebd0b32a-490d-4db2-a1fc-bf3bef93aeea
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c59c396534d6c555cfd133e949e3a5becb5375b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998837"
---
# <a name="pre-configuration-database-optimizations"></a>Optimizaciones de base de datos de configuración previa
BizTalk Server es una aplicación consume la base de datos que puede requerir la creación de hasta 13 bases de datos independientes en Microsoft SQL Server. Debido a la función crítica que SQL Server desempeña en cualquier entorno de BizTalk Server, resulta de gran importancia que SQL Server está configurado y optimizado para un rendimiento óptimo. Si SQL Server no está optimizado para llevar a cabo correctamente, las bases de datos usados por BizTalk Server se convertirá en un cuello de botella y se verá afectado el rendimiento general del entorno de BizTalk Server. En este tema se describe varias optimizaciones de rendimiento de SQL Server que se deben seguir antes de instalar a BizTalk Server y configurar las bases de datos de BizTalk Server.  
  
## <a name="set-ntfs-file-allocation-unit"></a>Establezca la unidad de asignación de archivos NTFS  
 SQL Server almacena sus datos en **extensiones**, que son grupos de ocho páginas de 8 KB. Por lo tanto, para optimizar el rendimiento de disco, establezca el tamaño de unidad de asignación NTFS a 64KB como se describe en la sección "Prácticas recomendadas de configuración de disco" de SQL Server los procedimientos recomendados "Preimplementación prácticas recomendadas de E/S" disponible en el artículo [ http://go.microsoft.com/fwlink/?LinkId=140818](http://go.microsoft.com/fwlink/?LinkId=140818). Para obtener más información acerca de SQL Server páginas y extensiones, vea el tema de libros en pantalla de SQL Server [descripción de páginas y extensiones](http://go.microsoft.com/fwlink/?LinkId=148939) (HYPERLINK "<http://go.microsoft.com/fwlink/?LinkId=148939>" <http://go.microsoft.com/fwlink/?LinkId=148939>).  
  
## <a name="database-planning-considerations"></a>Consideraciones de planeación de la base de datos  
 Se recomienda que hospede su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de almacenamiento rápido (por ejemplo, discos rápidos de SAN o discos SCSI rápidos). RAID 10 (1 + 0) en lugar de RAID 5 se recomienda porque es más lento en escritura raid 5. Discos de SAN más recientes tienen las memorias caché grandes cantidades de memoria, en que estos casos, la selección RAID no es tan importante. Para aumentar el rendimiento, las bases de datos y sus archivos de registro pueden residir en distintos discos físicos.  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>Instalar el service pack más reciente y las actualizaciones acumulativas de SQL Server  
 Instale los últimos service packs y las últimas actualizaciones acumulativas de SQL Server 2005 y SQL Server 2008, así como los service packs más recientes de .NET Framework.  
  
## <a name="install-sql-service-packs-on-both-biztalk-server-and-sql-server"></a>Instalar Service Packs de SQL en BizTalk Server y SQL Server  
 Al instalar los service packs de SQL Server, instale también el service pack en el equipo de BizTalk Server. BizTalk Server utiliza los componentes de cliente de SQL que actualizan los service packs de SQL Server.  
  
## <a name="consider-implementing-the-sql-server-2008-data-collector-and-management-data-warehouse"></a>Considere la posibilidad de implementar el recopilador de datos de SQL Server 2008 y el almacén de administración de datos  
 SQL Server 2008 admite el uso de los nuevos datos para pruebas y análisis de tendencias relacionados con el recopilador de datos y almacenamiento de datos de administración para recopilar el rendimiento de la base de datos o entorno. El recopilador de datos conserva todos los datos recopilados en el almacén de datos de administración especificado. Aunque esto no es una optimización del rendimiento, esto será útil para el análisis de problemas de rendimiento.  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>Conceda a la cuenta que se usa para el bloqueo de Windows las páginas de privilegio de memoria de SQL Server  
 Conceda a la Windows "Bloquear páginas en memoria" de privilegios a la cuenta de servicio de SQL Server. Esto debe hacerse para evitar que el sistema operativo Windows paginación a la memoria del grupo de búferes del proceso de SQL Server mediante el bloqueo de memoria asignada para el grupo de búferes en la memoria física. Para obtener más información, vea Microsoft Knowledge Base article 914483 "cómo reducir la paginación de memoria del grupo de búferes en la versión de 64 bits de SQL Server 2005" en [ http://go.microsoft.com/fwlink/?LinkId=148948 ](http://go.microsoft.com/fwlink/?LinkId=148948).  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>Conceder el SE_MANAGE_VOLUME_NAME a la cuenta de servicio de SQL Server  
 Asegúrese de que la cuenta que ejecuta el servicio SQL Server tiene el privilegio de Windows "Realizar tareas de mantenimiento de volumen" o asegúrese de que pertenece a un grupo de seguridad que realiza. Esto permitirá que la inicialización instantánea de archivos que garantiza un rendimiento óptimo si tiene una base de datos en crecimiento automático.  
  
## <a name="set-min-and-max-server-memory"></a>Establecer Min y Max Server Memory  
 Los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que hospedan las bases de datos de BizTalk Server deben estar dedicados a ejecutar SQL Server. Se recomienda que el "min server memory" y las opciones de "max server memory" en cada instancia de SQL Server se establecen para especificar la cantidad fija de memoria para asignar a SQL Server. En este caso, debe establecer el "min server memory" y "max server memory" en el mismo valor (es igual a la cantidad máxima de memoria física que va a usar SQL Server). Esto reducirá la sobrecarga que se usan por SQL Server, administrar dinámicamente estos valores. Ejecute los siguientes comandos de T-SQL en cada equipo de SQL Server para especificar la cantidad fija de memoria para asignar a SQL Server:  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 Antes de establecer la cantidad de memoria para SQL Server, determine la configuración de memoria apropiada restando la memoria necesaria para Windows Server desde la memoria física total. Se trata de la cantidad máxima de memoria que puede asignar a SQL Server.  
  
> [!NOTE]  
>  Si los equipos que ejecutan a SQL Server que hospedan las bases de datos de BizTalk Server también hospedan el Enterprise Single Sign-On servidor secreto principal, a continuación, es posible que deba ajustar este valor para asegurarse de que hay suficiente memoria disponible para su ejecución la Enterprise Single Sign-On Servicio. No es una práctica habitual para ejecutar una instancia agrupada del servicio Enterprise Single Sign-On en un clúster de SQL Server para proporcionar alta disponibilidad para el servidor secreto principal. Para obtener más información acerca de la agrupación en clústeres el Enterprise Single Sign-On servidor secreto principal, vea el tema "How to Cluster the Master Secret Server" en el BizTalk Serverdocumentation en [ http://go.microsoft.com/fwlink/?LinkID=106874 ](http://go.microsoft.com/fwlink/?LinkID=106874).  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>Dividir la base de datos tempdb en varios archivos de datos del mismo tamaño en cada instancia de SQL Server usados por BizTalk Server  
 Es fundamental asegurarse de que los archivos de datos que se utiliza para tempdb del mismo tamaño porque usa el algoritmo de relleno proporcional [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se basa en el tamaño de los archivos de datos. Este algoritmo intenta asegurarse de que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rellenos de cada archivo en proporción de espacio libre restante en ese archivo para que alcanzan su capacidad máxima en aproximadamente al mismo tiempo. Si se crean archivos de datos con distintos tamaños, el algoritmo de relleno proporcional usará el archivo más grande para las asignaciones de página GAM en lugar de distribuir las asignaciones entre todos los archivos, con lo que frustra el propósito de crear varios archivos de datos. El número de archivos de datos de la base de datos tempdb debe configurarse para que sea al menos igual que el número de procesadores que se asigna para SQL Server.  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>Habilitar T1118 de marca de seguimiento como un parámetro de inicio para todas las instancias de SQL Server  
 Implementar seguimiento marca – T1118 ayuda a reducir la contención entre las instancias de SQL Server mediante la eliminación de casi todas las asignaciones de página única. Para obtener más información, consulte el artículo 328551 de Microsoft Knowledge Base "PRB: mejoras de concurrencia para la base de datos tempdb" en [ http://go.microsoft.com/fwlink/?LinkID=103713 ](http://go.microsoft.com/fwlink/?LinkID=103713).  
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>No cambie la configuración de SQL Server predeterminado de max degree of parallelism, estadísticas de SQL Server, o vuelve a generar el índice de base de datos y la desfragmentación  
 Si una instancia de SQL Server hospede bases de datos de BizTalk Server, ciertas opciones de SQL Server no deben cambiarse. En concreto, las estadísticas de SQL Server en la base de datos de cuadro de mensajes y la configuración para el índice de base de datos de la SQL Server max degree of parallelism, vuelve a generar y no debe modificarse la desfragmentación. Para obtener más información, vea el tema "SQL Server configuración que no se debe cambiar" en la Guía de operaciones de BizTalk Server en [ http://go.microsoft.com/fwlink/?LinkId=114358 ](http://go.microsoft.com/fwlink/?LinkId=114358).