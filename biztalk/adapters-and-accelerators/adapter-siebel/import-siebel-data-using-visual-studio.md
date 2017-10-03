---
title: Importar datos de Siebel con Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSIS
- Data Provider for Siebel, importing Siebel data by using Visual Studio
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0671459b39462422768e42e18bf16336a469f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="import-siebel-data-using-visual-studio"></a><span data-ttu-id="024a4-102">Importar datos de Siebel con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="024a4-102">Import Siebel Data Using Visual Studio</span></span>
<span data-ttu-id="024a4-103">Esta sección proporciona información sobre cómo usar Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para importar datos desde un sistema Siebel en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="024a4-103">This section provides information about how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="024a4-104">También proporciona instrucciones sobre cómo crear y ejecutar un paquete SSIS para importar estos datos.</span><span class="sxs-lookup"><span data-stu-id="024a4-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="024a4-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="024a4-105">Prerequisites</span></span>  
 <span data-ttu-id="024a4-106">Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="024a4-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   <span data-ttu-id="024a4-107">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="024a4-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
-   <span data-ttu-id="024a4-108">Microsoft [!INCLUDE[vs2010](../../includes/vs2010-md.md)] está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="024a4-108">Microsoft [!INCLUDE[vs2010](../../includes/vs2010-md.md)] is installed on the computer.</span></span>  
  
## <a name="importing-data-by-using-visual-studio"></a><span data-ttu-id="024a4-109">Importar datos con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="024a4-109">Importing Data by Using Visual Studio</span></span>  
 <span data-ttu-id="024a4-110">Siga estos pasos para importar datos mediante [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="024a4-110">Perform the following steps to import data using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
#### <a name="to-import-data-by-using-visual-studio"></a><span data-ttu-id="024a4-111">Para importar datos mediante el uso de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="024a4-111">To import data by using Visual Studio</span></span>  
  
1.  <span data-ttu-id="024a4-112">Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y cree un proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="024a4-112">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2.  <span data-ttu-id="024a4-113">Desde el **proyecto** menú, seleccione **SSIS Import and Export Wizard**.</span><span class="sxs-lookup"><span data-stu-id="024a4-113">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="024a4-114">Esto inicia la importación de SQL Server y el Asistente para exportación.</span><span class="sxs-lookup"><span data-stu-id="024a4-114">This starts the SQL Server Import and Export Wizard.</span></span>  
  
3.  <span data-ttu-id="024a4-115">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="024a4-115">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="024a4-116">En el **elegir un origen de datos** cuadro de diálogo, desde el **origen de datos** lista desplegable **proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness**.</span><span class="sxs-lookup"><span data-stu-id="024a4-116">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="024a4-117">Especificar valores para las propiedades de conexión diferentes para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="024a4-117">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="024a4-118">Para obtener más información acerca de las propiedades de cadena de conexión, vea [propiedades de proveedor de datos de la cadena de conexión de Siebel](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="024a4-118">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
     <span data-ttu-id="024a4-119">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="024a4-119">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="024a4-120">En el **elegir un destino** cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="024a4-120">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="024a4-121">Desde el **destino** lista desplegable, seleccione **SQL Native Client**.</span><span class="sxs-lookup"><span data-stu-id="024a4-121">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="024a4-122">Desde el **nombre del servidor** lista desplegable, seleccione un nombre de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="024a4-122">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
    3.  <span data-ttu-id="024a4-123">Seleccione un modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="024a4-123">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="024a4-124">Desde el **base de datos** lista desplegable, seleccione la base de datos a la que van a importar en la tabla de Siebel.</span><span class="sxs-lookup"><span data-stu-id="024a4-124">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
    5.  <span data-ttu-id="024a4-125">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="024a4-125">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="024a4-126">En el **especificar copia de tabla o consulta** diálogo cuadro, elija la **escribir una consulta para especificar los datos que se va a transferir** opción.</span><span class="sxs-lookup"><span data-stu-id="024a4-126">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
7.  <span data-ttu-id="024a4-127">En el **proporcionar una consulta de origen** cuadro de diálogo, especifique una consulta SELECT para filtrar los datos que se importarán en el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="024a4-127">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="024a4-128">Para obtener más información sobre la gramática de una instrucción SELECT de consulta para la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], consulte [sintaxis de una instrucción SELECT de Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="024a4-128">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
8.  <span data-ttu-id="024a4-129">Para validar la consulta, haga clic en el **analizar** botón, haga clic en **Aceptar** en el cuadro de diálogo emergente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="024a4-129">To validate the query, click the **Parse** button, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="024a4-130">En el **seleccionar tablas de origen y vistas** cuadro de diálogo, seleccione la casilla de verificación en las tablas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="024a4-130">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="024a4-131">El origen es la consulta especificada para recuperar datos de Siebel.</span><span class="sxs-lookup"><span data-stu-id="024a4-131">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="024a4-132">El destino será la tabla que se creará en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="024a4-132">The destination will be the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="024a4-133">El asistente crea una asignación predeterminada entre el origen y el destino de campos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="024a4-133">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="024a4-134">Sin embargo, puede cambiar las asignaciones de acuerdo con sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="024a4-134">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="024a4-135">Para cambiar las asignaciones de campos, haga clic en **editar asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="024a4-135">To change the field mappings, click **Edit Mappings**.</span></span>  
  
11. <span data-ttu-id="024a4-136">En el **asignaciones de columnas** cuadro de diálogo, puede:</span><span class="sxs-lookup"><span data-stu-id="024a4-136">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="024a4-137">Cambiar los nombres de columnas en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="024a4-137">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="024a4-138">Omitir ciertas columnas de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="024a4-138">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="024a4-139">Cambiar el tipo de datos para los campos de tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="024a4-139">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="024a4-140">Cambiar otros atributos de campo como que acepta valores NULL, el tamaño, la precisión y la escala.</span><span class="sxs-lookup"><span data-stu-id="024a4-140">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="024a4-141">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="024a4-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="024a4-142">![Asignaciones de columnas entre la tabla de Siebel y SQL](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="024a4-142">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
12. <span data-ttu-id="024a4-143">En el **seleccionar tablas de origen y vistas** cuadro de diálogo, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="024a4-143">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="024a4-144">En el **Complete el asistente** diálogo cuadro, revise el resumen de las acciones que el asistente va a realizar y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="024a4-144">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="024a4-145">En el **realizar operaciones de** cuadro de diálogo, el asistente inicia la ejecución de tareas para importar la información de Siebel en una tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="024a4-145">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="024a4-146">El estado de cada tarea se muestra en el asistente.</span><span class="sxs-lookup"><span data-stu-id="024a4-146">The status for each task is displayed in the wizard.</span></span>  
  
15. <span data-ttu-id="024a4-147">Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="024a4-147">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="024a4-148">Si se produce un error en una tarea, vea el correspondiente mensaje de error, corrija el problema y vuelva a ejecutar al asistente.</span><span class="sxs-lookup"><span data-stu-id="024a4-148">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
16. <span data-ttu-id="024a4-149">El asistente agrega un paquete SSIS para el proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="024a4-149">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="024a4-150">Guarde el proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="024a4-150">Save the Integration Service project.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="024a4-151">Ejecutar el paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="024a4-151">Running the SSIS Package</span></span>  
 <span data-ttu-id="024a4-152">Una vez que el paquete se crea dentro de un proyecto de servicio de integración, puede ejecutarla para importar datos desde un sistema Siebel en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="024a4-152">Once the package is created within an Integration Service project, you can execute it to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="024a4-153">Realice los pasos siguientes para importar datos de Siebel mediante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="024a4-153">Perform the following steps to import Siebel data by executing the package.</span></span>  
  
#### <a name="to-run-the-package-from-visual-studio"></a><span data-ttu-id="024a4-154">Para ejecutar el paquete de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="024a4-154">To run the package from Visual Studio</span></span>  
  
1.  <span data-ttu-id="024a4-155">Navegue hasta el paquete SSIS en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="024a4-155">Navigate to the SSIS package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="024a4-156">Haga clic en el nombre del paquete y, a continuación, seleccione **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="024a4-156">Right-click the package name, and then select **Execute Package**.</span></span>  
  
 <span data-ttu-id="024a4-157">Para obtener más información sobre la ejecución de paquetes, vea "Paquetes en ejecución" en [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span><span class="sxs-lookup"><span data-stu-id="024a4-157">For more information about running packages, see "Running Packages" at [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="024a4-158">Para cualquier otra información relacionada con paquetes SSIS, consulte "paquete" Cómo... "temas (SSIS)" en [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span><span class="sxs-lookup"><span data-stu-id="024a4-158">For any other information related to SSIS packages, see "Package How-to Topics (SSIS)" at [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="024a4-159">Comprobar los resultados</span><span class="sxs-lookup"><span data-stu-id="024a4-159">Verifying the Results</span></span>  
 <span data-ttu-id="024a4-160">Después de ejecutar el paquete, debe comprobar los resultados de inicio de sesión en el servidor SQL Server y yendo a la base de datos a la que se importan los datos de Siebel.</span><span class="sxs-lookup"><span data-stu-id="024a4-160">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the Siebel data is imported.</span></span> <span data-ttu-id="024a4-161">Ejecutar el paquete debe haber creado una tabla en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="024a4-161">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="024a4-162">Esta tabla se debe rellenar con los valores de la tabla de Siebel.</span><span class="sxs-lookup"><span data-stu-id="024a4-162">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="024a4-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="024a4-163">See Also</span></span>  
 [<span data-ttu-id="024a4-164">Usar el proveedor de datos de Siebel con SSIS</span><span class="sxs-lookup"><span data-stu-id="024a4-164">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)