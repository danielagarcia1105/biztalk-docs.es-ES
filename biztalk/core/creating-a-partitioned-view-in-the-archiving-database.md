---
title: Crear una vista con particiones en la base de datos de archivado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases, partitioning
- partitioning
- Archive database [BAM], partitioning
ms.assetid: f9ef7480-2e37-4477-92c8-b5686ae9b54b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42adf8f614f124c9b17597a44cdaaba9d7ed4f93
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a>Crear una vista con particiones en la base de datos de archivo
Al ejecutar el paquete de mantenimiento de datos de BAM (BAM_DM_`<activity name>`) BAM copia cada partición de la base de datos de importación principal a una tabla separada de la base de datos de archivos BAM. Si desasocia la base de datos de archivo y vuelve a asociarla para las consultas, resultará difícil localizar los datos para la consulta.  
  
 Puede crear vistas con particiones en la base de datos de archivo BAM para facilitar la localización de los datos. BAM admite hasta 253 particiones. BAM genera, para cada actividad, un paquete DTS de mantenimiento de datos de BAM que se encarga de copiar los datos de actividad a la base de datos de archivo BAM y, después, los quita de la base de datos de importación principal de BAM. Si la base de datos de archivo se bloquea después de copiar los datos y antes de efectuar la siguiente copia de seguridad, los datos se perderán.  
  
 La solución para evitar la pérdida de datos consiste en disponer de un solo paquete de archivo, que primero copia los datos antiguos de todas las actividades, después realiza la copia de seguridad de la base de datos de archivo BAM y, finalmente, descarga las particiones copiadas desde la base de datos de importación principal de BAM.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a>Para crear una vista con particiones en la base de datos de archivo de BAM en SQL Server 2008 SP1 o SQL Server 2008 R2  
  
1.  Abra SQL Server Management Studio.  
  
2.  Seleccione la base de datos de archivo de BAM y, a continuación, haga clic en **nueva consulta**.  
  
3.  En el **consulta** menú, elija **resultados a** y, a continuación, haga clic en **resultados a texto**.  
  
4.  Copie la siguiente secuencia de comandos SQL en el panel de consulta. Reemplace \<nombre de la actividad\> con el nombre de la actividad y reemplazar `<view type>` con cualquiera **instancias** ver para la instancia o **relaciones** para la vista de relaciones.  
  
    ```  
    set nocount on  
  
    declare @activityName as nvarchar(128)  
    declare @viewType as nvarchar(50)  
    set @activityName = N'<activity name>'-- Substitute your activity name here  
    set @viewType = N'<view type>'-- Substitute the view type here, either "Instances" or "Relationships"  
  
    declare @tableName nvarchar(128)  
    declare @viewName nvarchar(128)  
    declare @isFirstTable bit  
    declare @scriptLine nvarchar(300)  
  
    set @viewName = N'bam_' + @activityName + '_' + @viewType + 'View'  
    select N'SELECT Name FROM sysobjects where name = N''' + @viewName + ''' and type = ''V'''   
     + char(13) + char(10) + 'IF @@ROWCOUNT > 0 DROP VIEW ' + @viewName   
     + char(13) + char(10) + 'GO'  
  
    select 'CREATE VIEW ' +  @viewName + ' AS ' + char(13) + char(10)  
  
    declare instance_cursor cursor local for  
    select name from sysobjects   
    where name like N'bam_' + @activityName + '_' + @viewType + '_%' and type = 'U'  
  
    SET @isFirstTable = 1  
    OPEN instance_cursor  
    FETCH NEXT FROM instance_cursor INTO @tableName  
  
    WHILE @@fetch_status = 0   
    BEGIN  
  
    if @isFirstTable = 1  
    BEGIN  
    SET @scriptLine = N'SELECT * FROM [' + @tableName + ']'  
    SET @isFirstTable = 0  
    END  
    ELSE  
    SET @scriptLine = N'UNION ALL SELECT * FROM [' + @tableName + ']'  
  
    SELECT @scriptLine  
  
    FETCH NEXT FROM instance_cursor INTO @tableName  
    END  
    CLOSE instance_cursor  
    DEALLOCATE instance_cursor  
  
    select 'GO'  
    set nocount off  
    ```  
  
5.  Ejecutar la consulta.  
  
## <a name="see-also"></a>Vea también  
 [Paquetes DTS de BAM](../core/bam-dts-packages.md)   
 [Cómo realizar una copia del análisis de seguimiento y análisis de BAM bases de datos de servidor](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)