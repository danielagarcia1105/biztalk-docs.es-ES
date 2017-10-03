---
title: "Cómo quitar instancias de actividad incompletas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
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
ms.openlocfilehash: 99c2f77b6883b7ffba997551c4121013a4379267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-incomplete-activity-instances"></a><span data-ttu-id="b816d-102">Cómo quitar instancias de actividad incompletas</span><span class="sxs-lookup"><span data-stu-id="b816d-102">How to Remove Incomplete Activity Instances</span></span>
<span data-ttu-id="b816d-103">Al implementar un archivo de definición de BAM, se crean cinco tablas en la base de datos de importación principal de BAM por cada actividad definida en el archivo de definición.</span><span class="sxs-lookup"><span data-stu-id="b816d-103">When a BAM definition file is deployed, five tables are created in the BAM Primary Import database for each activity defined in the definition file.</span></span> <span data-ttu-id="b816d-104">Estas tablas son:</span><span class="sxs-lookup"><span data-stu-id="b816d-104">These tables are:</span></span>  
  
-   <span data-ttu-id="b816d-105">bam_`ActivityName`_Active</span><span class="sxs-lookup"><span data-stu-id="b816d-105">bam_`ActivityName`_Active</span></span>  
  
-   <span data-ttu-id="b816d-106">bam_`ActivityName`_Completed</span><span class="sxs-lookup"><span data-stu-id="b816d-106">bam_`ActivityName`_Completed</span></span>  
  
-   <span data-ttu-id="b816d-107">bam_`ActivityName`_ActiveRelationships</span><span class="sxs-lookup"><span data-stu-id="b816d-107">bam_`ActivityName`_ActiveRelationships</span></span>  
  
-   <span data-ttu-id="b816d-108">bam_`ActivityName`_CompletedRelationships</span><span class="sxs-lookup"><span data-stu-id="b816d-108">bam_`ActivityName`_CompletedRelationships</span></span>  
  
-   <span data-ttu-id="b816d-109">bam_`ActivityName`_Continuations</span><span class="sxs-lookup"><span data-stu-id="b816d-109">bam_`ActivityName`_Continuations</span></span>  
  
 <span data-ttu-id="b816d-110">Donde `ActivityName` es el nombre de la actividad que el usuario ha definido.</span><span class="sxs-lookup"><span data-stu-id="b816d-110">Where `ActivityName` is the name of the activity that the user has defined.</span></span>  
  
 <span data-ttu-id="b816d-111">Durante una ejecución normal, los datos incompletos permanecen en la tabla bam_`ActivityName`_Active.</span><span class="sxs-lookup"><span data-stu-id="b816d-111">During normal execution, incomplete data remains in the bam_`ActivityName`_Active table.</span></span> <span data-ttu-id="b816d-112">Si los datos contienen relaciones y referencias, habrá datos en bam\_`ActivityName`_ActiveRelationships tabla.</span><span class="sxs-lookup"><span data-stu-id="b816d-112">If the data has relations and references, then there will be data in the bam\_`ActivityName`_ActiveRelationships table.</span></span>  
  
 <span data-ttu-id="b816d-113">Durante el seguimiento de actividades que usan continuaciones, pueden haber instancias en las que una actividad se deja en estado incompleto en las bases de datos e BAM.</span><span class="sxs-lookup"><span data-stu-id="b816d-113">During the tracking of activities that use continuations, there may be instances in which an activity is left in an incomplete state in the BAM databases.</span></span> <span data-ttu-id="b816d-114">Puede usar el script de creación de procedimientos almacenados del final de este tema para crear un procedimiento almacenado que depure los registros incompletos.</span><span class="sxs-lookup"><span data-stu-id="b816d-114">You can use the stored procedure creation script at the end of this topic to create a stored procedure that will purge the incomplete records.</span></span>  
  
 <span data-ttu-id="b816d-115">Para crear el procedimiento almacenado, copie el script y ejecútelo en la base de datos de importación principal de BAM con la administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b816d-115">To create the stored procedure, copy the script and execute it against the BAM Primary Import database by using SQL Server Management.</span></span> <span data-ttu-id="b816d-116">La secuencia de comandos generará un procedimiento almacenado denominado **RemoveDanglingInstances** en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b816d-116">The script will generate a stored procedure named **RemoveDanglingInstances** in the database.</span></span>  
  
### <a name="to-create-the-removedanglinginstances-stored-procedure"></a><span data-ttu-id="b816d-117">Procedimiento para crear el procedimiento almacenado RemoveDanglingInstances</span><span class="sxs-lookup"><span data-stu-id="b816d-117">To create the RemoveDanglingInstances stored procedure</span></span>  
  
1.  <span data-ttu-id="b816d-118">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP1** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="b816d-118">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="b816d-119">En el **conectar al servidor** cuadro de diálogo, seleccione el servidor SQL server y el método de autenticación adecuado y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="b816d-119">In the **Connect to Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="b816d-120">Expanda el nombre del servidor, expanda **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b816d-120">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="b816d-121">Haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="b816d-121">Click **New Query**.</span></span>  
  
5.  <span data-ttu-id="b816d-122">Copie el script de creación de procedimientos almacenados y péguelo en el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="b816d-122">Copy the stored procedure creation script and paste it into the right pane.</span></span>  
  
6.  <span data-ttu-id="b816d-123">Haga clic en **Execute** para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="b816d-123">Click **Execute** to run the script.</span></span> <span data-ttu-id="b816d-124">El procedimiento almacenado resultante puede verse en la lista de procedimientos almacenados como dbo.RemoveDanglingInstances.</span><span class="sxs-lookup"><span data-stu-id="b816d-124">The resulting stored procedure can be viewed in the list of stored procedures as dbo.RemoveDanglingInstances.</span></span>  
  
### <a name="to-remove-incomplete-activity-instances"></a><span data-ttu-id="b816d-125">Procedimiento para quitar instancias de actividad incompletas</span><span class="sxs-lookup"><span data-stu-id="b816d-125">To remove incomplete activity instances</span></span>  
  
1.  <span data-ttu-id="b816d-126">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP1** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="b816d-126">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="b816d-127">En el **conectar al servidor** cuadro de diálogo, seleccione el servidor SQL server y el método de autenticación adecuado y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="b816d-127">In the **Connect to Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="b816d-128">Expanda el nombre del servidor, expanda **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b816d-128">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="b816d-129">Haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="b816d-129">Click **New Query**.</span></span>  
  
5.  <span data-ttu-id="b816d-130">En el panel derecho, escriba `exec RemoveDanglingInstances` y los parámetros adecuados para la operación de eliminación que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="b816d-130">In the right pane, type `exec RemoveDanglingInstances` and the appropriate parameters for the remove operation you are performing.</span></span> <span data-ttu-id="b816d-131">Por ejemplo, para quitar todas las instancias incompletas de la actividad de pedido de compra, escriba `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span><span class="sxs-lookup"><span data-stu-id="b816d-131">For example, to remove all incomplete instances of the Purchase Order activity, type `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span></span>  
  
6.  <span data-ttu-id="b816d-132">Haga clic en **Execute** para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="b816d-132">Click **Execute** to run the script.</span></span>  
  
## <a name="removedanglinginstances-usage-examples"></a><span data-ttu-id="b816d-133">Ejemplos de uso de RemoveDanglingInstances</span><span class="sxs-lookup"><span data-stu-id="b816d-133">RemoveDanglingInstances Usage Examples</span></span>  
 <span data-ttu-id="b816d-134">El procedimiento almacenado puede recibir cuatro parámetros:</span><span class="sxs-lookup"><span data-stu-id="b816d-134">The stored procedure can receive four parameters:</span></span>  
  
|<span data-ttu-id="b816d-135">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b816d-135">Parameter</span></span>|<span data-ttu-id="b816d-136">Description</span><span class="sxs-lookup"><span data-stu-id="b816d-136">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b816d-137">@ActivityName nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="b816d-137">@ActivityName nvarchar(128)</span></span>|<span data-ttu-id="b816d-138">Especifica el nombre de la instancia de actividad incompleta que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="b816d-138">Specifies the name of the incomplete activity instance to remove.</span></span>|  
|<span data-ttu-id="b816d-139">@ActivityId nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="b816d-139">@ActivityId nvarchar(128)</span></span>|<span data-ttu-id="b816d-140">(Opcional) Especifica que el procedimiento almacenado quita solo la instancia pendiente con el identificador de instancia especificado.</span><span class="sxs-lookup"><span data-stu-id="b816d-140">(Optional) Specifies that the stored procedure remove only the dangling instance with the specified instance identifier.</span></span>|  
|<span data-ttu-id="b816d-141">@DateThresholdfecha y hora</span><span class="sxs-lookup"><span data-stu-id="b816d-141">@DateThreshold datetime</span></span>|<span data-ttu-id="b816d-142">(Opcional) Especifica que se quitan todas las instancias activas de la tabla activa que sean anteriores (no iguales y anteriores, sino únicamente anteriores) a la fecha dada.</span><span class="sxs-lookup"><span data-stu-id="b816d-142">(Optional) Specifies that all the active instances in the active table that are older (not equal to and older, only older) than the given date are removed.</span></span>|  
|<span data-ttu-id="b816d-143">@NewTableExtensionnvarchar (30)</span><span class="sxs-lookup"><span data-stu-id="b816d-143">@NewTableExtension nvarchar(30)</span></span>|<span data-ttu-id="b816d-144">(Opcional) Especifica que el procedimiento almacenado crea tres tablas nuevas al concatenar la extensión proporcionada con las tablas de actividad existentes.</span><span class="sxs-lookup"><span data-stu-id="b816d-144">(Optional) Specifies that the stored procedure creates three new tables by concatenating the supplied extension to the existing activity tables.</span></span><br /><br /> <span data-ttu-id="b816d-145">Las tablas resultantes serán las siguientes:</span><span class="sxs-lookup"><span data-stu-id="b816d-145">The resulting tables will be:</span></span><br /><br /> <span data-ttu-id="b816d-146">bam_ActivityName_Active_\<extensión ></span><span class="sxs-lookup"><span data-stu-id="b816d-146">bam_ActivityName_Active_\<Extension></span></span><br /><br /> <span data-ttu-id="b816d-147">bam_ActivityName_ActiveRelationships_\<extensión ></span><span class="sxs-lookup"><span data-stu-id="b816d-147">bam_ActivityName_ActiveRelationships_\<Extension></span></span><br /><br /> <span data-ttu-id="b816d-148">bam_ActivityName_Continuations_\<extensión ></span><span class="sxs-lookup"><span data-stu-id="b816d-148">bam_ActivityName_Continuations_\<Extension></span></span><br /><br /> <span data-ttu-id="b816d-149">Las instancias incompletas se mueven a las tablas nuevas en lugar de purgarse en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b816d-149">The incomplete instances are moved to the new tables rather than being purged from the database.</span></span><br /><br /> <span data-ttu-id="b816d-150">Si las tablas ya existen, el procedimiento almacenado las vuelve a usar; de lo contrario, se crean.</span><span class="sxs-lookup"><span data-stu-id="b816d-150">If the tables already exist, the stored procedure reuses them; otherwise they are created.</span></span> <span data-ttu-id="b816d-151">**Importante:** si las tablas ya existen, el procedimiento almacenado se supone que sus esquemas coinciden con los que se utilizarían si se hubieran creado.</span><span class="sxs-lookup"><span data-stu-id="b816d-151">**Important:**  If the tables already exist, the stored procedure assumes that their schemas match the ones that would be used if they were created.</span></span> <span data-ttu-id="b816d-152">Si un esquema no coincide, el procedimiento almacenado no podrá insertar los registros y se producirá un error en la operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="b816d-152">If a schema does not match, the stored procedure will fail to insert the records and the remove operation will fail.</span></span>|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 <span data-ttu-id="b816d-153">Quita todas las instancias activas de la actividad 'PurchaseOrder' de las tablas activas, de relaciones activas y de continuaciones.</span><span class="sxs-lookup"><span data-stu-id="b816d-153">Removes all active instances of the 'PurchaseOrder' activity in the active, active relationships, and continuations tables.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 <span data-ttu-id="b816d-154">Quita solo la instancia de actividad que tiene un Id. de actividad de 'PO220567' de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder'.</span><span class="sxs-lookup"><span data-stu-id="b816d-154">Removes only the activity instance that has an Activity ID of 'PO220567' from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="b816d-155">Quita todas las instancias de actividad que tienen una hora LastModified anterior a las 7:27:03.533 p.m. del 2 de febrero de 2005 de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder'.</span><span class="sxs-lookup"><span data-stu-id="b816d-155">Removes all the activity instances that have a LastModified time that is older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="b816d-156">Quita la instancia de actividad cuyo identificador de actividad es PO220567 solo si la columna LastModified es anterior a las 7:27:03.533 p.m. del 2 de febrero de 2005.</span><span class="sxs-lookup"><span data-stu-id="b816d-156">Removes the activity instance whose activity ID is PO220567 only if its LastModified column is older than Feb 2nd, 2005 7:27:03.533 PM.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 <span data-ttu-id="b816d-157">Crea las siguientes tablas en la base de datos:</span><span class="sxs-lookup"><span data-stu-id="b816d-157">Creates the following tables in the database:</span></span>  
  
 <span data-ttu-id="b816d-158">bam_PurchaseOrder_Active_Dangling</span><span class="sxs-lookup"><span data-stu-id="b816d-158">bam_PurchaseOrder_Active_Dangling</span></span>  
  
 <span data-ttu-id="b816d-159">bam_PurchaseOrder_ActiveRelationships_Dangling</span><span class="sxs-lookup"><span data-stu-id="b816d-159">bam_PurchaseOrder_ActiveRelationships_Dangling</span></span>  
  
 <span data-ttu-id="b816d-160">bam_PurchaseOrder_Continuations_Dangling</span><span class="sxs-lookup"><span data-stu-id="b816d-160">bam_PurchaseOrder_Continuations_Dangling</span></span>  
  
 <span data-ttu-id="b816d-161">El procedimiento almacenado copia todas las instancias de actividad incompletas que son anteriores a las 7:27:03.533 p.m. del 2 de febrero de 2005 de las tablas activas, de relaciones activas y de continuaciones para la actividad 'PurchaseOrder' y las inserta en tablas que se acaban de crear.</span><span class="sxs-lookup"><span data-stu-id="b816d-161">The stored procedure copies all incomplete activity instances that are older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity, and inserts them into the newly created tables.</span></span> <span data-ttu-id="b816d-162">A continuación, se quitan las instancias de actividad copiadas de las tablas activas, de relaciones activas y de continuaciones.</span><span class="sxs-lookup"><span data-stu-id="b816d-162">The copied activity instances are then removed from the active, active relationships, and continuations tables.</span></span>  
  
## <a name="stored-procedure-creation-script"></a><span data-ttu-id="b816d-163">Secuencia de comandos de creación de procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="b816d-163">Stored Procedure Creation Script</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b816d-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="b816d-164">See Also</span></span>  
 [<span data-ttu-id="b816d-165">Administrar bases de datos BAM</span><span class="sxs-lookup"><span data-stu-id="b816d-165">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)