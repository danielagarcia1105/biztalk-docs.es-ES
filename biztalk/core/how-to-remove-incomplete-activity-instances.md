---
title: Quitar instancias de actividad incompletas | Microsoft Docs
description: Ejecutar el script personalizado de RemoveDanglingInstances SQL para quitar instancias incompletas de la base de datos de importación principal de BAM en BizTalk Server
ms.custom: ''
ms.date: 01/18/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7060578c-6267-487b-8530-efa18f9431ce
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a4ed81978dd275be8eb0348ff15dc8748258239
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977173"
---
# <a name="remove-incomplete-activity-instances"></a><span data-ttu-id="5d5e5-103">Quitar instancias de actividad incompletas</span><span class="sxs-lookup"><span data-stu-id="5d5e5-103">Remove Incomplete Activity Instances</span></span>
<span data-ttu-id="5d5e5-104">Al implementar un archivo de definición de BAM, se crean cinco tablas en la base de datos de importación principal de BAM por cada actividad definida en el archivo de definición.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-104">When a BAM definition file is deployed, five tables are created in the BAM Primary Import database for each activity defined in the definition file.</span></span> <span data-ttu-id="5d5e5-105">Estas tablas son:</span><span class="sxs-lookup"><span data-stu-id="5d5e5-105">These tables are:</span></span>  
  
- <span data-ttu-id="5d5e5-106">bam_`ActivityName`_Active</span><span class="sxs-lookup"><span data-stu-id="5d5e5-106">bam_`ActivityName`_Active</span></span>  
  
- <span data-ttu-id="5d5e5-107">bam_`ActivityName`_Completed</span><span class="sxs-lookup"><span data-stu-id="5d5e5-107">bam_`ActivityName`_Completed</span></span>  
  
- <span data-ttu-id="5d5e5-108">bam_`ActivityName`_ActiveRelationships</span><span class="sxs-lookup"><span data-stu-id="5d5e5-108">bam_`ActivityName`_ActiveRelationships</span></span>  
  
- <span data-ttu-id="5d5e5-109">bam_`ActivityName`_CompletedRelationships</span><span class="sxs-lookup"><span data-stu-id="5d5e5-109">bam_`ActivityName`_CompletedRelationships</span></span>  
  
- <span data-ttu-id="5d5e5-110">bam_`ActivityName`_Continuations</span><span class="sxs-lookup"><span data-stu-id="5d5e5-110">bam_`ActivityName`_Continuations</span></span>  
  
  <span data-ttu-id="5d5e5-111">Donde `ActivityName` es el nombre de la actividad que el usuario ha definido.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-111">Where `ActivityName` is the name of the activity that the user has defined.</span></span>  
  
  <span data-ttu-id="5d5e5-112">Durante la ejecución normal, los datos incompletos permanecen en la tabla bam_`ActivityName`*tabla activa. Si los datos tienen relaciones y referencias, habrá datos en bam\\*`ActivityName`tabla _ActiveRelationships.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-112">During normal execution, incomplete data remains in the bam_`ActivityName`*Active table. If the data has relations and references, then there will be data in the bam\\*`ActivityName`_ActiveRelationships table.</span></span>  
  
  <span data-ttu-id="5d5e5-113">Durante el seguimiento de actividades que usan continuaciones, pueden haber instancias en las que una actividad se deja en estado incompleto en las bases de datos e BAM.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-113">During the tracking of activities that use continuations, there may be instances in which an activity is left in an incomplete state in the BAM databases.</span></span> <span data-ttu-id="5d5e5-114">Puede usar el script de creación de procedimientos almacenados del final de este tema para crear un procedimiento almacenado que depure los registros incompletos.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-114">You can use the stored procedure creation script at the end of this topic to create a stored procedure that will purge the incomplete records.</span></span>  
  
  <span data-ttu-id="5d5e5-115">Para crear el procedimiento almacenado, copie el script y ejecútelo en la base de datos de importación principal de BAM con la administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-115">To create the stored procedure, copy the script and execute it against the BAM Primary Import database by using SQL Server Management.</span></span> <span data-ttu-id="5d5e5-116">El script generará un procedimiento almacenado denominado **RemoveDanglingInstances** en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-116">The script will generate a stored procedure named **RemoveDanglingInstances** in the database.</span></span>  
  
## <a name="create-the-removedanglinginstances-stored-procedure"></a><span data-ttu-id="5d5e5-117">Crear el procedimiento almacenado de RemoveDanglingInstances</span><span class="sxs-lookup"><span data-stu-id="5d5e5-117">Create the RemoveDanglingInstances stored procedure</span></span>  
  
1.  <span data-ttu-id="5d5e5-118">Abra **SQL Server Management Studio**y conectarse a SQL server.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-118">Open **SQL Server Management Studio**, and connect to the SQL server.</span></span>
  
2.  <span data-ttu-id="5d5e5-119">Expanda el nombre del servidor, **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-119">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
3.  <span data-ttu-id="5d5e5-120">Haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-120">Click **New Query**.</span></span>  
  
4.  <span data-ttu-id="5d5e5-121">Copie el script de creación de procedimientos almacenados y péguelo en el panel de consulta.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-121">Copy the stored procedure creation script, and paste it into the query pane.</span></span>  
  
5.  <span data-ttu-id="5d5e5-122">**Ejecutar** la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-122">**Execute** the script.</span></span> <span data-ttu-id="5d5e5-123">El procedimiento almacenado resultante puede verse en la lista de procedimientos almacenados como dbo.RemoveDanglingInstances.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-123">The resulting stored procedure can be viewed in the list of stored procedures as dbo.RemoveDanglingInstances.</span></span>  
  
## <a name="remove-incomplete-activity-instances"></a><span data-ttu-id="5d5e5-124">Quitar instancias de actividad incompletas</span><span class="sxs-lookup"><span data-stu-id="5d5e5-124">Remove incomplete activity instances</span></span>  
  
1.  <span data-ttu-id="5d5e5-125">Abra **SQL Server Management Studio**y conectarse a SQL server.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-125">Open **SQL Server Management Studio**, and connect to the SQL server.</span></span>
  
2.  <span data-ttu-id="5d5e5-126">Expanda el nombre del servidor, **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-126">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
3.  <span data-ttu-id="5d5e5-127">Haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-127">Click **New Query**.</span></span>  
  
4.  <span data-ttu-id="5d5e5-128">En el panel consulta, escriba `exec RemoveDanglingInstances` y los parámetros adecuados para la operación de eliminación que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-128">In the query pane, type `exec RemoveDanglingInstances` and the appropriate parameters for the remove operation you are performing.</span></span> <span data-ttu-id="5d5e5-129">Por ejemplo, para quitar todas las instancias incompletas de la actividad de pedido de compra, escriba `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-129">For example, to remove all incomplete instances of the Purchase Order activity, type `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span></span>  
  
5.  <span data-ttu-id="5d5e5-130">**Ejecutar** la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-130">**Execute** the script.</span></span>  
  
## <a name="removedanglinginstances-usage-examples"></a><span data-ttu-id="5d5e5-131">Ejemplos de uso de RemoveDanglingInstances</span><span class="sxs-lookup"><span data-stu-id="5d5e5-131">RemoveDanglingInstances Usage Examples</span></span>  
 <span data-ttu-id="5d5e5-132">El procedimiento almacenado puede recibir cuatro parámetros:</span><span class="sxs-lookup"><span data-stu-id="5d5e5-132">The stored procedure can receive four parameters:</span></span>  
  
|<span data-ttu-id="5d5e5-133">Parámetro</span><span class="sxs-lookup"><span data-stu-id="5d5e5-133">Parameter</span></span>|<span data-ttu-id="5d5e5-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d5e5-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d5e5-135">@ActivityName nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="5d5e5-135">@ActivityName nvarchar(128)</span></span>|<span data-ttu-id="5d5e5-136">Especifica el nombre de la instancia de actividad incompleta que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-136">Specifies the name of the incomplete activity instance to remove.</span></span>|  
|<span data-ttu-id="5d5e5-137">@ActivityId nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="5d5e5-137">@ActivityId nvarchar(128)</span></span>|<span data-ttu-id="5d5e5-138">(Opcional) Especifica que el procedimiento almacenado quita solo la instancia pendiente con el identificador de instancia especificado.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-138">(Optional) Specifies that the stored procedure remove only the dangling instance with the specified instance identifier.</span></span>|  
|<span data-ttu-id="5d5e5-139">@DateThreshold fecha y hora</span><span class="sxs-lookup"><span data-stu-id="5d5e5-139">@DateThreshold datetime</span></span>|<span data-ttu-id="5d5e5-140">(Opcional) Especifica que se quitan todas las instancias activas de la tabla activa que sean anteriores (no iguales y anteriores, sino únicamente anteriores) a la fecha dada.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-140">(Optional) Specifies that all the active instances in the active table that are older (not equal to and older, only older) than the given date are removed.</span></span>|  
|<span data-ttu-id="5d5e5-141">@NewTableExtension nvarchar (30)</span><span class="sxs-lookup"><span data-stu-id="5d5e5-141">@NewTableExtension nvarchar(30)</span></span>|<span data-ttu-id="5d5e5-142">(Opcional) Especifica que el procedimiento almacenado crea tres tablas nuevas al concatenar la extensión proporcionada con las tablas de actividad existentes.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-142">(Optional) Specifies that the stored procedure creates three new tables by concatenating the supplied extension to the existing activity tables.</span></span><br /><br /> <span data-ttu-id="5d5e5-143">Las tablas resultantes serán las siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d5e5-143">The resulting tables will be:</span></span><br /><br /> <span data-ttu-id="5d5e5-144">bam_ActivityName_Active_\<Extension\></span><span class="sxs-lookup"><span data-stu-id="5d5e5-144">bam_ActivityName_Active_\<Extension\></span></span><br /><br /> <span data-ttu-id="5d5e5-145">bam_ActivityName_ActiveRelationships_\<Extension\></span><span class="sxs-lookup"><span data-stu-id="5d5e5-145">bam_ActivityName_ActiveRelationships_\<Extension\></span></span><br /><br /> <span data-ttu-id="5d5e5-146">bam_ActivityName_Continuations_\<Extension\></span><span class="sxs-lookup"><span data-stu-id="5d5e5-146">bam_ActivityName_Continuations_\<Extension\></span></span><br /><br /> <span data-ttu-id="5d5e5-147">Las instancias incompletas se mueven a las tablas nuevas en lugar de purgarse en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-147">The incomplete instances are moved to the new tables rather than being purged from the database.</span></span><br /><br /> <span data-ttu-id="5d5e5-148">Si las tablas ya existen, el procedimiento almacenado las vuelve a usar; de lo contrario, se crean.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-148">If the tables already exist, the stored procedure reuses them; otherwise they are created.</span></span> <span data-ttu-id="5d5e5-149">**Importante:** si las tablas ya existen, en el procedimiento almacenado se da por supuesto que sus esquemas coinciden con los que se usaría si se hubieran creado.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-149">**Important:**  If the tables already exist, the stored procedure assumes that their schemas match the ones that would be used if they were created.</span></span> <span data-ttu-id="5d5e5-150">Si un esquema no coincide, el procedimiento almacenado no podrá insertar los registros y se producirá un error en la operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-150">If a schema does not match, the stored procedure will fail to insert the records and the remove operation will fail.</span></span>|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 <span data-ttu-id="5d5e5-151">Quita todas las instancias activas de la actividad 'PurchaseOrder' de las tablas activas, de relaciones activas y de continuaciones.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-151">Removes all active instances of the 'PurchaseOrder' activity in the active, active relationships, and continuations tables.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 <span data-ttu-id="5d5e5-152">Quita solo la instancia de actividad que tiene un Id. de actividad de 'PO220567' de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder'.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-152">Removes only the activity instance that has an Activity ID of 'PO220567' from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="5d5e5-153">Quita todas las instancias de actividad que tienen una hora LastModified anterior a las 7:27:03.533 p.m. del 2 de febrero de 2005 de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder'.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-153">Removes all the activity instances that have a LastModified time that is older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="5d5e5-154">Quita la instancia de actividad cuyo identificador de actividad es PO220567 solo si la columna LastModified es anterior a las 7:27:03.533 p.m. del 2 de febrero de 2005.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-154">Removes the activity instance whose activity ID is PO220567 only if its LastModified column is older than Feb 2nd, 2005 7:27:03.533 PM.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 <span data-ttu-id="5d5e5-155">Crea las siguientes tablas en la base de datos:</span><span class="sxs-lookup"><span data-stu-id="5d5e5-155">Creates the following tables in the database:</span></span>  
  
 <span data-ttu-id="5d5e5-156">bam_PurchaseOrder_Active_Dangling</span><span class="sxs-lookup"><span data-stu-id="5d5e5-156">bam_PurchaseOrder_Active_Dangling</span></span>  
  
 <span data-ttu-id="5d5e5-157">bam_PurchaseOrder_ActiveRelationships_Dangling</span><span class="sxs-lookup"><span data-stu-id="5d5e5-157">bam_PurchaseOrder_ActiveRelationships_Dangling</span></span>  
  
 <span data-ttu-id="5d5e5-158">bam_PurchaseOrder_Continuations_Dangling</span><span class="sxs-lookup"><span data-stu-id="5d5e5-158">bam_PurchaseOrder_Continuations_Dangling</span></span>  
  
 <span data-ttu-id="5d5e5-159">El procedimiento almacenado copia todas las instancias de actividad incompletas que son anteriores a las 7:27:03.533 p.m. del 2 de febrero de 2005 de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder' y las inserta en tablas que se acaban de crear.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-159">The stored procedure copies all incomplete activity instances that are older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity, and inserts them into the newly created tables.</span></span> <span data-ttu-id="5d5e5-160">A continuación, se quitan las instancias de actividad copiadas de las tablas activas, de relaciones activas y de continuaciones.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-160">The copied activity instances are then removed from the active, active relationships, and continuations tables.</span></span>  
  
## <a name="stored-procedure-creation-script"></a><span data-ttu-id="5d5e5-161">Secuencia de comandos de creación de procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="5d5e5-161">Stored Procedure Creation Script</span></span>  
  
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

## <a name="another-method-of-resolving-incomplete-instances"></a><span data-ttu-id="5d5e5-162">Otro método para resolver instancias incompletas</span><span class="sxs-lookup"><span data-stu-id="5d5e5-162">Another method of resolving incomplete instances</span></span>
<span data-ttu-id="5d5e5-163">También puede resolver instancias de actividad incompletas de la base de datos BAMPrimaryImport mediante el uso de una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="5d5e5-163">You can also resolve incomplete activity instances from the BAMPrimaryImport database by using a SQL query.</span></span> <span data-ttu-id="5d5e5-164">Consulte [resolver instancias de actividad incompletas](how-to-resolve-incomplete-activity-instances.md).</span><span class="sxs-lookup"><span data-stu-id="5d5e5-164">See [Resolve incomplete activity instances](how-to-resolve-incomplete-activity-instances.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d5e5-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d5e5-165">See Also</span></span>  
 [<span data-ttu-id="5d5e5-166">Administración de bases de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="5d5e5-166">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
