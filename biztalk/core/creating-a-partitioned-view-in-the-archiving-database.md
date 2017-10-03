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
ms.openlocfilehash: 4f6000c95b94570b5f058073537fa926fd1651c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a><span data-ttu-id="d5d8d-102">Crear una vista con particiones en la base de datos de archivo</span><span class="sxs-lookup"><span data-stu-id="d5d8d-102">Creating a Partitioned View in the Archiving Database</span></span>
<span data-ttu-id="d5d8d-103">Al ejecutar el paquete de mantenimiento de datos de BAM (BAM_DM_`<activity name>`) BAM copia cada partición de la base de datos de importación principal a una tabla separada de la base de datos de archivos BAM.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-103">When you run the BAM data maintenance package (BAM_DM_`<activity name>`) BAM copies each partition in the BAM Primary Import database to a separate table in the BAM Archive database.</span></span> <span data-ttu-id="d5d8d-104">Si desasocia la base de datos de archivo y vuelve a asociarla para las consultas, resultará difícil localizar los datos para la consulta.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-104">If you detach the archive database and reattach it for querying, it will be difficult to locate the data for your query.</span></span>  
  
 <span data-ttu-id="d5d8d-105">Puede crear vistas con particiones en la base de datos de archivo BAM para facilitar la localización de los datos.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-105">You can create partitioned views in the BAM Archive database to facilitate locating the data.</span></span> <span data-ttu-id="d5d8d-106">BAM admite hasta 253 particiones.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-106">BAM supports up to 253 partitions.</span></span> <span data-ttu-id="d5d8d-107">BAM genera, para cada actividad, un paquete DTS de mantenimiento de datos de BAM que se encarga de copiar los datos de actividad a la base de datos de archivo BAM y, después, los quita de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-107">For each activity, BAM generates one BAM data maintenance DTS package, which copies the activity data to the BAM Archive database and then removes it from the BAM Primary Import database.</span></span> <span data-ttu-id="d5d8d-108">Si la base de datos de archivo se bloquea después de copiar los datos y antes de efectuar la siguiente copia de seguridad, los datos se perderán.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-108">If the archive database fails after the data is copied but before the next backup, data is lost.</span></span>  
  
 <span data-ttu-id="d5d8d-109">La solución para evitar la pérdida de datos consiste en disponer de un solo paquete de archivo, que primero copia los datos antiguos de todas las actividades, después realiza la copia de seguridad de la base de datos de archivo BAM y, finalmente, descarga las particiones copiadas desde la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-109">The solution to prevent lost data is to have a single archiving package, which first copies the old data from all activities, then backs up the BAM Archive database, and finally drops the partitions that were copied from the BAM Primary Import database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5d8d-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d5d8d-110">Prerequisites</span></span>  
 <span data-ttu-id="d5d8d-111">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-111">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a><span data-ttu-id="d5d8d-112">Para crear una vista con particiones en la base de datos de archivo de BAM en SQL Server 2008 SP1 o SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d5d8d-112">To create a partitioned view in the BAM Archive database in SQL Server 2008 SP1 or SQL Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="d5d8d-113">Abra SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-113">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="d5d8d-114">Seleccione la base de datos de archivo de BAM y, a continuación, haga clic en **nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-114">Select the BAM Archive database, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d5d8d-115">En el **consulta** menú, elija **resultados a** y, a continuación, haga clic en **resultados a texto**.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-115">On the **Query** menu, point to **Results To** and then click **Results to Text**.</span></span>  
  
4.  <span data-ttu-id="d5d8d-116">Copie la siguiente secuencia de comandos SQL en el panel de consulta.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-116">Copy the following SQL script into the query pane.</span></span> <span data-ttu-id="d5d8d-117">Reemplace \<nombre de actividad > por el nombre de la actividad y `<view type>` con cualquiera **instancias** ver para la instancia o **relaciones** para la vista de relaciones.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-117">Replace \<activity name> with your activity name, and replace `<view type>` with either **Instances** for instance view or **Relationships** for relationship view.</span></span>  
  
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
  
5.  <span data-ttu-id="d5d8d-118">Ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="d5d8d-118">Execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d8d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5d8d-119">See Also</span></span>  
 <span data-ttu-id="d5d8d-120">[Paquetes DTS de BAM](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="d5d8d-120">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 [<span data-ttu-id="d5d8d-121">Cómo realizar una copia del análisis de seguimiento y análisis de BAM bases de datos de servidor</span><span class="sxs-lookup"><span data-stu-id="d5d8d-121">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)