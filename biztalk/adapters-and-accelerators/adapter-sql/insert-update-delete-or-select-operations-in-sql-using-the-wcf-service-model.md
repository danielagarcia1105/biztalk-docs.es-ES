---
title: Insertar, actualizar, eliminar o seleccionar las operaciones de SQL mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340048ad-ce28-4acf-ae4e-f18bdb3b6f47
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2bc522a1b0b60a9ba0b8407228dd1db65c4e6f0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22226092"
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="a12c7-102">Insertar, actualizar, eliminar o seleccionar las operaciones de SQL mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a12c7-102">Insert, update, delete, or select operations in SQL using the WCF service model</span></span>
<span data-ttu-id="a12c7-103">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] detecta un conjunto de operaciones básicas de Insert, Select, Update y Delete en vistas y tablas de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a12c7-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on SQL Server database tables and views.</span></span> <span data-ttu-id="a12c7-104">Mediante el uso de estas operaciones, puede realizar simple SQL Insert, Select, Update y eliminar instrucciones que califican Where cláusula en una tabla de destino o la vista.</span><span class="sxs-lookup"><span data-stu-id="a12c7-104">By using these operations, you can perform simple SQL Insert, Select, Update, and Delete statements qualified by a Where clause on a target table or view.</span></span> <span data-ttu-id="a12c7-105">Este tema proporciona instrucciones sobre cómo realizar estas operaciones mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="a12c7-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  
  
 <span data-ttu-id="a12c7-106">Para obtener más información sobre cómo el adaptador es compatible con estas operaciones, vea [Insert, Update, Delete y seleccione las operaciones en tablas y vistas con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a12c7-106">For more information on how the adapter supports these operations, see [Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a12c7-107">Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a12c7-107">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="a12c7-108">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="a12c7-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="a12c7-109">El ejemplo de este tema realiza operaciones en la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="a12c7-109">The example in this topic performs operations on the Employee table.</span></span> <span data-ttu-id="a12c7-110">La tabla de empleados se crea al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a12c7-110">The Employee table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="a12c7-111">Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a12c7-111">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="a12c7-112">Obtener un ejemplo, **EmployeeBasicOps**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a12c7-112">A sample, **EmployeeBasicOps**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="a12c7-113">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="a12c7-113">The WCF Client Class</span></span>  
 <span data-ttu-id="a12c7-114">El nombre del cliente WCF que se genera para las operaciones básicas de SQL que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a12c7-114">The name of the WCF client generated for the basic SQL operations that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="a12c7-115">Artefactos de base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="a12c7-115">SQL Server Database Artifact</span></span>|<span data-ttu-id="a12c7-116">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="a12c7-116">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="a12c7-117">Table</span><span class="sxs-lookup"><span data-stu-id="a12c7-117">Table</span></span>|<span data-ttu-id="a12c7-118">TableOp_[Schema]_[TABLE_NAME]Client</span><span class="sxs-lookup"><span data-stu-id="a12c7-118">TableOp_[Schema]_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="a12c7-119">Ver</span><span class="sxs-lookup"><span data-stu-id="a12c7-119">View</span></span>|<span data-ttu-id="a12c7-120">ViewOp_[Schema]_[VIEW_NAME]Client</span><span class="sxs-lookup"><span data-stu-id="a12c7-120">ViewOp_[Schema]_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="a12c7-121">[Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.</span><span class="sxs-lookup"><span data-stu-id="a12c7-121">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="a12c7-122">[NombreTabla] = el nombre de la tabla. Por ejemplo, el empleado.</span><span class="sxs-lookup"><span data-stu-id="a12c7-122">[TABLE_NAME] = The name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="a12c7-123">[VIEW_NAME] = el nombre de la vista; Por ejemplo, Employee_View.</span><span class="sxs-lookup"><span data-stu-id="a12c7-123">[VIEW_NAME] = The name of the view; for example, Employee_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="a12c7-124">Firma de método para invocar operaciones en tablas</span><span class="sxs-lookup"><span data-stu-id="a12c7-124">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="a12c7-125">La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla.</span><span class="sxs-lookup"><span data-stu-id="a12c7-125">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="a12c7-126">Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a12c7-126">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="a12c7-127">Operación</span><span class="sxs-lookup"><span data-stu-id="a12c7-127">Operation</span></span>|<span data-ttu-id="a12c7-128">Firma de método</span><span class="sxs-lookup"><span data-stu-id="a12c7-128">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="a12c7-129">Insert</span><span class="sxs-lookup"><span data-stu-id="a12c7-129">Insert</span></span>|<span data-ttu-id="a12c7-130">long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);</span><span class="sxs-lookup"><span data-stu-id="a12c7-130">long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);</span></span>|  
|<span data-ttu-id="a12c7-131">Select</span><span class="sxs-lookup"><span data-stu-id="a12c7-131">Select</span></span>|<span data-ttu-id="a12c7-132">[TABLE_NS]. [NOMBRETABLA] [] Seleccione (cadena de columnas, la cadena de consulta);</span><span class="sxs-lookup"><span data-stu-id="a12c7-132">[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);</span></span>|  
|<span data-ttu-id="a12c7-133">Update</span><span class="sxs-lookup"><span data-stu-id="a12c7-133">Update</span></span>|<span data-ttu-id="a12c7-134">int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);</span><span class="sxs-lookup"><span data-stu-id="a12c7-134">int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);</span></span>|  
|<span data-ttu-id="a12c7-135">Delete</span><span class="sxs-lookup"><span data-stu-id="a12c7-135">Delete</span></span>|<span data-ttu-id="a12c7-136">int Delete ([TABLE_NS]. [ Filas NombreTabla] []);</span><span class="sxs-lookup"><span data-stu-id="a12c7-136">int Delete([TABLE_NS].[TABLE_NAME][] Rows);</span></span>|  
  
 <span data-ttu-id="a12c7-137">[TABLE_NS] = el nombre del espacio de nombres de tabla; Por ejemplo, schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee.</span><span class="sxs-lookup"><span data-stu-id="a12c7-137">[TABLE_NS] = The name of the table namespace; for example, schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee.</span></span>  
  
 <span data-ttu-id="a12c7-138">[NombreTabla] = el nombre de la tabla. Por ejemplo, el empleado.</span><span class="sxs-lookup"><span data-stu-id="a12c7-138">[TABLE_NAME] = The name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="a12c7-139">Por ejemplo, el código siguiente muestra las firmas de método para una clase de cliente WCF generado para las operaciones Delete, Insert, Select y Update en la tabla de empleados en el esquema predeterminado "dbo".</span><span class="sxs-lookup"><span data-stu-id="a12c7-139">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the Employee table under the default “dbo” schema.</span></span>  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 <span data-ttu-id="a12c7-140">En este fragmento de código, TableOp_dbo_EmployeeClient es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a12c7-140">In this snippet, TableOp_dbo_EmployeeClient is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="a12c7-141">Parámetros para las operaciones de tabla</span><span class="sxs-lookup"><span data-stu-id="a12c7-141">Parameters for Table Operations</span></span>  
 <span data-ttu-id="a12c7-142">Esta sección proporciona los parámetros requeridos por cada operación de tabla</span><span class="sxs-lookup"><span data-stu-id="a12c7-142">This section provides the parameters required by each table operation</span></span>  
  
 <span data-ttu-id="a12c7-143">**Operación de inserción**</span><span class="sxs-lookup"><span data-stu-id="a12c7-143">**Insert Operation**</span></span>  
  
|<span data-ttu-id="a12c7-144">Insertar tipo de operación</span><span class="sxs-lookup"><span data-stu-id="a12c7-144">Insert operation type</span></span>|<span data-ttu-id="a12c7-145">CONJUNTO DE REGISTROS</span><span class="sxs-lookup"><span data-stu-id="a12c7-145">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="a12c7-146">Registro de varios</span><span class="sxs-lookup"><span data-stu-id="a12c7-146">Multiple record</span></span>|<span data-ttu-id="a12c7-147">Una colección de INSERTRECORDS que se deben insertar en la tabla.</span><span class="sxs-lookup"><span data-stu-id="a12c7-147">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  
  
 <span data-ttu-id="a12c7-148">La operación de inserción devuelve una matriz de tipo de datos Long y almacena los valores de identidad de las filas insertadas, si lo hay.</span><span class="sxs-lookup"><span data-stu-id="a12c7-148">The insert operation returns an array of Long data type and stores the identity values of the inserted rows, if any.</span></span> <span data-ttu-id="a12c7-149">Si no hay ninguna columna de identidad en una tabla, el valor devuelto es NULL.</span><span class="sxs-lookup"><span data-stu-id="a12c7-149">If there is no identity column in a table, the return value is NULL.</span></span>  
  
 <span data-ttu-id="a12c7-150">**Seleccione la operación**</span><span class="sxs-lookup"><span data-stu-id="a12c7-150">**Select Operation**</span></span>  
  
|<span data-ttu-id="a12c7-151">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="a12c7-151">COLUMN_NAMES</span></span>|<span data-ttu-id="a12c7-152">QUERY</span><span class="sxs-lookup"><span data-stu-id="a12c7-152">QUERY</span></span>|  
|-------------------|-----------|  
|<span data-ttu-id="a12c7-153">Una lista delimitada por comas de nombres de columna en el destino; Por ejemplo, "IdDeEmpleado, designación".</span><span class="sxs-lookup"><span data-stu-id="a12c7-153">A comma-delimited list of column names in the target; for example, "Employee_ID, Designation".</span></span> <span data-ttu-id="a12c7-154">La lista de columnas especifica las columnas de destino que se deben devolver en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="a12c7-154">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="a12c7-155">Las columnas no especificadas en la lista de columnas se establecerá con sus valores predeterminados de .NET en el conjunto de registros devuelto.</span><span class="sxs-lookup"><span data-stu-id="a12c7-155">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="a12c7-156">Para las columnas nillable, este valor es **null**.</span><span class="sxs-lookup"><span data-stu-id="a12c7-156">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="a12c7-157">El contenido de una cláusula WHERE de SQL que especifica las filas de destino de la consulta; Por ejemplo, "designación = 'Administrador'".</span><span class="sxs-lookup"><span data-stu-id="a12c7-157">The contents of a SQL WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="a12c7-158">Puede establecer este parámetro en **null** para devolver todas las filas de destino.</span><span class="sxs-lookup"><span data-stu-id="a12c7-158">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="a12c7-159">El valor devuelto de la operación seleccionada es un conjunto de resultados fuertemente tipadas que contiene las columnas especificadas y las filas de la tabla de destino o la vista.</span><span class="sxs-lookup"><span data-stu-id="a12c7-159">The return value of the Select operation is a strongly-typed result set that contains the specified columns and rows from the target table or view.</span></span>  
  
 <span data-ttu-id="a12c7-160">**La operación de actualización**</span><span class="sxs-lookup"><span data-stu-id="a12c7-160">**Update Operation**</span></span>  
  
|<span data-ttu-id="a12c7-161">Primera fila del par</span><span class="sxs-lookup"><span data-stu-id="a12c7-161">First row of the pair</span></span>|<span data-ttu-id="a12c7-162">Segunda fila del par</span><span class="sxs-lookup"><span data-stu-id="a12c7-162">Second row of the pair</span></span>|  
|---------------------------|----------------------------|  
|<span data-ttu-id="a12c7-163">El primer registro del registro par corresponde a los nuevos valores que deben actualizarse, es decir, se corresponde con la cláusula SET de la instrucción UPDATE.</span><span class="sxs-lookup"><span data-stu-id="a12c7-163">The first record of the record pair corresponds to new values that need to be updated, that is, it corresponds to the SET clause of the UPDATE statement.</span></span> <span data-ttu-id="a12c7-164">Esto se puede establecer utilizando `RowPair.After`.</span><span class="sxs-lookup"><span data-stu-id="a12c7-164">This can be set using `RowPair.After`.</span></span>|<span data-ttu-id="a12c7-165">El segundo registro del par de registro corresponde a los valores anteriores de las filas, es decir, corresponde a la cláusula WHERE de la instrucción UPDATE.</span><span class="sxs-lookup"><span data-stu-id="a12c7-165">The second record of the record pair corresponds to the old values of the rows, that is, it corresponds to the WHERE clause of the UPDATE statement.</span></span> <span data-ttu-id="a12c7-166">Esto se puede establecer utilizando `RowPair.Before`.</span><span class="sxs-lookup"><span data-stu-id="a12c7-166">This can be set using `RowPair.Before`.</span></span>|  
  
 <span data-ttu-id="a12c7-167">El valor devuelto de la operación de actualización es de tipo de dato Int32 e indica el número de filas actualizadas.</span><span class="sxs-lookup"><span data-stu-id="a12c7-167">The return value of the Update operation is of Int32 data type, and denotes the number of rows updated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a12c7-168">Al especificar el registro que debe actualizarse, debe proporcionar valores para todas las columnas, incluso si no se actualizan todos los valores.</span><span class="sxs-lookup"><span data-stu-id="a12c7-168">While specifying the record that has to be updated, you must provide values for all the columns, even if all values are not being updated.</span></span> <span data-ttu-id="a12c7-169">Por ejemplo, si una fila tiene cinco columnas y la operación de actualización actualiza solo 2 columnas, como parte de RowPair.Before, debe pasar todos los valores de 5 columna.</span><span class="sxs-lookup"><span data-stu-id="a12c7-169">For example, if a row has five columns and the Update operation updates only 2 columns, as part of RowPair.Before, you must pass all the 5 column values.</span></span> <span data-ttu-id="a12c7-170">Sin embargo, para RowPair.After, puede especificar solo las columnas que se actualizará.</span><span class="sxs-lookup"><span data-stu-id="a12c7-170">However, for RowPair.After, you can specify only the columns that will be updated.</span></span>  
  
 <span data-ttu-id="a12c7-171">**La operación de eliminación**</span><span class="sxs-lookup"><span data-stu-id="a12c7-171">**Delete Operation**</span></span>  
  
 <span data-ttu-id="a12c7-172">La operación de eliminación se toma como matriz de entrada fuertemente tipada de registros.</span><span class="sxs-lookup"><span data-stu-id="a12c7-172">The Delete operation takes as input a strongly-typed array of records.</span></span> <span data-ttu-id="a12c7-173">El valor devuelto de la operación de eliminación es del tipo de dato Int32 e indica el número de filas eliminadas.</span><span class="sxs-lookup"><span data-stu-id="a12c7-173">The return value of the Delete operation is of Int32 data type, and denotes the number of rows deleted.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a><span data-ttu-id="a12c7-174">Creación de un cliente WCF para invocar operaciones en tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="a12c7-174">Creating a WCF Client to Invoke Operations on Tables and Views</span></span>  
 <span data-ttu-id="a12c7-175">El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a12c7-175">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="a12c7-176">En esta sección se describe cómo crear un cliente WCF para invocar básicas Insert, Select, Update, las operaciones Delete en una tabla.</span><span class="sxs-lookup"><span data-stu-id="a12c7-176">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on a table.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="a12c7-177">Para crear un cliente WCF para llevar a cabo operaciones en tablas</span><span class="sxs-lookup"><span data-stu-id="a12c7-177">To create a WCF client to perform operations on tables</span></span>  
  
1.  <span data-ttu-id="a12c7-178">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a12c7-178">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="a12c7-179">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="a12c7-179">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="a12c7-180">Generar la clase de cliente WCF para la inserción, Select, Update y, en la tabla de empleados de la operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="a12c7-180">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the Employee table.</span></span> <span data-ttu-id="a12c7-181">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="a12c7-181">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a12c7-182">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="a12c7-182">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="a12c7-183">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="a12c7-183">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="a12c7-184">Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="a12c7-184">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="a12c7-185">En este fragmento de código, `TableOp_dbo_EmployeeClient` es el cliente WCF definido en SqlAdapterBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="a12c7-185">In this snippet, `TableOp_dbo_EmployeeClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="a12c7-186">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a12c7-186">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="a12c7-187">`SqlAdapterBinding_TableOp_dbo_Employee` es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="a12c7-187">`SqlAdapterBinding_TableOp_dbo_Employee` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a12c7-188">En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a12c7-188">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="a12c7-189">Puede especificar también explícitamente estos valores en el código.</span><span class="sxs-lookup"><span data-stu-id="a12c7-189">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="a12c7-190">Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a12c7-190">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="a12c7-191">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="a12c7-191">Open the client as described in the snippet below:</span></span>  
  
    ```  
    try  
    {  
       Console.WriteLine("Opening Client...");  
       client.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    ```  
  
6.  <span data-ttu-id="a12c7-192">Invocar la operación de inserción en la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="a12c7-192">Invoke the Insert operation on the Employee table.</span></span>  
  
    ```  
    long[] recordsInserted;  
  
    schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] insertRecord =  
    new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
    insertRecord[0] = new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
    insertRecord[0].Name = "John Smith";  
    insertRecord[0].Designation = "Manager";  
    insertRecord[0].Salary = 500000;  
  
    try  
    {  
       Console.WriteLine("Inserting new table entry...");  
       recordsInserted = client.Insert(insertRecord);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    Console.WriteLine("Record inserted");  
    Console.WriteLine("Press any key to continue ...");  
    Console.ReadLine();  
    ```  
  
     <span data-ttu-id="a12c7-193">Puede reemplazar el fragmento de código anterior para llevar a cabo Select, Update o Delete también las operaciones.</span><span class="sxs-lookup"><span data-stu-id="a12c7-193">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="a12c7-194">También puede agregar los fragmentos de código para llevar a cabo todas las operaciones en una sola aplicación.</span><span class="sxs-lookup"><span data-stu-id="a12c7-194">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="a12c7-195">Para fragmentos de código sobre cómo realizar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="a12c7-195">For code snippets on how to perform these operations.</span></span>  
  
7.  <span data-ttu-id="a12c7-196">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="a12c7-196">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="a12c7-197">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="a12c7-197">Build the project and then run it.</span></span> <span data-ttu-id="a12c7-198">La aplicación inserta un registro en la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="a12c7-198">The application inserts a record in the Employee table.</span></span>  
  
###   <a name="select-operation"></a><span data-ttu-id="a12c7-199">Seleccione la operación</span><span class="sxs-lookup"><span data-stu-id="a12c7-199">Select Operation</span></span>  
 <span data-ttu-id="a12c7-200">El código siguiente muestra una operación de selección que tenga como destino de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="a12c7-200">The following code shows a Select operation that targets the Employee table.</span></span> <span data-ttu-id="a12c7-201">La operación de selección, selecciona el último registro insertado en la tabla.</span><span class="sxs-lookup"><span data-stu-id="a12c7-201">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="a12c7-202">Los registros devueltos se escriben en la consola.</span><span class="sxs-lookup"><span data-stu-id="a12c7-202">The returned records are written to the console.</span></span>  
  
```  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
try  
{  
   Console.WriteLine("Selecting Row...");  
   selectRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("The details of the newly added employee are:");  
Console.WriteLine("********************************************");  
for (int i = 0; i < selectRecords.Length; i++)  
{  
   Console.WriteLine("Employee ID        : " + selectRecords[i].Employee_ID);  
   Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
   Console.WriteLine("Employee Desigation: " + selectRecords[i].Designation);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="update-operation"></a><span data-ttu-id="a12c7-203">La operación de actualización</span><span class="sxs-lookup"><span data-stu-id="a12c7-203">Update Operation</span></span>  
 <span data-ttu-id="a12c7-204">El código siguiente muestra una operación de actualización que tenga como destino de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="a12c7-204">The following code shows an Update operation that targets the Employee table.</span></span>  
  
```  
int result;  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair updateRecordPair =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair();  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee updateRecord =   
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] updateArray =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[1];  
  
updateRecord = insertRecord[0];  
updateRecord.Name = "Jeff Smith";  
  
updateRecordPair.After = updateRecord;  
updateRecordPair.Before = selectRecords[0];  
  
updateArray[0] = updateRecordPair;  
  
try  
{  
   Console.WriteLine("Updating the database...");  
   result = client.Update(updateArray);  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("Updated Record for {0}", updateRecordPair.Before.Name);  
Console.WriteLine("The new name for the employee is {0}", updateRecordPair.After.Name);  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="delete-operation"></a><span data-ttu-id="a12c7-205">Operación de eliminación</span><span class="sxs-lookup"><span data-stu-id="a12c7-205">Delete Operation</span></span>  
 <span data-ttu-id="a12c7-206">El código siguiente muestra una operación de eliminación que tenga como destino de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="a12c7-206">The following code shows a Delete operation that targets the Employee table.</span></span>  
  
```  
int deleteSuccess;  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] deleteRecords =  
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
deleteRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
  
Console.WriteLine("Following employees will be deleted from the database:");  
for (int i = 0; i < deleteRecords.Length; i++)  
{  
   Console.WriteLine("Name: {0}", deleteRecords[i].Name);  
}  
Console.WriteLine("Press any key to begin deletion...");  
Console.ReadLine();  
  
try  
{  
   Console.WriteLine("Deleting employee record...");  
   deleteSuccess = client.Delete(deleteRecords);  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a12c7-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="a12c7-207">See Also</span></span>  
[<span data-ttu-id="a12c7-208">Desarrollar aplicaciones con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a12c7-208">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)