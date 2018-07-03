---
title: Importar datos de Siebel con Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d631c461c876ef4066e497d7d72d2e5fe13d022
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978037"
---
# <a name="import-siebel-data-using-visual-studio"></a><span data-ttu-id="601ab-102">Importar datos de Siebel con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="601ab-102">Import Siebel Data Using Visual Studio</span></span>
<span data-ttu-id="601ab-103">Esta sección proporciona información sobre cómo usar Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para importar datos desde un sistema Siebel en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="601ab-103">This section provides information about how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="601ab-104">También proporciona instrucciones sobre cómo crear y ejecutar un paquete SSIS para importar estos datos.</span><span class="sxs-lookup"><span data-stu-id="601ab-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="601ab-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="601ab-105">Prerequisites</span></span>  
 <span data-ttu-id="601ab-106">Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="601ab-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
- <span data-ttu-id="601ab-107">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="601ab-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
- <span data-ttu-id="601ab-108">Microsoft Visual Studio está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="601ab-108">Microsoft Visual Studio is installed on the computer.</span></span>  
  
## <a name="import-in-visual-studio"></a><span data-ttu-id="601ab-109">Importación en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="601ab-109">Import in Visual Studio</span></span>  
 
1. <span data-ttu-id="601ab-110">Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y crear un proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="601ab-110">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2. <span data-ttu-id="601ab-111">Desde el **proyecto** menú, seleccione **SSIS Import and Export Wizard**.</span><span class="sxs-lookup"><span data-stu-id="601ab-111">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="601ab-112">Esto inicia la importación de SQL Server y el Asistente para exportación.</span><span class="sxs-lookup"><span data-stu-id="601ab-112">This starts the SQL Server Import and Export Wizard.</span></span>  
  
3. <span data-ttu-id="601ab-113">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="601ab-113">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="601ab-114">En el **elegir un origen de datos** cuadro de diálogo desde el **origen de datos** lista desplegable **.NET Framework Data Provider para aplicaciones Siebel eBusiness**.</span><span class="sxs-lookup"><span data-stu-id="601ab-114">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="601ab-115">Especifique los valores de las propiedades de conexión diferentes para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="601ab-115">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="601ab-116">Para obtener más información acerca de las propiedades de cadena de conexión, consulte [las propiedades de proveedor de datos de la cadena de conexión de Siebel](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="601ab-116">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
    <span data-ttu-id="601ab-117">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="601ab-117">Click **Next**.</span></span>  
  
5. <span data-ttu-id="601ab-118">En el **elegir un destino** cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="601ab-118">In the **Choose a Destination** dialog box:</span></span>  
  
   1.  <span data-ttu-id="601ab-119">Desde el **destino** lista desplegable, seleccione **SQL Native Client**.</span><span class="sxs-lookup"><span data-stu-id="601ab-119">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
   2.  <span data-ttu-id="601ab-120">Desde el **nombre del servidor** lista desplegable, seleccione un nombre de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="601ab-120">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
   3.  <span data-ttu-id="601ab-121">Seleccione un modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="601ab-121">Select an authentication mode.</span></span>  
  
   4.  <span data-ttu-id="601ab-122">Desde el **base de datos** lista desplegable, seleccione la base de datos a la que van a importar la tabla de Siebel.</span><span class="sxs-lookup"><span data-stu-id="601ab-122">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
   5.  <span data-ttu-id="601ab-123">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="601ab-123">Click **Next**.</span></span>  
  
6. <span data-ttu-id="601ab-124">En el **especificar copia de tabla o consulta** diálogo cuadro, elija el **escribir una consulta para especificar los datos que se van a transferir** opción.</span><span class="sxs-lookup"><span data-stu-id="601ab-124">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
7. <span data-ttu-id="601ab-125">En el **proporcionar una consulta de origen** diálogo cuadro, especifique una consulta SELECT para filtrar los datos que se importarán en el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="601ab-125">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="601ab-126">Para obtener más información sobre la gramática de una instrucción SELECT de consulta para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], consulte [sintaxis para una instrucción SELECT en Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="601ab-126">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
8. <span data-ttu-id="601ab-127">Para validar la consulta, haga clic en el **analizar** botón, haga clic en **Aceptar** en el cuadro de diálogo emergente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="601ab-127">To validate the query, click the **Parse** button, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="601ab-128">En el **seleccionar tablas de origen y las vistas** diálogo cuadro, active la casilla de verificación en las tablas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="601ab-128">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="601ab-129">El origen es la consulta especificada para recuperar datos de Siebel.</span><span class="sxs-lookup"><span data-stu-id="601ab-129">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="601ab-130">El destino será la tabla que se creará en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="601ab-130">The destination will be the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="601ab-131">El asistente crea una asignación predeterminada entre el origen y destino de los campos de tabla.</span><span class="sxs-lookup"><span data-stu-id="601ab-131">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="601ab-132">Sin embargo, puede cambiar las asignaciones de acuerdo con sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="601ab-132">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="601ab-133">Para cambiar las asignaciones de campos, haga clic en **editar asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="601ab-133">To change the field mappings, click **Edit Mappings**.</span></span>  
  
11. <span data-ttu-id="601ab-134">En el **asignaciones de columnas** cuadro de diálogo, puede:</span><span class="sxs-lookup"><span data-stu-id="601ab-134">In the **Column Mappings** dialog box, you can:</span></span>  
  
    - <span data-ttu-id="601ab-135">Cambiar los nombres de columnas en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="601ab-135">Change the names of columns in the destination table.</span></span>  
  
    - <span data-ttu-id="601ab-136">Omitir algunas columnas en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="601ab-136">Ignore certain columns in the destination table.</span></span>  
  
    - <span data-ttu-id="601ab-137">Cambiar el tipo de datos para los campos de tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="601ab-137">Change the data type for fields in destination table.</span></span>  
  
    - <span data-ttu-id="601ab-138">Cambiar otros atributos de campo como que acepta valores NULL, tamaño, precisión y escala.</span><span class="sxs-lookup"><span data-stu-id="601ab-138">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    - <span data-ttu-id="601ab-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="601ab-139">Click **OK**.</span></span>  
  
      <span data-ttu-id="601ab-140">![Asignaciones de columnas entre tablas Siebel y SQL](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="601ab-140">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
12. <span data-ttu-id="601ab-141">En el **seleccionar tablas de origen y las vistas** cuadro de diálogo, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="601ab-141">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="601ab-142">En el **Complete el asistente** diálogo cuadro, revise el resumen de las acciones que realizar el asistente y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="601ab-142">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="601ab-143">En el **realizar operaciones de** cuadro de diálogo, el asistente inicia la ejecución de tareas para importar la información de Siebel en una tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="601ab-143">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="601ab-144">El estado de cada tarea se muestra en el asistente.</span><span class="sxs-lookup"><span data-stu-id="601ab-144">The status for each task is displayed in the wizard.</span></span>  
  
15. <span data-ttu-id="601ab-145">Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="601ab-145">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="601ab-146">Si se produce un error en una tarea, vea el correspondiente mensaje de error, corrija el problema y vuelva a ejecutar al asistente.</span><span class="sxs-lookup"><span data-stu-id="601ab-146">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
16. <span data-ttu-id="601ab-147">El asistente agrega un paquete SSIS para el proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="601ab-147">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="601ab-148">Guarde el proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="601ab-148">Save the Integration Service project.</span></span>  
  
## <a name="run-the-ssis-package"></a><span data-ttu-id="601ab-149">Ejecutar el paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="601ab-149">Run the SSIS Package</span></span>  
 <span data-ttu-id="601ab-150">Una vez creado el paquete dentro de un proyecto de servicio de integración, puede ejecutarla para importar datos desde un sistema Siebel en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="601ab-150">Once the package is created within an Integration Service project, you can execute it to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="601ab-151">Realice los pasos siguientes para importar datos de Siebel mediante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="601ab-151">Perform the following steps to import Siebel data by executing the package.</span></span>  
  
1.  <span data-ttu-id="601ab-152">Navegue hasta el paquete SSIS en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="601ab-152">Navigate to the SSIS package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="601ab-153">Haga clic en el nombre del paquete y, a continuación, seleccione **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="601ab-153">Right-click the package name, and then select **Execute Package**.</span></span>  
  
<span data-ttu-id="601ab-154">[Ejecutar paquetes de Integration Services (SSIS)](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages) proporciona más información.</span><span class="sxs-lookup"><span data-stu-id="601ab-154">[Run Integration Services (SSIS) Packages](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages) provides more info.</span></span> 
  
## <a name="verify-the-results"></a><span data-ttu-id="601ab-155">Comprobar los resultados</span><span class="sxs-lookup"><span data-stu-id="601ab-155">Verify the Results</span></span>  
 <span data-ttu-id="601ab-156">Después de ejecutar el paquete, debe comprobar los resultados, iniciar sesión en el servidor SQL Server y vaya a la base de datos a la que se importan los datos de Siebel.</span><span class="sxs-lookup"><span data-stu-id="601ab-156">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the Siebel data is imported.</span></span> <span data-ttu-id="601ab-157">Ejecutar el paquete debería haber creado una tabla en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="601ab-157">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="601ab-158">Esta tabla debe rellenarse con los valores de la tabla de Siebel.</span><span class="sxs-lookup"><span data-stu-id="601ab-158">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="601ab-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="601ab-159">See Also</span></span>  
 [<span data-ttu-id="601ab-160">Usar el proveedor de datos para Siebel con SSIS</span><span class="sxs-lookup"><span data-stu-id="601ab-160">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)