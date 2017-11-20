---
title: Importar datos SAP mediante Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- importing SAP data, using Visual Studio
- Visual Studio, importing SAP data
ms.assetid: 70cce089-232d-4ab9-81bd-6b0d6f0097d7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1295f763815872bacedf2262f7c022d6813bd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="import-sap-data-using-visual-studio"></a><span data-ttu-id="0cf9e-102">Importar datos SAP mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0cf9e-102">Import SAP Data Using Visual Studio</span></span>
<span data-ttu-id="0cf9e-103">Esta sección proporciona información sobre cómo usar Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para importar datos desde un sistema SAP en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-103">This section provides information on how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="0cf9e-104">Esta sección proporciona instrucciones sobre cómo crear un paquete SSIS que se puede ejecutar para importar datos.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-104">This section provides instruction on how to create an SSIS package that you can execute to import data.</span></span> <span data-ttu-id="0cf9e-105">En esta sección también proporciona información sobre cómo ejecutar el paquete SSIS.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-105">This section also provides information on how to execute the SSIS package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0cf9e-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0cf9e-106">Prerequisites</span></span>  
 <span data-ttu-id="0cf9e-107">Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="0cf9e-107">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="0cf9e-108">está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-108"> is installed on the computer.</span></span>  
  
-   [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="0cf9e-109">está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-109"> is installed on the computer.</span></span>  
  
### <a name="to-import-data-using-visual-studio"></a><span data-ttu-id="0cf9e-110">Para importar datos con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0cf9e-110">To import data using Visual Studio</span></span>  
  
1.  <span data-ttu-id="0cf9e-111">Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y cree un proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-111">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2.  <span data-ttu-id="0cf9e-112">Desde el **proyecto** menú, seleccione **SSIS Import and Export Wizard**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-112">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="0cf9e-113">Esto inicia el **SQL Server Import and Export Wizard**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-113">This starts the **SQL Server Import and Export Wizard**.</span></span>  
  
3.  <span data-ttu-id="0cf9e-114">Lea la información de la pantalla de bienvenida y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-114">Read the information on the welcome screen and click **Next**.</span></span>  
  
4.  <span data-ttu-id="0cf9e-115">En el **elegir un origen de datos** cuadro de diálogo, desde el **origen de datos** lista desplegable **.NET Framework Data Provider para mySAP Business Suite**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-115">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for mySAP Business Suite**.</span></span> <span data-ttu-id="0cf9e-116">El cuadro de diálogo muestra los parámetros de conexión diferente para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-116">The dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="0cf9e-117">Una cadena de conexión típica para conectarse a un sistema SAP mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere:</span><span class="sxs-lookup"><span data-stu-id="0cf9e-117">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
    -   <span data-ttu-id="0cf9e-118">Los parámetros de conexión para un tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-118">The connection parameters for a connection type.</span></span> <span data-ttu-id="0cf9e-119">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] es compatible con los tipos de conexión A, B y D. Para conectarse a un sistema SAP debe proporcionar parámetros de conexión para cualquier *una* de estos tipos de conexión.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-119">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="0cf9e-120">Por ejemplo, para el tipo de conexión A, debe proporcionar el nombre del host de servidor de aplicación y el número del sistema.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-120">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
    -   <span data-ttu-id="0cf9e-121">La información de inicio de sesión para conectarse a un sistema SAP como nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-121">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="0cf9e-122">Para obtener más información acerca de la cadena de conexión para conectarse a un sistema SAP mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [más información sobre el proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="0cf9e-122">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="0cf9e-123">En el **elegir un origen de datos** diálogo cuadro, especifique:</span><span class="sxs-lookup"><span data-stu-id="0cf9e-123">In the **Choose a Data Source** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="0cf9e-124">Los parámetros de conexión para cualquier tipo de una conexión.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-124">The connection parameters for any one connection type.</span></span>  
  
    -   <span data-ttu-id="0cf9e-125">La información de inicio de sesión para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-125">The login information to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="0cf9e-126">Si desea habilitar la depuración de GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-126">Whether you want to enable SAP GUI debugging.</span></span>  
  
    -   <span data-ttu-id="0cf9e-127">Si desea utilizar el seguimiento de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-127">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="0cf9e-128">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-128">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="0cf9e-129">En el **elegir un destino** cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="0cf9e-129">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="0cf9e-130">Desde el **destino** lista desplegable, seleccione **SQL Native Client**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-130">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="0cf9e-131">Desde el **nombre del servidor** lista desplegable, seleccione un nombre de SQL server.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-131">From the **Server name** drop-down list, select a SQL server name.</span></span>  
  
    3.  <span data-ttu-id="0cf9e-132">Seleccione un modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-132">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="0cf9e-133">Desde el **base de datos** lista desplegable, seleccione la base de datos a la que van a importar la tabla SAP.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-133">From the **Database** drop-down list, select the database to which you want to import the SAP table.</span></span>  
  
    5.  <span data-ttu-id="0cf9e-134">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-134">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="0cf9e-135">En el **especificar copia de tabla o consulta** diálogo cuadro, elija la **escribir una consulta para especificar los datos que se va a transferir** opción y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-135">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option and click **Next**.</span></span>  
  
7.  <span data-ttu-id="0cf9e-136">En el **proporcionar una consulta de origen** cuadro de diálogo, especifique una consulta SELECT para filtrar los datos que se importarán en el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-136">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="0cf9e-137">Para obtener más información sobre la gramática de una instrucción SELECT de consulta para la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="0cf9e-137">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
     <span data-ttu-id="0cf9e-138">Haga clic en el **analizar** botón para validar la consulta y haga clic en **Aceptar** en el cuadro de diálogo emergente.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-138">Click the **Parse** button to validate the query and click **OK** in the pop-up dialog box.</span></span> <span data-ttu-id="0cf9e-139">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-139">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="0cf9e-140">En el **seleccionar tablas de origen y vistas** cuadro de diálogo, seleccione la casilla de verificación en las tablas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-140">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="0cf9e-141">El origen es la consulta especificada para recuperar datos de SAP.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-141">The source is the query you specified to retrieve data from SAP.</span></span> <span data-ttu-id="0cf9e-142">El destino es la tabla que se creará en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-142">The destination is the table that will be created in the SQL Server database.</span></span>  
  
9. <span data-ttu-id="0cf9e-143">El asistente crea una asignación predeterminada entre el origen y el destino de campos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-143">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="0cf9e-144">Sin embargo, puede cambiar las asignaciones de acuerdo con sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-144">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="0cf9e-145">Para cambiar las asignaciones de campos, haga clic en **editar asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-145">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="0cf9e-146">![Asignaciones de columnas entre tablas SAP y SQL](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span><span class="sxs-lookup"><span data-stu-id="0cf9e-146">![Column mappings between SAP and SQL tables](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span></span>  
  
10. <span data-ttu-id="0cf9e-147">En el **asignaciones de columnas** cuadro de diálogo, puede:</span><span class="sxs-lookup"><span data-stu-id="0cf9e-147">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="0cf9e-148">Cambiar los nombres de columnas en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-148">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="0cf9e-149">Omitir ciertas columnas de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-149">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="0cf9e-150">Cambiar el tipo de datos para los campos de tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-150">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="0cf9e-151">Cambiar otros atributos de campo como que acepta valores NULL, el tamaño, la precisión y la escala.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-151">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="0cf9e-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-152">Click **OK**.</span></span>  
  
11. <span data-ttu-id="0cf9e-153">En el **seleccionar tablas de origen y vistas** cuadro de diálogo, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-153">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
12. <span data-ttu-id="0cf9e-154">En el **Complete el asistente** diálogo cuadro, revise el resumen de las acciones que el asistente va a realizar y haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-154">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and click **Finish**.</span></span>  
  
13. <span data-ttu-id="0cf9e-155">En el **operación en curso** cuadro de diálogo, el asistente inicia la ejecución de tareas para importar la información de SAP en una tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-155">In the **Performing Operation** dialog box, the wizard starts executing tasks to import the information from SAP into a SQL Server database table.</span></span> <span data-ttu-id="0cf9e-156">El estado de cada tarea se muestra en el asistente.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-156">The status for each task is displayed in the wizard.</span></span>  
  
14. <span data-ttu-id="0cf9e-157">Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-157">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="0cf9e-158">Si se produce un error en una tarea, vea el correspondiente mensaje de error, corrija el problema y vuelva a ejecutar al asistente.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-158">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
15. <span data-ttu-id="0cf9e-159">El asistente agrega un paquete SSIS para el proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-159">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="0cf9e-160">Guarde el proyecto de servicio de integración.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-160">Save the Integration Service project.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="0cf9e-161">Ejecutar el paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="0cf9e-161">Running the SSIS Package</span></span>  
 <span data-ttu-id="0cf9e-162">Una vez que el paquete se crea dentro de un proyecto de servicio de integración, puede ejecutarla para importar datos desde un sistema SAP en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-162">Once the package is created within an Integration Service project, you can execute it to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="0cf9e-163">Realice los pasos siguientes para importar datos SAP mediante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-163">Perform the following steps to import SAP data by executing the package.</span></span>  
  
#### <a name="to-run-the-package-from-visual-studio"></a><span data-ttu-id="0cf9e-164">Para ejecutar el paquete de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0cf9e-164">To run the package from Visual Studio</span></span>  
  
1.  <span data-ttu-id="0cf9e-165">Navegue hasta el paquete SSIS en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-165">Navigate to the SSIS package in the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="0cf9e-166">Haga clic en el nombre del paquete y seleccione **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-166">Right-click the package name and select **Execute Package**.</span></span>  
  
 <span data-ttu-id="0cf9e-167">Para obtener más información sobre la ejecución de paquetes, consulte [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span><span class="sxs-lookup"><span data-stu-id="0cf9e-167">For more information about running packages, see [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="0cf9e-168">Para cualquier otra información relacionada con paquetes de SSIS, vea [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span><span class="sxs-lookup"><span data-stu-id="0cf9e-168">For any other information related to SSIS packages, see [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="0cf9e-169">Comprobar los resultados</span><span class="sxs-lookup"><span data-stu-id="0cf9e-169">Verifying the Results</span></span>  
 <span data-ttu-id="0cf9e-170">Después de ejecutar el paquete, debe comprobar los resultados de inicio de sesión en el servidor SQL Server y yendo a la base de datos a la que se importan los datos SAP.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-170">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the SAP data is imported.</span></span> <span data-ttu-id="0cf9e-171">Ejecutar el paquete debe haber creado una tabla de base de datos de destino y rellena con los valores de la tabla SAP.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-171">Executing the package should have created a table in destination database and populated with the values from the SAP table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf9e-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cf9e-172">See Also</span></span>  
 [<span data-ttu-id="0cf9e-173">Usar el proveedor de datos para SAP con SSIS</span><span class="sxs-lookup"><span data-stu-id="0cf9e-173">Use the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)