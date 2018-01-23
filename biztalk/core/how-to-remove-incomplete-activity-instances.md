---
title: Quitar instancias de actividad incompletas | Documentos de Microsoft
description: "Ejecute el script personalizado de RemoveDanglingInstances SQL para quitar instancias incompletas de la base de datos de importación principal de BAM de BizTalk Server"
ms.custom: 
ms.date: 01/18/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7060578c-6267-487b-8530-efa18f9431ce
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 542d92b838b1638a2d018c6325d4c40467545c42
ms.sourcegitcommit: 9e7a7dc5544d30d4523c0b3cdaa59f4890e7a4e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="remove-incomplete-activity-instances"></a>Quitar instancias de actividad incompletas
Al implementar un archivo de definición de BAM, se crean cinco tablas en la base de datos de importación principal de BAM por cada actividad definida en el archivo de definición. Estas tablas son:  
  
-   bam_`ActivityName`_Active  
  
-   bam_`ActivityName`_Completed  
  
-   bam_`ActivityName`_ActiveRelationships  
  
-   bam_`ActivityName`_CompletedRelationships  
  
-   bam_`ActivityName`_Continuations  
  
 Donde `ActivityName` es el nombre de la actividad que el usuario ha definido.  
  
 Durante una ejecución normal, los datos incompletos permanecen en la tabla bam_`ActivityName`_Active. Si los datos contienen relaciones y referencias, habrá datos en bam\_`ActivityName`_ActiveRelationships tabla.  
  
 Durante el seguimiento de actividades que usan continuaciones, pueden haber instancias en las que una actividad se deja en estado incompleto en las bases de datos e BAM. Puede usar el script de creación de procedimientos almacenados del final de este tema para crear un procedimiento almacenado que depure los registros incompletos.  
  
 Para crear el procedimiento almacenado, copie el script y ejecútelo en la base de datos de importación principal de BAM con la administración de SQL Server. La secuencia de comandos generará un procedimiento almacenado denominado **RemoveDanglingInstances** en la base de datos.  
  
## <a name="create-the-removedanglinginstances-stored-procedure"></a>Crear el procedimiento almacenado de RemoveDanglingInstances  
  
1.  Abra **SQL Server Management Studio**y conectarse a SQL server.
  
2.  Expanda el nombre del servidor, expanda **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.  
  
3.  Haga clic en **Nueva consulta**.  
  
4.  Copie el script de creación de procedimientos almacenados y péguelo en el panel de consulta.  
  
5.  **Ejecutar** la secuencia de comandos. El procedimiento almacenado resultante puede verse en la lista de procedimientos almacenados como dbo.RemoveDanglingInstances.  
  
## <a name="remove-incomplete-activity-instances"></a>Quitar instancias de actividad incompletas  
  
1.  Abra **SQL Server Management Studio**y conectarse a SQL server.
  
2.  Expanda el nombre del servidor, expanda **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.  
  
3.  Haga clic en **Nueva consulta**.  
  
4.  En el panel de consulta, escriba `exec RemoveDanglingInstances` y los parámetros adecuados para la operación de eliminación que se va a realizar. Por ejemplo, para quitar todas las instancias incompletas de la actividad de pedido de compra, escriba `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.  
  
5.  **Ejecutar** la secuencia de comandos.  
  
## <a name="removedanglinginstances-usage-examples"></a>Ejemplos de uso de RemoveDanglingInstances  
 El procedimiento almacenado puede recibir cuatro parámetros:  
  
|Parámetro|Description|  
|---------------|-----------------|  
|@ActivityName nvarchar(128)|Especifica el nombre de la instancia de actividad incompleta que se va a quitar.|  
|@ActivityId nvarchar(128)|(Opcional) Especifica que el procedimiento almacenado quita solo la instancia pendiente con el identificador de instancia especificado.|  
|@DateThresholdfecha y hora|(Opcional) Especifica que se quitan todas las instancias activas de la tabla activa que sean anteriores (no iguales y anteriores, sino únicamente anteriores) a la fecha dada.|  
|@NewTableExtensionnvarchar (30)|(Opcional) Especifica que el procedimiento almacenado crea tres tablas nuevas al concatenar la extensión proporcionada con las tablas de actividad existentes.<br /><br /> Las tablas resultantes serán las siguientes:<br /><br /> bam_ActivityName_Active_\<Extension\><br /><br /> bam_ActivityName_ActiveRelationships_\<Extension\><br /><br /> bam_ActivityName_Continuations_\<Extension\><br /><br /> Las instancias incompletas se mueven a las tablas nuevas en lugar de purgarse en la base de datos.<br /><br /> Si las tablas ya existen, el procedimiento almacenado las vuelve a usar; de lo contrario, se crean. **Importante:** si las tablas ya existen, el procedimiento almacenado se supone que sus esquemas coinciden con los que se utilizarían si se hubieran creado. Si un esquema no coincide, el procedimiento almacenado no podrá insertar los registros y se producirá un error en la operación de eliminación.|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 Quita todas las instancias activas de la actividad 'PurchaseOrder' de las tablas activas, de relaciones activas y de continuaciones.  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 Quita solo la instancia de actividad que tiene un Id. de actividad de 'PO220567' de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder'.  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 Quita todas las instancias de actividad que tienen una hora LastModified anterior a las 7:27:03.533 p.m. del 2 de febrero de 2005 de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder'.  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 Quita la instancia de actividad cuyo identificador de actividad es PO220567 solo si la columna LastModified es anterior a las 7:27:03.533 p.m. del 2 de febrero de 2005.  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 Crea las siguientes tablas en la base de datos:  
  
 bam_PurchaseOrder_Active_Dangling  
  
 bam_PurchaseOrder_ActiveRelationships_Dangling  
  
 bam_PurchaseOrder_Continuations_Dangling  
  
 El procedimiento almacenado copia todas las instancias de actividad incompletas que son anteriores a las 7:27:03.533 p.m. del 2 de febrero de 2005 de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder' y las inserta en tablas que se acaban de crear. A continuación, se quitan las instancias de actividad copiadas de las tablas activas, de relaciones activas y de continuaciones.  
  
## <a name="stored-procedure-creation-script"></a>Secuencia de comandos de creación de procedimientos almacenados  
  
```  
EXEC sp_stored_procedures @sp_name = 'RemoveDanglingInstances'  
IF @@ROWCOUNT > 0 DROP PROCEDURE RemoveDanglingInstances  
GO  
  
CREATE PROCEDURE RemoveDanglingInstances  
    @ActivityName nvarchar(128),  
    @ActivityId nvarchar(128) = NULL,  
    @DateThreshold datetime = NULL,  
    @NewTableExtension nvarchar(30) = NULL  
AS  
    DECLARE @QueryString nvarchar(4000)  
    DECLARE @ActiveTableName sysname  
    DECLARE @ActiveRelationshipsTableName sysname  
    DECLARE @ContinuationsTableName sysname  
    DECLARE @DanglingActiveTableName sysname  
    DECLARE @DanglingActiveRelationshipsTableName sysname  
    DECLARE @DanglingContinuationsTableName sysname  
  
    SET @ActiveTableName = 'bam_' + @ActivityName + '_Active'  
    SET @ActiveRelationshipsTableName = 'bam_' + @ActivityName + '_ActiveRelationships'  
    SET @ContinuationsTableName = 'bam_' + @ActivityName + '_Continuations'  
  
    SET TRANSACTION ISOLATION LEVEL READ COMMITTED  
    BEGIN TRAN  
  
    DECLARE @LockActivity nvarchar(128)  
    SELECT @LockActivity = ActivityName  
    FROM bam_Metadata_Activities WITH (XLOCK)  
    WHERE ActivityName = @ActivityName  
  
    EXEC sp_tables @table_name = #DanglingActivities  
    IF @@ROWCOUNT > 0 DROP TABLE #DanglingActivities  
  
    CREATE TABLE #DanglingActivities(ActivityID nvarchar(128) PRIMARY KEY)  
  
    SET @QueryString = N'INSERT INTO #DanglingActivities (ActivityID) SELECT ActivityID FROM [bam_' + @ActivityName + '_Active]'  
  
    IF (@DateThreshold is not NULL) OR (@ActivityId is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' WHERE'  
    END  
  
    IF (@DateThreshold is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' LastModified < N''' + CONVERT(nvarchar(50), @DateThreshold, 109) + ''''  
        IF (@ActivityId is not NULL)  
        BEGIN  
            SET @QueryString = @QueryString + ' AND'  
        END  
    END  
  
    IF (@ActivityId is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' ActivityID = N''' + @ActivityId + ''''  
    END  
  
    EXEC sp_executesql @QueryString  
    SELECT * FROM #DanglingActivities  
  
    SET @QueryString = N''  
  
    -- If the user gave a table extension, the dangling instances will be inserted  
    -- into that table.   
    IF (isnull(@NewTableExtension, '') <> '')  
    BEGIN  
        SET @DanglingActiveTableName = @ActiveTableName + '_' + @NewTableExtension  
        SET @DanglingActiveRelationshipsTableName = @ActiveRelationshipsTableName + '_' + @NewTableExtension  
        SET @DanglingContinuationsTableName = @ContinuationsTableName + '_' + @NewTableExtension  
  
        -- If the table for the dangling instances exists then insert into it  
        -- If the table does not exist, then create the dangling instances table  
        -- and then insert into it. SELECT INTO will do that.  
        EXEC sp_tables @table_name = @DanglingActiveTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingActiveTableName + '] SELECT active.* FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingActiveTableName + '] FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
  
        -- Now do what you did for the Active Instances table for the   
        -- ActiveRelationships table  
        EXEC sp_tables @table_name = @DanglingActiveRelationshipsTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingActiveRelationshipsTableName + '] SELECT active.* FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingActiveRelationshipsTableName + '] FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
  
        -- And finally for the continuations table  
        EXEC sp_tables @table_name = @DanglingContinuationsTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingContinuationsTableName + '] SELECT active.* FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingContinuationsTableName + '] FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
    END  
  
    -- Remove the dangling instances from the Active Instances Table  
    SET @QueryString = 'DELETE FROM [' + @ActiveTableName + '] FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    SET @QueryString = 'DELETE FROM [' + @ActiveRelationshipsTableName + '] FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    SET @QueryString = 'DELETE FROM [' + @ContinuationsTableName + '] FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    DROP TABLE #DanglingActivities  
  
    COMMIT TRAN      
GO  
```  

## <a name="another-method-of-resolving-incomplete-instances"></a>Otro método de resolución de instancias incompletas
También puede resolver instancias de actividad incompletas de la base de datos BAMPrimaryImport mediante una consulta SQL. Vea [resolver instancias de actividad incompletas](how-to-resolve-incomplete-activity-instances.md).

## <a name="see-also"></a>Vea también  
 [Administrar bases de datos BAM](../core/managing-bam-databases.md)
