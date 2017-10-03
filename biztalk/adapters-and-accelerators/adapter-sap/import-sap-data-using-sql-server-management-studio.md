---
title: Importar datos SAP con SQL Server Management Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- SQL Server Management Studio, importing data
ms.assetid: c8151c6d-4b33-40fe-9b83-9bed27df9a99
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28981d2130e82a094e470de1e2b6904382be56b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="import-sap-data-using-sql-server-management-studio"></a><span data-ttu-id="b9dd8-102">Importar datos SAP con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9dd8-102">Import SAP Data Using SQL Server Management Studio</span></span>
<span data-ttu-id="b9dd8-103">Esta sección proporciona información sobre cómo usar SQL Server Management Studio para importar datos desde un sistema SAP en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-103">This section provides information on how to use the SQL Server Management Studio to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="b9dd8-104">Esta sección proporciona instrucciones sobre cómo crear un paquete SSIS que se puede ejecutar para importar datos.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-104">This section provides instruction on how to create an SSIS package that you can execute to import data.</span></span> <span data-ttu-id="b9dd8-105">En esta sección también proporciona información sobre cómo ejecutar el paquete SSIS.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-105">This section also provides information on how to execute the SSIS package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b9dd8-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b9dd8-106">Prerequisites</span></span>  
 <span data-ttu-id="b9dd8-107">Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="b9dd8-107">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="b9dd8-108">está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-108"> is installed on the computer.</span></span>  
  
-   <span data-ttu-id="b9dd8-109">SQL Server Business Intelligence Development Studio está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-109">SQL Server Business Intelligence Development Studio is installed on the computer.</span></span>  
  
### <a name="to-import-data-using-sql-server-management-studio"></a><span data-ttu-id="b9dd8-110">Para importar datos mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9dd8-110">To import data using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="b9dd8-111">Inicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-111">Start the SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="b9dd8-112">En el **conectar al servidor** diálogo cuadro, especifique los valores para conectarse a una base de datos de SQL Server y haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-112">In the **Connect to Server** dialog box, specify the values to connect to a SQL Server database and click **Connect**.</span></span> <span data-ttu-id="b9dd8-113">El **Microsoft SQL Server Management Studio** se abre.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-113">The **Microsoft SQL Server Management Studio** opens.</span></span>  
  
3.  <span data-ttu-id="b9dd8-114">En el **Explorador de objetos**, expanda el nombre de SQL Server, **bases de datos**y haga clic en la base de datos en la que va a exportar las tablas del sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-114">In the **Object Explorer**, expand the SQL Server name, expand **Databases**, and right-click the database into which you will be exporting the tables from the SAP system.</span></span> <span data-ttu-id="b9dd8-115">En el menú contextual, seleccione **tareas**y haga clic en **importar datos**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-115">From the context menu, point to **Tasks**, and click **Import Data**.</span></span> <span data-ttu-id="b9dd8-116">Esto inicia el **SQL Server Import and Export Wizard**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-116">This starts the **SQL Server Import and Export Wizard**.</span></span>  
  
4.  <span data-ttu-id="b9dd8-117">Lea la información de la pantalla de bienvenida y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-117">Read the information on the welcome screen and click **Next**.</span></span>  
  
5.  <span data-ttu-id="b9dd8-118">En el **elegir un origen de datos** cuadro de diálogo, desde el **origen de datos** lista desplegable **.NET Framework Data Provider para mySAP Business Suite**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-118">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for mySAP Business Suite**.</span></span> <span data-ttu-id="b9dd8-119">El cuadro de diálogo muestra los parámetros de conexión diferente para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-119">The dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="b9dd8-120">Una cadena de conexión típica para conectarse a un sistema SAP mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere:</span><span class="sxs-lookup"><span data-stu-id="b9dd8-120">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
    -   <span data-ttu-id="b9dd8-121">Los parámetros de conexión para un tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-121">The connection parameters for a connection type.</span></span> <span data-ttu-id="b9dd8-122">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] es compatible con los tipos de conexión A, B y D. Para conectarse a un sistema SAP debe proporcionar parámetros de conexión para cualquier *una* de estos tipos de conexión.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-122">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="b9dd8-123">Por ejemplo, para el tipo de conexión A, debe proporcionar el nombre del host de servidor de aplicación y el número del sistema.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-123">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
    -   <span data-ttu-id="b9dd8-124">La información de inicio de sesión para conectarse a un sistema SAP como nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-124">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="b9dd8-125">Para obtener más información acerca de la cadena de conexión para conectarse a un sistema SAP mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [más información sobre el proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="b9dd8-125">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="b9dd8-126">En el **elegir un origen de datos** diálogo cuadro, especifique:</span><span class="sxs-lookup"><span data-stu-id="b9dd8-126">In the **Choose a Data Source** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="b9dd8-127">Los parámetros de conexión para cualquier tipo de una conexión.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-127">The connection parameters for any one connection type.</span></span>  
  
    -   <span data-ttu-id="b9dd8-128">La información de inicio de sesión para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-128">The login information to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="b9dd8-129">Si desea habilitar la depuración de GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-129">Whether you want to enable SAP GUI debugging.</span></span>  
  
    -   <span data-ttu-id="b9dd8-130">Si desea utilizar el seguimiento de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-130">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="b9dd8-131">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-131">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b9dd8-132">En el **elegir un destino** cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="b9dd8-132">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="b9dd8-133">Desde el **destino** lista desplegable, seleccione **SQL Native Client**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-133">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="b9dd8-134">Desde el **nombre del servidor** lista desplegable, seleccione un nombre de SQL server.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-134">From the **Server name** drop-down list, select a SQL server name.</span></span>  
  
    3.  <span data-ttu-id="b9dd8-135">Seleccione un modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-135">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="b9dd8-136">Desde el **base de datos** lista desplegable, seleccione la base de datos a la que van a importar la tabla SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-136">From the **Database** drop-down list, select the database to which you want to import the SAP table.</span></span>  
  
    5.  <span data-ttu-id="b9dd8-137">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-137">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="b9dd8-138">En el **especificar copia de tabla o consulta** diálogo cuadro, elija la **escribir una consulta para especificar los datos que se va a transferir** opción y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-138">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option and click **Next**.</span></span>  
  
8.  <span data-ttu-id="b9dd8-139">En el **proporcionar una consulta de origen** cuadro de diálogo, especifique una consulta SELECT para filtrar los datos que se importarán en el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-139">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="b9dd8-140">Para obtener más información sobre la gramática de una instrucción SELECT de consulta para la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [sintaxis para un SAP de instrucción seleccionar](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="b9dd8-140">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
     <span data-ttu-id="b9dd8-141">Haga clic en el **analizar** botón para validar la consulta y haga clic en **Aceptar** en el cuadro de diálogo emergente.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-141">Click the **Parse** button to validate the query and click **OK** in the pop-up dialog box.</span></span> <span data-ttu-id="b9dd8-142">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-142">Click **Next**.</span></span>  
  
9. <span data-ttu-id="b9dd8-143">En el **seleccionar tablas de origen y vistas** cuadro de diálogo, seleccione la casilla de verificación en las tablas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-143">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="b9dd8-144">El origen es la consulta especificada para recuperar datos de SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-144">The source is the query you specified to retrieve data from SAP.</span></span> <span data-ttu-id="b9dd8-145">El destino es la tabla que se creará en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-145">The destination is the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="b9dd8-146">El asistente crea una asignación predeterminada entre el origen y el destino de campos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-146">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="b9dd8-147">Sin embargo, puede cambiar las asignaciones de acuerdo con sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-147">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="b9dd8-148">Para cambiar las asignaciones de campos, haga clic en **editar asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-148">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="b9dd8-149">![Asignaciones de columnas entre tablas SAP y SQL](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span><span class="sxs-lookup"><span data-stu-id="b9dd8-149">![Column mappings between SAP and SQL tables](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span></span>  
  
11. <span data-ttu-id="b9dd8-150">En el **asignaciones de columnas** cuadro de diálogo, puede:</span><span class="sxs-lookup"><span data-stu-id="b9dd8-150">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="b9dd8-151">Cambiar los nombres de columnas en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-151">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="b9dd8-152">Omitir ciertas columnas de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-152">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="b9dd8-153">Cambiar el tipo de datos para los campos de tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-153">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="b9dd8-154">Cambiar otros atributos de campo como que acepta valores NULL, el tamaño, la precisión y la escala.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-154">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="b9dd8-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-155">Click **OK**.</span></span>  
  
12. <span data-ttu-id="b9dd8-156">En el **seleccionar tablas de origen y vistas** cuadro de diálogo, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-156">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="b9dd8-157">En el **guardar y ejecutar paquete** cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="b9dd8-157">In the **Save and Execute Package** dialog box,</span></span>  
  
    -   <span data-ttu-id="b9dd8-158">Seleccione el **ejecutar inmediatamente** casilla de verificación para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-158">Select the **Execute immediately** check box to execute the query.</span></span>  
  
    -   <span data-ttu-id="b9dd8-159">Seleccione el **guardar el paquete SSIS** casilla de verificación para guardar la consulta como un paquete y ejecutarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-159">Select the **Save SSIS Package** check box to save the query as a package and execute it later.</span></span> <span data-ttu-id="b9dd8-160">Si decide guardar el paquete, también debe especificar si desea guardar el paquete en el servidor SQL Server o el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-160">If you chose to save the package, you must also specify whether you want to save the package in the SQL Server or the file system.</span></span>  
  
    -   <span data-ttu-id="b9dd8-161">Desde el **nivel de protección del paquete** lista desplegable, seleccione una protección de nivel para el paquete y especifique las credenciales cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-161">From the **Package protection level** drop-down list, select a protection level for the package and specify credentials where required.</span></span>  
  
    -   <span data-ttu-id="b9dd8-162">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-162">Click **Next**.</span></span>  
  
     <span data-ttu-id="b9dd8-163">Si decide guardar el paquete, vaya al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-163">If you chose to save the package, proceed to next step.</span></span> <span data-ttu-id="b9dd8-164">De lo contrario, vaya al paso 15.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-164">Otherwise, skip to step 15.</span></span>  
  
14. <span data-ttu-id="b9dd8-165">En el **guardar el paquete SSIS** diálogo cuadro, especifique:</span><span class="sxs-lookup"><span data-stu-id="b9dd8-165">In the **Save SSIS Package** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="b9dd8-166">Nombre para el paquete</span><span class="sxs-lookup"><span data-stu-id="b9dd8-166">Name for the package</span></span>  
  
    -   <span data-ttu-id="b9dd8-167">Descripción del paquete</span><span class="sxs-lookup"><span data-stu-id="b9dd8-167">Description for the package</span></span>  
  
    -   <span data-ttu-id="b9dd8-168">Si decide guardar el paquete en un servidor SQL server, seleccione un servidor SQL Server desde el **nombre del servidor** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-168">If you chose to save the package to a SQL server, select a SQL Server from the **Server name** drop-down list.</span></span>  
  
    -   <span data-ttu-id="b9dd8-169">Si decide guardar el paquete en el sistema de archivos, especifique el nombre y la ubicación del archivo en el **nombre de archivo** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-169">If you chose to save the package to the file system, specify the name and location of the file in the **File name** text box.</span></span>  
  
    -   <span data-ttu-id="b9dd8-170">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-170">Click **Next**.</span></span>  
  
15. <span data-ttu-id="b9dd8-171">En el **Complete el asistente** diálogo cuadro, revise el resumen de las acciones que el asistente va a realizar y haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-171">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and click **Finish**.</span></span>  
  
16. <span data-ttu-id="b9dd8-172">En el **realizar operaciones de** cuadro de diálogo, el asistente inicia la ejecución de tareas para importar la información de SAP en una tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-172">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from SAP into a SQL Server database table.</span></span> <span data-ttu-id="b9dd8-173">El estado de cada tarea se muestra en el asistente.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-173">The status for each task is displayed in the wizard.</span></span>  
  
17. <span data-ttu-id="b9dd8-174">Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-174">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="b9dd8-175">Si se produce un error en una tarea, vea el correspondiente mensaje de error, corrija el problema y vuelva a ejecutar al asistente.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-175">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="b9dd8-176">Ejecutar el paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="b9dd8-176">Running the SSIS Package</span></span>  
 <span data-ttu-id="b9dd8-177">Si decide guardar el paquete SSIS, puede ejecutarla para recuperar la información más reciente desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-177">If you chose to save the SSIS package, you can run it to retrieve the most recent information from the SAP system.</span></span> <span data-ttu-id="b9dd8-178">Esta sección proporciona información sobre cómo ejecutar el paquete si decide guardarlo en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-178">This section provides information on how to run the package if you chose to save it to the file system.</span></span>  
  
#### <a name="to-run-the-package-from-windows-explorer"></a><span data-ttu-id="b9dd8-179">Para ejecutar el paquete desde el Explorador de Windows</span><span class="sxs-lookup"><span data-stu-id="b9dd8-179">To run the package from Windows Explorer</span></span>  
  
1.  <span data-ttu-id="b9dd8-180">Desde el **el Explorador de Windows**, navegue hasta la ubicación donde guardó el paquete y haga doble clic en el paquete.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-180">From the **Windows Explorer**, navigate to the location where you saved the package, and double-click the package.</span></span>  
  
2.  <span data-ttu-id="b9dd8-181">En el **paquete utilidad de ejecución de** cuadro de diálogo, haga clic en **Execute**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-181">On the **Execute Package Utility** dialog box, click **Execute**.</span></span>  
  
3.  <span data-ttu-id="b9dd8-182">El **progreso de ejecución del paquete** cuadro de diálogo muestra el progreso de las distintas tareas.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-182">The **Package Execution Progress** dialog box displays the progress of the different tasks.</span></span>  
  
4.  <span data-ttu-id="b9dd8-183">Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-183">After all the tasks are successfully executed, click **Close**.</span></span>  
  
5.  <span data-ttu-id="b9dd8-184">En el **paquete utilidad de ejecución de** cuadro de diálogo, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-184">On the **Execute Package Utility** dialog box, click **Close**.</span></span>  
  
 <span data-ttu-id="b9dd8-185">Para obtener más información sobre la ejecución de paquetes, consulte [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span><span class="sxs-lookup"><span data-stu-id="b9dd8-185">For more information about running packages, see [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="b9dd8-186">Para cualquier otra información relacionada con paquetes de SSIS, vea [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span><span class="sxs-lookup"><span data-stu-id="b9dd8-186">For any other information related to SSIS packages, see [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="b9dd8-187">Comprobar los resultados</span><span class="sxs-lookup"><span data-stu-id="b9dd8-187">Verifying the Results</span></span>  
 <span data-ttu-id="b9dd8-188">Después de ejecutar el paquete, debe comprobar los resultados, vaya a la base de datos de SQL Server a la que se importan los datos SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-188">After executing the package, you must verify the results by going to the SQL Server database to which the SAP data is imported.</span></span> <span data-ttu-id="b9dd8-189">Ejecutar el paquete debe haber creado una tabla de base de datos de destino y rellena con los valores de la tabla SAP.</span><span class="sxs-lookup"><span data-stu-id="b9dd8-189">Executing the package should have created a table in destination database and populated with the values from the SAP table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9dd8-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9dd8-190">See Also</span></span>  
 [<span data-ttu-id="b9dd8-191">Mediante el proveedor de datos para SAP con SSIS</span><span class="sxs-lookup"><span data-stu-id="b9dd8-191">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)