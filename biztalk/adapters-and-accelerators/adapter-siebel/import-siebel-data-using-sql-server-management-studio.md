---
title: Importar datos de Siebel mediante SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Management Studio, importing data by using
- how to, import data by using SQL Server Management Studio
ms.assetid: 67da7f7b-37ea-4a31-89ef-a9f6974ff976
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdcc6140bb50ebca299cd58f78063be8f108dea4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013181"
---
# <a name="import-siebel-data-using-sql-server-management-studio"></a><span data-ttu-id="7397b-102">Importar datos de Siebel mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7397b-102">Import Siebel Data Using SQL Server Management Studio</span></span>
<span data-ttu-id="7397b-103">Esta sección proporciona información sobre cómo usar SQL Server Management Studio para importar datos desde un sistema Siebel en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7397b-103">This section provides information about how to use SQL Server Management Studio to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="7397b-104">También proporciona instrucciones sobre cómo crear y ejecutar un paquete SSIS para importar estos datos.</span><span class="sxs-lookup"><span data-stu-id="7397b-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7397b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7397b-105">Prerequisites</span></span>  
 <span data-ttu-id="7397b-106">Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="7397b-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
- <span data-ttu-id="7397b-107">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7397b-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
- <span data-ttu-id="7397b-108">SQL Server Business Intelligence Development Studio está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7397b-108">SQL Server Business Intelligence Development Studio is installed on the computer.</span></span>  
  
## <a name="importing-data-by-using-sql-server-management-studio"></a><span data-ttu-id="7397b-109">Importar datos mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7397b-109">Importing Data by Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7397b-110">Realice los pasos siguientes para importar datos del sistema de Siebel con [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="7397b-110">Perform the following steps to import data from Siebel system using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SQL Server Management Studio.</span></span>  
  
#### <a name="to-import-data-by-using-sql-server-management-studio"></a><span data-ttu-id="7397b-111">Para importar datos mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7397b-111">To import data by using SQL Server Management Studio</span></span>  
  
1. <span data-ttu-id="7397b-112">Inicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="7397b-112">Start the SQL Server Management Studio.</span></span>  
  
2. <span data-ttu-id="7397b-113">En el **conectar al servidor** diálogo cuadro, especifique los valores para conectarse a una base de datos de SQL Server y, a continuación, haga clic en **Connect**.</span><span class="sxs-lookup"><span data-stu-id="7397b-113">In the **Connect to Server** dialog box, specify the values to connect to a SQL Server database, and then click **Connect**.</span></span> <span data-ttu-id="7397b-114">Se abre Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="7397b-114">Microsoft SQL Server Management Studio opens.</span></span>  
  
3. <span data-ttu-id="7397b-115">En el Explorador de objetos, expanda el nombre de SQL Server, expanda **bases de datos**y haga clic en la base de datos en la que se van a exportar las tablas en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="7397b-115">In Object Explorer, expand the SQL Server name, expand **Databases**, and right-click the database into which you will be exporting the tables from the Siebel system.</span></span> <span data-ttu-id="7397b-116">En el menú contextual, seleccione **tareas**y, a continuación, haga clic en **importar datos**.</span><span class="sxs-lookup"><span data-stu-id="7397b-116">From the context menu, point to **Tasks**, and then click **Import Data**.</span></span> <span data-ttu-id="7397b-117">Esto inicia la importación de SQL Server y el Asistente para exportación.</span><span class="sxs-lookup"><span data-stu-id="7397b-117">This starts the SQL Server Import and Export Wizard.</span></span>  
  
4. <span data-ttu-id="7397b-118">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7397b-118">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5. <span data-ttu-id="7397b-119">En el **elegir un origen de datos** cuadro de diálogo desde el **origen de datos** lista desplegable, seleccione **.NET Framework Data Provider para aplicaciones Siebel eBusiness**.</span><span class="sxs-lookup"><span data-stu-id="7397b-119">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list, select **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="7397b-120">Especifique los valores de las propiedades de conexión diferentes para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="7397b-120">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="7397b-121">Para obtener más información acerca de las propiedades de cadena de conexión, consulte [las propiedades de proveedor de datos de la cadena de conexión de Siebel](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="7397b-121">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
    <span data-ttu-id="7397b-122">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7397b-122">Click **Next**.</span></span>  
  
6. <span data-ttu-id="7397b-123">En el **elegir un destino** cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="7397b-123">In the **Choose a Destination** dialog box:</span></span>  
  
   1.  <span data-ttu-id="7397b-124">Desde el **destino** lista desplegable, seleccione **SQL Native Client**.</span><span class="sxs-lookup"><span data-stu-id="7397b-124">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
   2.  <span data-ttu-id="7397b-125">Desde el **nombre del servidor** lista desplegable, seleccione un nombre de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7397b-125">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
   3.  <span data-ttu-id="7397b-126">Seleccione un modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="7397b-126">Select an authentication mode.</span></span>  
  
   4.  <span data-ttu-id="7397b-127">Desde el **base de datos** lista desplegable, seleccione la base de datos a la que van a importar la tabla de Siebel.</span><span class="sxs-lookup"><span data-stu-id="7397b-127">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
   5.  <span data-ttu-id="7397b-128">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7397b-128">Click **Next**.</span></span>  
  
7. <span data-ttu-id="7397b-129">En el **especificar copia de tabla o consulta** diálogo cuadro, elija el **escribir una consulta para especificar los datos que se van a transferir** opción.</span><span class="sxs-lookup"><span data-stu-id="7397b-129">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
8. <span data-ttu-id="7397b-130">En el **proporcionar una consulta de origen** diálogo cuadro, especifique una consulta SELECT para filtrar los datos que se importarán en el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7397b-130">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="7397b-131">Para obtener más información sobre la gramática de una instrucción SELECT de consulta para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], consulte [sintaxis para una instrucción SELECT en Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="7397b-131">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
    <span data-ttu-id="7397b-132">Haga clic en el **analizar** botón para validar la consulta, haga clic en **Aceptar** en el cuadro de diálogo emergente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7397b-132">Click the **Parse** button to validate the query, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="7397b-133">En el **seleccionar tablas de origen y las vistas** diálogo cuadro, active la casilla de verificación en las tablas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="7397b-133">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="7397b-134">El origen es la consulta especificada para recuperar datos de Siebel.</span><span class="sxs-lookup"><span data-stu-id="7397b-134">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="7397b-135">El destino es la tabla que se creará en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7397b-135">The destination is the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="7397b-136">El asistente crea una asignación predeterminada entre el origen y destino de los campos de tabla.</span><span class="sxs-lookup"><span data-stu-id="7397b-136">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="7397b-137">Sin embargo, puede cambiar las asignaciones de acuerdo con sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="7397b-137">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="7397b-138">Para cambiar las asignaciones de campos, haga clic en **editar asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="7397b-138">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="7397b-139">![Asignaciones de columnas entre tablas Siebel y SQL](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="7397b-139">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
11. <span data-ttu-id="7397b-140">En el **asignaciones de columnas** cuadro de diálogo, puede:</span><span class="sxs-lookup"><span data-stu-id="7397b-140">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="7397b-141">Cambiar los nombres de columnas en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="7397b-141">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="7397b-142">Omitir algunas columnas en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="7397b-142">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="7397b-143">Cambiar el tipo de datos para los campos de tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="7397b-143">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="7397b-144">Cambiar otros atributos de campo como que acepta valores NULL, tamaño, precisión y escala.</span><span class="sxs-lookup"><span data-stu-id="7397b-144">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
         <span data-ttu-id="7397b-145">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7397b-145">When you are finished, click **OK**.</span></span>  
  
12. <span data-ttu-id="7397b-146">En el **seleccionar tablas de origen y las vistas** cuadro de diálogo, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7397b-146">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="7397b-147">En el **guardar y ejecutar paquete** cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="7397b-147">In the **Save and Execute Package** dialog box:</span></span>  
  
    - <span data-ttu-id="7397b-148">Seleccione el **ejecutar inmediatamente** casilla de verificación para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="7397b-148">Select the **Execute immediately** check box to execute the query.</span></span>  
  
    - <span data-ttu-id="7397b-149">Seleccione el **guardar el paquete SSIS** casilla de verificación para guardar la consulta como un paquete y ejecutarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="7397b-149">Select the **Save SSIS Package** check box to save the query as a package and execute it later.</span></span> <span data-ttu-id="7397b-150">Si decide guardar el paquete, también debe especificar si desea guardar el paquete en el servidor SQL Server o el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="7397b-150">If you chose to save the package, you must also specify whether you want to save the package in the SQL Server or the file system.</span></span>  
  
    - <span data-ttu-id="7397b-151">Desde el **nivel de protección de paquetes** lista desplegable, seleccione una protección de nivel para el paquete y especifique las credenciales cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7397b-151">From the **Package protection level** drop-down list, select a protection level for the package and specify credentials where required.</span></span>  
  
    - <span data-ttu-id="7397b-152">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7397b-152">Click **Next**.</span></span>  
  
      <span data-ttu-id="7397b-153">Si decide guardar el paquete, continúe con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="7397b-153">If you chose to save the package, proceed to the next step.</span></span> <span data-ttu-id="7397b-154">En caso contrario, vaya al paso 15.</span><span class="sxs-lookup"><span data-stu-id="7397b-154">Otherwise, skip to step 15.</span></span>  
  
14. <span data-ttu-id="7397b-155">En el **guardar el paquete SSIS** diálogo cuadro, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7397b-155">In the **Save SSIS Package** dialog box, specify the following:</span></span>  
  
    -   <span data-ttu-id="7397b-156">El nombre del paquete</span><span class="sxs-lookup"><span data-stu-id="7397b-156">The name for the package</span></span>  
  
    -   <span data-ttu-id="7397b-157">La descripción del paquete</span><span class="sxs-lookup"><span data-stu-id="7397b-157">The description for the package</span></span>  
  
    -   <span data-ttu-id="7397b-158">Si decide guardar el paquete en un servidor SQL Server, seleccione un servidor SQL Server desde el **nombre del servidor** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7397b-158">If you chose to save the package to a SQL Server, select a SQL Server from the **Server name** drop-down list.</span></span>  
  
    -   <span data-ttu-id="7397b-159">Si decide guardar el paquete en el sistema de archivos, especifique el nombre y la ubicación del archivo en el **nombre de archivo** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="7397b-159">If you chose to save the package to the file system, specify the name and location of the file in the **File name** text box.</span></span>  
  
         <span data-ttu-id="7397b-160">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7397b-160">When you are finished, click **Next**.</span></span>  
  
15. <span data-ttu-id="7397b-161">En el **Complete el asistente** diálogo cuadro, revise el resumen de las acciones que realizar el asistente y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7397b-161">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
16. <span data-ttu-id="7397b-162">En el **realizar operaciones de** cuadro de diálogo, el asistente inicia la ejecución de tareas para importar la información de Siebel en una tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7397b-162">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="7397b-163">El estado de cada tarea se muestra en el asistente.</span><span class="sxs-lookup"><span data-stu-id="7397b-163">The status for each task is displayed in the wizard.</span></span>  
  
17. <span data-ttu-id="7397b-164">Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7397b-164">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="7397b-165">Si se produce un error en una tarea, vea el correspondiente mensaje de error, corrija el problema y vuelva a ejecutar al asistente.</span><span class="sxs-lookup"><span data-stu-id="7397b-165">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="7397b-166">Ejecutar el paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="7397b-166">Running the SSIS Package</span></span>  
 <span data-ttu-id="7397b-167">Si decide guardar el paquete SSIS, puede ejecutarla para recuperar la información más reciente en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="7397b-167">If you chose to save the SSIS package, you can run it to retrieve the most recent information from the Siebel system.</span></span> <span data-ttu-id="7397b-168">Esta sección proporciona información sobre cómo ejecutar el paquete si se decide guardarlo en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="7397b-168">This section provides information about how to run the package if you chose to save it to the file system.</span></span>  
  
#### <a name="to-run-the-package-from-windows-explorer"></a><span data-ttu-id="7397b-169">Para ejecutar el paquete desde el Explorador de Windows</span><span class="sxs-lookup"><span data-stu-id="7397b-169">To run the package from Windows Explorer</span></span>  
  
1. <span data-ttu-id="7397b-170">Desde **Windows Explorer**, desplácese hasta la ubicación donde guardó el paquete y haga doble clic en el paquete.</span><span class="sxs-lookup"><span data-stu-id="7397b-170">From **Windows Explorer**, navigate to the location where you saved the package, and double-click the package.</span></span>  
  
2. <span data-ttu-id="7397b-171">En el cuadro de diálogo **Utilidad de ejecución de paquetes** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7397b-171">In the **Execute Package Utility** dialog box, click **Execute**.</span></span> <span data-ttu-id="7397b-172">El **progreso de ejecución del paquete** cuadro de diálogo muestra el progreso de las distintas tareas.</span><span class="sxs-lookup"><span data-stu-id="7397b-172">The **Package Execution Progress** dialog box displays the progress of the different tasks.</span></span>  
  
3. <span data-ttu-id="7397b-173">Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7397b-173">After all the tasks are successfully executed, click **Close**.</span></span>  
  
4. <span data-ttu-id="7397b-174">En el cuadro de diálogo **Utilidad de ejecución de paquetes** , haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7397b-174">In the **Execute Package Utility** dialog box, click **Close**.</span></span>  
  
   <span data-ttu-id="7397b-175">Para obtener más información sobre la ejecución de paquetes, vea "Paquetes en ejecución" en [ http://go.microsoft.com/fwlink/?LinkId=94972 ](http://go.microsoft.com/fwlink/?LinkId=94972).</span><span class="sxs-lookup"><span data-stu-id="7397b-175">For more information about running packages, see "Running Packages" at [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="7397b-176">Para cualquier otra información relacionada con los paquetes de SSIS, vea "paquete procedimientos temas (SSIS)" en [ http://go.microsoft.com/fwlink/?LinkId=94973 ](http://go.microsoft.com/fwlink/?LinkId=94973).</span><span class="sxs-lookup"><span data-stu-id="7397b-176">For any other information related to SSIS packages, see "Package How-to Topics (SSIS)" at [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="7397b-177">Comprobar los resultados</span><span class="sxs-lookup"><span data-stu-id="7397b-177">Verifying the Results</span></span>  
 <span data-ttu-id="7397b-178">Después de ejecutar el paquete, debe comprobar los resultados, vaya a la base de datos de SQL Server a la que se importan los datos de Siebel.</span><span class="sxs-lookup"><span data-stu-id="7397b-178">After executing the package, you must verify the results by going to the SQL Server database to which the Siebel data is imported.</span></span> <span data-ttu-id="7397b-179">Ejecutar el paquete debería haber creado una tabla en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="7397b-179">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="7397b-180">Esta tabla debe rellenarse con los valores de la tabla de Siebel.</span><span class="sxs-lookup"><span data-stu-id="7397b-180">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7397b-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="7397b-181">See Also</span></span>  
 [<span data-ttu-id="7397b-182">Usar el proveedor de datos para Siebel con SSIS</span><span class="sxs-lookup"><span data-stu-id="7397b-182">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)