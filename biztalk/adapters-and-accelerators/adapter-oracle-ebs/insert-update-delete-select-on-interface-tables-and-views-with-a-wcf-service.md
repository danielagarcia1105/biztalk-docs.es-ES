---
title: Insertar, actualizar, eliminar o seleccionar operaciones en tablas de interfaz y vistas que usan el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae613c0e-4d9a-4c66-99e4-dd0443f1d495
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc9e3968b760be10b428e39662ec3d09db490cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-or-select-operations-on-interface-tables-and-views-using-the-wcf-service-model"></a><span data-ttu-id="e80e6-102">Insertar, actualizar, eliminar o seleccionar operaciones en tablas de interfaz y vistas que usan el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="e80e6-102">Insert, update, delete, or select operations on interface tables and views using the WCF service model</span></span>
<span data-ttu-id="e80e6-103">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] detecta un conjunto de operaciones básicas de Insert, Select, Update y Delete en tablas de interfaz.</span><span class="sxs-lookup"><span data-stu-id="e80e6-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on interface tables.</span></span> <span data-ttu-id="e80e6-104">Mediante el uso de estas operaciones, puede realizar simple Insert, Select, Update y eliminar instrucciones calificadas por una cláusula WHERE en una tabla de la interfaz de destino.</span><span class="sxs-lookup"><span data-stu-id="e80e6-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a WHERE clause on a target interface table.</span></span> <span data-ttu-id="e80e6-105">Este tema proporciona instrucciones sobre cómo realizar estas operaciones mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e80e6-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e80e6-106">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite solo las operaciones en las vistas de interfaz de selección.</span><span class="sxs-lookup"><span data-stu-id="e80e6-106">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports only Select operations on interface views.</span></span>  
  
 <span data-ttu-id="e80e6-107">Para obtener más información acerca del modo en que el adaptador admite estas operaciones, vea [operaciones en tablas de interfaz y vistas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span><span class="sxs-lookup"><span data-stu-id="e80e6-107">For more information about how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e80e6-108">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="e80e6-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e80e6-109">El ejemplo de este tema realiza operaciones en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e80e6-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="e80e6-110">La tabla se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e80e6-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="e80e6-111">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e80e6-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="e80e6-112">Obtener un ejemplo, **Interface_Table_Ops**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e80e6-112">A sample, **Interface_Table_Ops**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="e80e6-113">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="e80e6-113">The WCF Client Class</span></span>  
 <span data-ttu-id="e80e6-114">El nombre del cliente WCF que se genera para las operaciones básicas que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] detecta se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e80e6-114">The name of the WCF client generated for the basic operations that the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="e80e6-115">Artefacto</span><span class="sxs-lookup"><span data-stu-id="e80e6-115">Artifact</span></span>|<span data-ttu-id="e80e6-116">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="e80e6-116">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="e80e6-117">Tablas de interfaz</span><span class="sxs-lookup"><span data-stu-id="e80e6-117">Interface tables</span></span>|<span data-ttu-id="e80e6-118">InterfaceTables_ [APP_NAME] _ [esquema]\_cliente [NombreTabla]</span><span class="sxs-lookup"><span data-stu-id="e80e6-118">InterfaceTables_[APP_NAME]_[SCHEMA]\_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="e80e6-119">Vistas de interfaz</span><span class="sxs-lookup"><span data-stu-id="e80e6-119">Interface views</span></span>|<span data-ttu-id="e80e6-120">InterfaceViews_ [APP_NAME] _ [esquema]\_cliente [VIEW_NAME]</span><span class="sxs-lookup"><span data-stu-id="e80e6-120">InterfaceViews_[APP_NAME]_[SCHEMA]\_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="e80e6-121">[APP_NAME] = nombre real de la aplicación de Oracle E-Business Suite; Por ejemplo, buscar.</span><span class="sxs-lookup"><span data-stu-id="e80e6-121">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
 <span data-ttu-id="e80e6-122">[Esquema] = colección de artefactos; Por ejemplo, las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e80e6-122">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  
  
 <span data-ttu-id="e80e6-123">[NombreTabla] = el nombre de la tabla. Por ejemplo, MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e80e6-123">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="e80e6-124">[VIEW_NAME] = el nombre de la vista; Por ejemplo, MS_SAMPLE_EMPLOYEE_View.</span><span class="sxs-lookup"><span data-stu-id="e80e6-124">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="e80e6-125">Firma de método para invocar operaciones en tablas</span><span class="sxs-lookup"><span data-stu-id="e80e6-125">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="e80e6-126">La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla.</span><span class="sxs-lookup"><span data-stu-id="e80e6-126">The following table shows the method signatures for the basic operations on an table.</span></span> <span data-ttu-id="e80e6-127">Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e80e6-127">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="e80e6-128">Operación</span><span class="sxs-lookup"><span data-stu-id="e80e6-128">Operation</span></span>|<span data-ttu-id="e80e6-129">Firma de método</span><span class="sxs-lookup"><span data-stu-id="e80e6-129">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="e80e6-130">Insert</span><span class="sxs-lookup"><span data-stu-id="e80e6-130">Insert</span></span>|<span data-ttu-id="e80e6-131">cadena Insert (InsertRecord] conjunto de registros);</span><span class="sxs-lookup"><span data-stu-id="e80e6-131">string Insert(InsertRecord[] RECORDSET);</span></span>|  
|<span data-ttu-id="e80e6-132">Select</span><span class="sxs-lookup"><span data-stu-id="e80e6-132">Select</span></span>|<span data-ttu-id="e80e6-133">SelectRecord [] seleccione (string COLUMN_NAMES, cadena de filtro);</span><span class="sxs-lookup"><span data-stu-id="e80e6-133">SelectRecord[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="e80e6-134">Update</span><span class="sxs-lookup"><span data-stu-id="e80e6-134">Update</span></span>|<span data-ttu-id="e80e6-135">cadena Update (UpdateRecord RECORDSET, cadena de filtro);</span><span class="sxs-lookup"><span data-stu-id="e80e6-135">string Update(UpdateRecord RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="e80e6-136">DELETE</span><span class="sxs-lookup"><span data-stu-id="e80e6-136">Delete</span></span>|<span data-ttu-id="e80e6-137">cadena Delete (cadena de filtro);</span><span class="sxs-lookup"><span data-stu-id="e80e6-137">string Delete(string FILTER);</span></span>|  
  
 <span data-ttu-id="e80e6-138">Por ejemplo, el código siguiente muestra las firmas de método para una clase de cliente WCF generado para la eliminación, inserción, seleccione y operaciones Update en la tabla de interfaz MS_SAMPLE_EMPLOYEE en el esquema de aplicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e80e6-138">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the MS_SAMPLE_EMPLOYEE interface table under the default APPS schema.</span></span>  
  
```  
public partial class InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient : System.ServiceModel.ClientBase<InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE>, InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {      
    public SelectRecord[] Select(string COLUMN_NAMES, string FILTER);  
  
    public string Insert(InsertRecord[] RECORDSET);  
  
    public string Update(UpdateRecord RECORDSET, string FILTER);  
  
    public string Delete(string FILTER);  
}  
```  
  
 <span data-ttu-id="e80e6-139">En este fragmento de código, **InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient** es el nombre de la clase WCF en el OracleEBSBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e80e6-139">In this snippet, **InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="e80e6-140">Parámetros para las operaciones de tabla</span><span class="sxs-lookup"><span data-stu-id="e80e6-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="e80e6-141">Esta sección proporciona los parámetros requeridos por cada operación de tabla</span><span class="sxs-lookup"><span data-stu-id="e80e6-141">This section provides the parameters required by each table operation</span></span>  
  
 <span data-ttu-id="e80e6-142">**Seleccione la operación**</span><span class="sxs-lookup"><span data-stu-id="e80e6-142">**Select Operation**</span></span>  
  
|<span data-ttu-id="e80e6-143">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="e80e6-143">COLUMN_NAMES</span></span>|<span data-ttu-id="e80e6-144">FILTER</span><span class="sxs-lookup"><span data-stu-id="e80e6-144">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="e80e6-145">Una lista delimitada por comas de nombres de columna en el destino; Por ejemplo, "EMP_NO, designación".</span><span class="sxs-lookup"><span data-stu-id="e80e6-145">A comma-delimited list of column names in the target; for example, "EMP_NO, DESIGNATION".</span></span> <span data-ttu-id="e80e6-146">La lista de columnas especifica las columnas de destino que se deben devolver en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e80e6-146">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="e80e6-147">Las columnas no especificadas en la lista de columnas se establecerá con sus valores predeterminados de .NET en el conjunto de registros devuelto.</span><span class="sxs-lookup"><span data-stu-id="e80e6-147">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="e80e6-148">Para las columnas nillable, este valor es **null**.</span><span class="sxs-lookup"><span data-stu-id="e80e6-148">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="e80e6-149">El contenido de una cláusula WHERE que especifica las filas de destino de la consulta; Por ejemplo, "designación = 'Administrador'".</span><span class="sxs-lookup"><span data-stu-id="e80e6-149">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="e80e6-150">Puede establecer este parámetro en **null** para devolver todas las filas de destino.</span><span class="sxs-lookup"><span data-stu-id="e80e6-150">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="e80e6-151">El valor devuelto para una operación de selección es un conjunto de resultados fuertemente tipadas que contiene las filas y columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="e80e6-151">The return value for a Select operation is a strongly-typed result set that contains the specified columns and rows.</span></span>  
  
 <span data-ttu-id="e80e6-152">**Operación de inserción**</span><span class="sxs-lookup"><span data-stu-id="e80e6-152">**Insert Operation**</span></span>  
  
|<span data-ttu-id="e80e6-153">Insertar tipo de operación</span><span class="sxs-lookup"><span data-stu-id="e80e6-153">Insert operation type</span></span>|<span data-ttu-id="e80e6-154">CONJUNTO DE REGISTROS</span><span class="sxs-lookup"><span data-stu-id="e80e6-154">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="e80e6-155">Registro de varios</span><span class="sxs-lookup"><span data-stu-id="e80e6-155">Multiple record</span></span>|<span data-ttu-id="e80e6-156">Una colección de INSERTRECORDS que se deben insertar en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e80e6-156">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  
  
 <span data-ttu-id="e80e6-157">El valor devuelto para una operación de inserción es el número de filas insertadas.</span><span class="sxs-lookup"><span data-stu-id="e80e6-157">The return value for an Insert operation is the number of rows inserted.</span></span>  
  
 <span data-ttu-id="e80e6-158">**La operación de actualización**</span><span class="sxs-lookup"><span data-stu-id="e80e6-158">**Update Operation**</span></span>  
  
|<span data-ttu-id="e80e6-159">CONJUNTO DE REGISTROS</span><span class="sxs-lookup"><span data-stu-id="e80e6-159">RECORDSET</span></span>|<span data-ttu-id="e80e6-160">FILTER</span><span class="sxs-lookup"><span data-stu-id="e80e6-160">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="e80e6-161">Una colección de registros que deben actualizarse en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e80e6-161">A collection of records that should be updated in the table.</span></span>|<span data-ttu-id="e80e6-162">El contenido de una cláusula WHERE que especifica las filas de destino de la consulta; Por ejemplo, "designación = 'Administrador'".</span><span class="sxs-lookup"><span data-stu-id="e80e6-162">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="e80e6-163">Puede establecer este parámetro en **null** para devolver todas las filas de destino.</span><span class="sxs-lookup"><span data-stu-id="e80e6-163">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="e80e6-164">El valor devuelto para una operación de actualización es el número de filas actualizadas.</span><span class="sxs-lookup"><span data-stu-id="e80e6-164">The return value for an Update operation is the number of rows updated.</span></span>  
  
 <span data-ttu-id="e80e6-165">**La operación de eliminación**</span><span class="sxs-lookup"><span data-stu-id="e80e6-165">**Delete Operation**</span></span>  
  
 <span data-ttu-id="e80e6-166">La operación de Delete toma como entrada una cláusula WHERE que especifica las filas que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="e80e6-166">The Delete operation takes as input a WHERE clause that specifies the rows to be deleted.</span></span> <span data-ttu-id="e80e6-167">El valor devuelto para una operación de eliminación es el número de filas eliminadas.</span><span class="sxs-lookup"><span data-stu-id="e80e6-167">The return value for a Delete operation is the number of rows deleted.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-interface-tables-and-interface-views"></a><span data-ttu-id="e80e6-168">Creación de un cliente WCF para invocar operaciones en tablas de interfaz y vistas de la interfaz</span><span class="sxs-lookup"><span data-stu-id="e80e6-168">Creating a WCF Client to Invoke Operations on Interface Tables and Interface Views</span></span>  
 <span data-ttu-id="e80e6-169">El conjunto de acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF genérico implica un conjunto de tareas que se describen en [información general del modelo del canal WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e80e6-169">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="e80e6-170">En esta sección se describe cómo crear un cliente WCF para invocar básicas Insert, Select, Update, las operaciones Delete en una tabla de interfaz.</span><span class="sxs-lookup"><span data-stu-id="e80e6-170">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on an interface table.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="e80e6-171">Para crear un cliente WCF para llevar a cabo operaciones en tablas</span><span class="sxs-lookup"><span data-stu-id="e80e6-171">To create a WCF client to perform operations on tables</span></span>  
  
1.  <span data-ttu-id="e80e6-172">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e80e6-172">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="e80e6-173">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="e80e6-173">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="e80e6-174">Generar la clase de cliente WCF para la inserción, Select, Update y, en la tabla de interfaz MS_SAMPLE_EMPLOYEE la operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="e80e6-174">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="e80e6-175">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="e80e6-175">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e80e6-176">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="e80e6-176">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="e80e6-177">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="e80e6-177">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="e80e6-178">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="e80e6-178">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="e80e6-179">Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="e80e6-179">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient client = new InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient(binding, address);  
    ```  
  
     <span data-ttu-id="e80e6-180">En este fragmento de código, `InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient` es el cliente WCF definido en OracleEBSBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="e80e6-180">In this snippet, `InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="e80e6-181">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e80e6-181">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e80e6-182">En este fragmento, especificar explícitamente la dirección de enlace y el punto de conexión en el código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e80e6-182">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="e80e6-183">Puede utilizar estos valores desde el archivo de configuración del aplicación, app.config, también generado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e80e6-183">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="e80e6-184">Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="e80e6-184">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="e80e6-185">Establezca las credenciales para el cliente.</span><span class="sxs-lookup"><span data-stu-id="e80e6-185">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="e80e6-186">Dado que está realizando una operación en una tabla de interfaz, debe establecer el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e80e6-186">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="e80e6-187">En este ejemplo, para establecer el contexto de la aplicación, especifique la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="e80e6-187">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="e80e6-188">Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="e80e6-188">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="e80e6-189">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="e80e6-189">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="e80e6-190">Invocar la operación de inserción en la tabla MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e80e6-190">Invoke the Insert operation on the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
    ```  
    Console.WriteLine("The application will insert a record in the MS_SAMPLE_EMPLOYEE interface table");  
  
    // The date values cannot contain time zone information. Hence, you must use  
    // DateTimeKind.Unspecified to not include the time zone information.  
    DateTime date = new DateTime(DateTime.Now.Ticks, DateTimeKind.Unspecified);  
  
    string result;  
  
    InsertRecord[] recordSet = new InsertRecord[1];  
  
    EMP_NO__COMPLEX_TYPE emp_no = new EMP_NO__COMPLEX_TYPE();  
    emp_no.Value = "10007";  
  
    NAME__COMPLEX_TYPE name = new NAME__COMPLEX_TYPE();  
    name.Value = "John Smith";  
  
    DESIGNATION__COMPLEX_TYPE desig = new DESIGNATION__COMPLEX_TYPE();  
    desig.Value = "Manager";  
  
    SALARY__COMPLEX_TYPE salary = new SALARY__COMPLEX_TYPE();  
    salary.Value = "500000";  
  
    JOIN_DATE__COMPLEX_TYPE doj = new JOIN_DATE__COMPLEX_TYPE();  
    doj.Value = date;  
  
    recordSet[0] = new InsertRecord();  
    recordSet[0].EMP_NO = emp_no;  
    recordSet[0].NAME = name;  
    recordSet[0].DESIGNATION = desig;  
    recordSet[0].SALARY = salary;  
    recordSet[0].JOIN_DATE = doj;  
  
    try  
    {  
       result = client.Insert(recordSet);   
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    Console.WriteLine("Number of records inserted= " + result);  
    Console.WriteLine("Press any key to continue...");  
    Console.ReadLine();  
  
    ```  
  
     <span data-ttu-id="e80e6-191">Puede reemplazar el fragmento de código anterior para llevar a cabo Select, Update o Delete también las operaciones.</span><span class="sxs-lookup"><span data-stu-id="e80e6-191">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="e80e6-192">También puede agregar los fragmentos de código para llevar a cabo todas las operaciones en una sola aplicación.</span><span class="sxs-lookup"><span data-stu-id="e80e6-192">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="e80e6-193">Para fragmentos de código sobre cómo realizar estas operaciones, vea [Seleccionar operación](#BKMK_Select), [operación de actualización](#BKMK_Update), y [operación Delete](#BKMK_Delete) respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e80e6-193">For code snippets on how to perform these operations, see [Select Operation](#BKMK_Select), [Update Operation](#BKMK_Update), and [Delete Operation](#BKMK_Delete) respectively.</span></span>  
  
10. <span data-ttu-id="e80e6-194">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="e80e6-194">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="e80e6-195">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="e80e6-195">Build the project and then run it.</span></span> <span data-ttu-id="e80e6-196">La aplicación inserta un registro en la tabla MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e80e6-196">The application inserts a record in the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
###  <a name="BKMK_Select"></a><span data-ttu-id="e80e6-197">Seleccione la operación</span><span class="sxs-lookup"><span data-stu-id="e80e6-197">Select Operation</span></span>  
 <span data-ttu-id="e80e6-198">El código siguiente muestra una operación de selección que tenga como destino de la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e80e6-198">The following code shows a Select operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="e80e6-199">La operación de selección, selecciona el último registro insertado en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e80e6-199">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="e80e6-200">El registro devuelto se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="e80e6-200">The returned record is written to the console.</span></span>  
  
```  
Console.WriteLine("The application will now select the last inserted record");  
SelectRecord[] selectRecords;  
try  
{  
   selectRecords = client.Select("*", "WHERE EMP_NO LIKE 10007");  
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
   Console.WriteLine("Employee ID         : " + selectRecords[i].EMP_NO);  
   Console.WriteLine("Employee Name       : " + selectRecords[i].NAME);  
   Console.WriteLine("Employee Desigation : " + selectRecords[i].DESIGNATION);  
   Console.WriteLine("Employee Salary     : " + selectRecords[i].SALARY);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###  <a name="BKMK_Update"></a><span data-ttu-id="e80e6-201">La operación de actualización</span><span class="sxs-lookup"><span data-stu-id="e80e6-201">Update Operation</span></span>  
 <span data-ttu-id="e80e6-202">El código siguiente muestra una operación de actualización que tenga como destino de la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e80e6-202">The following code shows an Update operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
```  
Console.WriteLine("The application will now update the employee name in the newly inserted record");  
string recordsUpdated;  
UpdateRecord updateRecordSet = new UpdateRecord();  
updateRecordSet.NAME = "Tom Smith";  
updateRecordSet.DESIGNATION = "Accountant";  
  
try  
{  
   recordsUpdated = client.Update(updateRecordSet, "WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("No of records updated: " + recordsUpdated);  
Console.WriteLine("Press any key to continue...");  
Console.ReadLine();  
```  
  
###  <a name="BKMK_Delete"></a><span data-ttu-id="e80e6-203">La operación de eliminación</span><span class="sxs-lookup"><span data-stu-id="e80e6-203">Delete Operation</span></span>  
 <span data-ttu-id="e80e6-204">El código siguiente muestra una operación de eliminación que tenga como destino de la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e80e6-204">The following code shows a Delete operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
```  
Console.WriteLine("The sample will now delete the record that it first inserted");  
string deletedRecords;  
try  
{  
   deletedRecords = client.Delete("WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
Console.WriteLine("No of records deleted: " + deletedRecords);  
Console.WriteLine("Press any key to exit...");  
Console.ReadLine();  
```  
  
## <a name="see-also"></a><span data-ttu-id="e80e6-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="e80e6-205">See Also</span></span>  
 [<span data-ttu-id="e80e6-206">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="e80e6-206">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)