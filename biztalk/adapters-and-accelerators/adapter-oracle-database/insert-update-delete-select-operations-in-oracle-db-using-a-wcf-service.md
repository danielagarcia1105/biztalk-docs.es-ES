---
title: Insertar, actualizar, eliminar o seleccionar las operaciones de base de datos de Oracle mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, Delete operation
- WCF service model, Select operation
- WCF service model, Insert operation
- WCF service model, Update operation
ms.assetid: d1a9f44f-ea0b-4dd6-9489-fa0d963848c4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91fa9b1828a8519dcbf7e1efba1db99ba84f1d0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982453"
---
# <a name="insert-update-delete-or-select-operations-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="ac950-102">Insertar, actualizar, eliminar o seleccionar las operaciones de base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="ac950-102">Insert, update, delete, or select operations in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="ac950-103">La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un conjunto de básicas Insert, Update, Delete y las operaciones Select en las vistas y tablas de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ac950-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a set of basic Insert, Update, Delete, and Select operations on Oracle database tables and views.</span></span> <span data-ttu-id="ac950-104">Mediante el uso de estas operaciones, puede realizar SELECT SQL INSERT, UPDATE, simple y eliminar instrucciones calificadas por una cláusula WHERE en una tabla de destino o vista.</span><span class="sxs-lookup"><span data-stu-id="ac950-104">By using these operations, you can perform simple SQL INSERT, UPDATE, SELECT, and DELETE statements qualified by a WHERE clause on a target table or view.</span></span> <span data-ttu-id="ac950-105">Para llevar a cabo operaciones más complejas, por ejemplo una consulta de SQL SELECT que utiliza el operador de combinación, puede usar la operación SQLEXECUTE.</span><span class="sxs-lookup"><span data-stu-id="ac950-105">To perform more complex operations, for example a SQL SELECT query that uses the JOIN operator, you can use the SQLEXECUTE operation.</span></span> <span data-ttu-id="ac950-106">Para obtener más información acerca de la operación SQLEXECUTE, consulte [realizar una operación de SQLEXECUTE en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="ac950-106">For more information about the SQLEXECUTE operation, see [Performing a SQLEXECUTE Operation in Oracle Database Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="ac950-107">En la tabla siguiente se resume las operaciones básicas de SQL que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies en tablas y vistas.</span><span class="sxs-lookup"><span data-stu-id="ac950-107">The following table summarizes the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces on tables and views.</span></span> <span data-ttu-id="ac950-108">Para obtener una descripción completa de estas operaciones, consulte [esquemas de mensaje para insertar básica, Update, Delete y seleccione operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span><span class="sxs-lookup"><span data-stu-id="ac950-108">For a complete description of these operations, see [Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
|<span data-ttu-id="ac950-109">Operación</span><span class="sxs-lookup"><span data-stu-id="ac950-109">Operation</span></span>|<span data-ttu-id="ac950-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac950-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac950-111">Insert</span><span class="sxs-lookup"><span data-stu-id="ac950-111">Insert</span></span>|<span data-ttu-id="ac950-112">La operación de inserción admite varias inserciones de registro o de forma masiva en la vista o tabla de destino:</span><span class="sxs-lookup"><span data-stu-id="ac950-112">The Insert operation supports multiple record or bulk inserts into the target table or view:</span></span><br /><br /> <span data-ttu-id="ac950-113">-Una operación de inserción varios registra inserta filas en una tabla o vista en función de un conjunto de registros proporcionado.</span><span class="sxs-lookup"><span data-stu-id="ac950-113">-   A multiple record Insert operation inserts rows into a table or view based on a supplied record set.</span></span><br /><span data-ttu-id="ac950-114">-Una operación de inserción masiva inserta filas en una tabla o vista basándose en una lista proporcionada de consulta y la columna SELECT de SQL.</span><span class="sxs-lookup"><span data-stu-id="ac950-114">-   A bulk Insert operation inserts rows into a table or view based on a supplied SQL SELECT query and column list.</span></span> <span data-ttu-id="ac950-115">Los registros que devuelve la consulta se insertan en la tabla de destino basándose en la lista de columnas.</span><span class="sxs-lookup"><span data-stu-id="ac950-115">The records that the query returns are inserted into the target table based on the column list.</span></span>|  
|<span data-ttu-id="ac950-116">Select</span><span class="sxs-lookup"><span data-stu-id="ac950-116">Select</span></span>|<span data-ttu-id="ac950-117">Realiza una consulta SELECT de SQL en la tabla de destino basándose en una lista proporcionada de nombres de columna y una cadena de filtro que especifica una cláusula WHERE de SQL.</span><span class="sxs-lookup"><span data-stu-id="ac950-117">Performs a SQL SELECT query on the target table based on a supplied list of column names and a filter string that specifies a SQL WHERE clause.</span></span>|  
|<span data-ttu-id="ac950-118">Update</span><span class="sxs-lookup"><span data-stu-id="ac950-118">Update</span></span>|<span data-ttu-id="ac950-119">Realiza una actualización en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-119">Performs an UPDATE on the target table.</span></span> <span data-ttu-id="ac950-120">Los registros que se va a actualizarse se especifican mediante una cadena de filtro que especifica una cláusula WHERE de SQL.</span><span class="sxs-lookup"><span data-stu-id="ac950-120">The records to be updated are specified by a filter string that specifies a SQL WHERE clause.</span></span> <span data-ttu-id="ac950-121">Los valores de la actualización se especifican en un registro de plantilla.</span><span class="sxs-lookup"><span data-stu-id="ac950-121">The values for the update are specified in a template record.</span></span>|  
|<span data-ttu-id="ac950-122">DELETE</span><span class="sxs-lookup"><span data-stu-id="ac950-122">Delete</span></span>|<span data-ttu-id="ac950-123">Realiza una eliminación en la tabla de destino basándose en una cláusula WHERE de SQL que se especifica en una cadena de filtro.</span><span class="sxs-lookup"><span data-stu-id="ac950-123">Performs a DELETE on the target table based on a SQL WHERE clause that is specified in a filter string.</span></span>|  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="ac950-124">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="ac950-124">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="ac950-125">Los ejemplos en este tema usan la tabla /SCOTT/ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac950-125">The examples in this topic use the /SCOTT/ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="ac950-126">Una secuencia de comandos para generar esta tabla se suministra con los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="ac950-126">A script to generate this table is supplied with the SDK samples.</span></span> <span data-ttu-id="ac950-127">Para obtener más información acerca de los ejemplos SDK, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="ac950-127">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="ac950-128">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="ac950-128">The WCF Client Class</span></span>  
 <span data-ttu-id="ac950-129">El nombre del cliente WCF generado para las operaciones básicas de SQL que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ac950-129">The name of the WCF client generated for the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces is based on the name of the table or view, as in the following table.</span></span>  
  
|<span data-ttu-id="ac950-130">Artefacto de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ac950-130">Oracle Database Artifact</span></span>|<span data-ttu-id="ac950-131">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="ac950-131">WCF Client Name</span></span>|  
|------------------------------|---------------------|  
|<span data-ttu-id="ac950-132">Table</span><span class="sxs-lookup"><span data-stu-id="ac950-132">Table</span></span>|<span data-ttu-id="ac950-133">[ESQUEMA] Cliente de Table [NombreTabla]</span><span class="sxs-lookup"><span data-stu-id="ac950-133">[SCHEMA]Table[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="ac950-134">Ver</span><span class="sxs-lookup"><span data-stu-id="ac950-134">View</span></span>|<span data-ttu-id="ac950-135">[ESQUEMA] Cliente de vista [VIEW_NAME]</span><span class="sxs-lookup"><span data-stu-id="ac950-135">[SCHEMA]View[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="ac950-136">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="ac950-136">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="ac950-137">[NombreTabla] = nombre de la tabla. Por ejemplo, ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac950-137">[TABLE_NAME] = The name of the table; for example, ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="ac950-138">[VIEW_NAME] = el nombre de la vista.</span><span class="sxs-lookup"><span data-stu-id="ac950-138">[VIEW_NAME] = The name of the view.</span></span>  
  
 <span data-ttu-id="ac950-139">La siguiente tabla muestra las firmas de método para las operaciones básicas de SQL en una tabla.</span><span class="sxs-lookup"><span data-stu-id="ac950-139">The following table shows the method signatures for the basic SQL operations on a table.</span></span> <span data-ttu-id="ac950-140">Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre reemplazan las de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ac950-140">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="ac950-141">Operación</span><span class="sxs-lookup"><span data-stu-id="ac950-141">Operation</span></span>|<span data-ttu-id="ac950-142">Firma de método</span><span class="sxs-lookup"><span data-stu-id="ac950-142">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="ac950-143">Insert</span><span class="sxs-lookup"><span data-stu-id="ac950-143">Insert</span></span>|<span data-ttu-id="ac950-144">Insertar larga ([TABLE_NS]. [ RECORDINSERT NombreTabla] [] conjunto de registros, cadena COLUMN_NAMES, cadena de consulta);</span><span class="sxs-lookup"><span data-stu-id="ac950-144">long Insert([TABLE_NS].[TABLE_NAME]RECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);</span></span>|  
|<span data-ttu-id="ac950-145">Select</span><span class="sxs-lookup"><span data-stu-id="ac950-145">Select</span></span>|<span data-ttu-id="ac950-146">[TABLE_NS]. [NOMBRETABLA] RECORDSELECT [] seleccione (COLUMN_NAMES, cadena de filtro de cadena);</span><span class="sxs-lookup"><span data-stu-id="ac950-146">[TABLE_NS].[TABLE_NAME]RECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="ac950-147">Update</span><span class="sxs-lookup"><span data-stu-id="ac950-147">Update</span></span>|<span data-ttu-id="ac950-148">Actualizar largo ([TABLE_NS]. [ Table_name] RECORDUPDATE RECORDSET, cadena de filtro);</span><span class="sxs-lookup"><span data-stu-id="ac950-148">long Update([TABLE_NS].[TABLE_NAME]RECORDUPDATE RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="ac950-149">DELETE</span><span class="sxs-lookup"><span data-stu-id="ac950-149">Delete</span></span>|<span data-ttu-id="ac950-150">Eliminar largo (cadena de filtro);</span><span class="sxs-lookup"><span data-stu-id="ac950-150">Long Delete(string FILTER);</span></span>|  
  
 <span data-ttu-id="ac950-151">[TABLE_NS] = el nombre del espacio de nombres de tabla; Por ejemplo, microsoft.lobservices.oracledb._2007._03.SCOTT. Table.ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac950-151">[TABLE_NS] = The name of the table namespace; for example, microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="ac950-152">[NombreTabla] = nombre de la tabla. Por ejemplo, ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac950-152">[TABLE_NAME] = The name of the table; for example, ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="ac950-153">Utilizado por las operaciones de inserción, actualización y seleccionadas los tipos de registro se definen en la tabla o ver el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ac950-153">The record types used by the Insert, Update, and Select operations are all defined in the table or view namespace.</span></span>  
  
 <span data-ttu-id="ac950-154">El código siguiente muestra las firmas de método para una clase de cliente WCF habían generado para el Delete, Insert, Select y Update operaciones en la tabla ACCOUNTACTIVITY/SCOTT /.</span><span class="sxs-lookup"><span data-stu-id="ac950-154">The following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the /SCOTT/ACCOUNTACTIVITY table.</span></span>  
  
```  
public partial class SCOTTTableACCOUNTACTIVITYClient : System.ServiceModel.ClientBase<SCOTTTableACCOUNTACTIVITY>, SCOTTTableACCOUNTACTIVITY {  
  
    public long Delete(string FILTER);  
  
    public long Insert(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);  
  
    public long Update(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE RECORDSET, string FILTER);  
}  
```  
  
## <a name="invoking-the-basic-sql-operations"></a><span data-ttu-id="ac950-155">Invocar las operaciones básicas de SQL</span><span class="sxs-lookup"><span data-stu-id="ac950-155">Invoking the Basic SQL Operations</span></span>  
 <span data-ttu-id="ac950-156">Para invocar las operaciones básicas de SQL en una tabla o vista mediante el uso de un cliente de WCF, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ac950-156">To invoke the basic SQL operations on a table or view by using a WCF client, perform the following steps.</span></span>  
  
1. <span data-ttu-id="ac950-157">Generar una clase de cliente WCF para la tabla de destino o vista.</span><span class="sxs-lookup"><span data-stu-id="ac950-157">Generate a WCF client class for the target table or view.</span></span> <span data-ttu-id="ac950-158">Esta clase debe contener métodos para las operaciones que va a invocar en el artefacto de destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-158">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
2. <span data-ttu-id="ac950-159">Crear una instancia de la clase de cliente WCF e invocar sus métodos para realizar operaciones en la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="ac950-159">Create an instance of the WCF client class and invoke its methods to perform operations on the table or view.</span></span>  
  
   <span data-ttu-id="ac950-160">Para obtener más información acerca de cómo crear una clase de cliente WCF e invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [general del modelo de servicio WCF con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="ac950-160">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
   <span data-ttu-id="ac950-161">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ejecuta cada operación dentro de una transacción en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ac950-161">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span> <span data-ttu-id="ac950-162">Puede controlar el nivel de aislamiento de esta transacción estableciendo la **TransactionIsolationLevel** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ac950-162">You can control the isolation level of this transaction by setting the **TransactionIsolationLevel** binding property.</span></span> <span data-ttu-id="ac950-163">Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] las propiedades de enlace, consulte [trabajar con el adaptador de BizTalk para propiedades de enlace de base de datos de Oracle](https://msdn.microsoft.com/library/dd788467.aspx).</span><span class="sxs-lookup"><span data-stu-id="ac950-163">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
   <span data-ttu-id="ac950-164">Las secciones siguientes proporcionan detalles sobre cómo invocar cada operación básica de SQL en el código.</span><span class="sxs-lookup"><span data-stu-id="ac950-164">The following sections provide details about how to invoke each basic SQL operation in your code.</span></span>  
  
###  <a name="BKMK_InsertOperation"></a> <span data-ttu-id="ac950-165">Operación de inserción</span><span class="sxs-lookup"><span data-stu-id="ac950-165">Insert Operation</span></span>  
 <span data-ttu-id="ac950-166">En la tabla siguiente se muestra cómo establecer los parámetros de varios registros de inserción y las operaciones de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="ac950-166">The following table shows how to set parameters for multiple record Insert and bulk Insert operations.</span></span>  
  
|<span data-ttu-id="ac950-167">Tipo de operación de inserción</span><span class="sxs-lookup"><span data-stu-id="ac950-167">Insert operation type</span></span>|<span data-ttu-id="ac950-168">CONJUNTO DE REGISTROS</span><span class="sxs-lookup"><span data-stu-id="ac950-168">RECORDSET</span></span>|<span data-ttu-id="ac950-169">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="ac950-169">COLUMN_NAMES</span></span>|<span data-ttu-id="ac950-170">QUERY</span><span class="sxs-lookup"><span data-stu-id="ac950-170">QUERY</span></span>|  
|---------------------------|---------------|-------------------|-----------|  
|<span data-ttu-id="ac950-171">Varios registros</span><span class="sxs-lookup"><span data-stu-id="ac950-171">Multiple record</span></span>|<span data-ttu-id="ac950-172">Una colección de INSERTRECORDS que debe insertarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-172">A collection of INSERTRECORDS that should be inserted into the target.</span></span>|<span data-ttu-id="ac950-173">null</span><span class="sxs-lookup"><span data-stu-id="ac950-173">null</span></span>|<span data-ttu-id="ac950-174">null</span><span class="sxs-lookup"><span data-stu-id="ac950-174">null</span></span>|  
|<span data-ttu-id="ac950-175">Masiva</span><span class="sxs-lookup"><span data-stu-id="ac950-175">Bulk</span></span>|<span data-ttu-id="ac950-176">null</span><span class="sxs-lookup"><span data-stu-id="ac950-176">null</span></span>|<span data-ttu-id="ac950-177">Una lista delimitada por comas de nombres de columna en el destino; Por ejemplo, "TID, cuenta".</span><span class="sxs-lookup"><span data-stu-id="ac950-177">A comma-delimited list of column names in the target; for example, "TID, ACCOUNT".</span></span> <span data-ttu-id="ac950-178">La lista de columnas especifica las columnas en la que se deben colocar los resultados de consulta en cada fila insertada.</span><span class="sxs-lookup"><span data-stu-id="ac950-178">The column list specifies the columns into which the query results should be placed in each inserted row.</span></span> <span data-ttu-id="ac950-179">La consulta debe devolver un conjunto de resultados que coincida con las columnas especificadas en la lista de columnas en el número y tipo.</span><span class="sxs-lookup"><span data-stu-id="ac950-179">The query must return a result set that matches the columns specified in the column list in both number and type.</span></span>|<span data-ttu-id="ac950-180">Una consulta SELECT de SQL en una tabla de base de datos o vista que devuelve un conjunto de resultados para insertar en el destino; Por ejemplo, "SELECT (TID, cuenta) de cuenta de WHERE NEW_TRANSACTIONS = 100001".</span><span class="sxs-lookup"><span data-stu-id="ac950-180">A SQL SELECT query on a database table or view that returns a result set to insert into the target; for example, "SELECT (TID, ACCOUNT) FROM NEW_TRANSACTIONS WHERE ACCOUNT = 100001".</span></span> <span data-ttu-id="ac950-181">El conjunto de resultados debe coincidir con la lista de columnas en el número y tipo.</span><span class="sxs-lookup"><span data-stu-id="ac950-181">The result set must match the column list in both number and type.</span></span>|  
  
 <span data-ttu-id="ac950-182">La operación de inserción devuelve el número de registros que se insertan en el destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-182">The Insert operation returns the number of records inserted into the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac950-183">En el modelo de servicio WCF, el conjunto de registros que se usan en la operación de inserción está fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="ac950-183">In the WCF service model, the record set used in the Insert operation is strongly-typed.</span></span> <span data-ttu-id="ac950-184">Puede establecer el valor de una columna nillable para **null** en un registro para excluir esa columna de la operación de inserción; sin embargo, no se puede establecer el valor de una columna para no aceptar valores nil **null**.</span><span class="sxs-lookup"><span data-stu-id="ac950-184">You can set the value of a nillable column to **null** in a record to exclude that column from the Insert operation; however, you cannot set the value of a non-nillable column to **null**.</span></span> <span data-ttu-id="ac950-185">Esto significa que en una operación de inserción registra varios, debe proporcionar valores para todas las columnas no aceptar valores nil en cada registro.</span><span class="sxs-lookup"><span data-stu-id="ac950-185">This means that in a multiple record Insert operation, you must supply values for all non-nillable columns in each record.</span></span> <span data-ttu-id="ac950-186">Además, no hay ninguna compatibilidad con streaming para las operaciones básicas de SQL cuando se usa el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ac950-186">In addition, there is no streaming support for the basic SQL operations when you use the WCF service model.</span></span> <span data-ttu-id="ac950-187">Si la operación de insertar varios registra implica un gran conjunto de registros, esto puede ser una consideración importante.</span><span class="sxs-lookup"><span data-stu-id="ac950-187">If your multiple record Insert operation involves a large record set, this may be an important consideration.</span></span> <span data-ttu-id="ac950-188">Para obtener más información, consulte [limitaciones de invocar las operaciones básicas de SQL mediante el modelo de servicio WCF](#BKMK_LimitationsInvoking).</span><span class="sxs-lookup"><span data-stu-id="ac950-188">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="ac950-189">El código siguiente muestra una varios registra operación de inserción (registros de dos) que tenga como destino de la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac950-189">The following code shows a multiple record Insert operation (two records) that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
// Insert records  
                using (SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
                    new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY"))  
                {  
                    long recsInserted;  
  
                    aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
                    aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
  
                    try  
                    {  
                        aaTableClient.Open();  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    // Do a multiple record Insert of 2 records for account 100001  
  
                    microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] insertRecs =  
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[2];  
  
                                  TID__COMPLEX_TYPE tid = new TID__COMPLEX_TYPE();  
                                  tid.InlineValue = "tidSequence.NextVal()";  
  
                                  ACCOUNT__COMPLEX_TYPE account = new ACCOUNT__COMPLEX_TYPE();  
                                  account.Value = 100001;  
  
                    AMOUNT__COMPLEX_TYPE amount = new AMOUNT__COMPLEX_TYPE();  
                    amount.Value = 400;  
  
                    TRANSDATE__COMPLEX_TYPE transdate = new TRANSDATE__COMPLEX_TYPE();  
                    transdate.Value = DateTime.Now.Date;  
  
                    PROCESSED__COMPLEX_TYPE processed = new PROCESSED__COMPLEX_TYPE();  
                    processed.Value = "n";  
  
                    DESCRIPTION__COMPLEX_TYPE description1 = new DESCRIPTION__COMPLEX_TYPE();  
                    description1.Value = "Inserted Record #1";  
  
                    DESCRIPTION__COMPLEX_TYPE description2 = new DESCRIPTION__COMPLEX_TYPE();  
                    description2.Value = "Inserted Record #2";  
  
                    insertRecs[0] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[0].TID = tid;  
                    insertRecs[0].ACCOUNT = account;  
                    insertRecs[0].AMOUNT = amount;  
                    insertRecs[0].TRANSDATE = transdate;  
                    insertRecs[0].DESCRIPTION = description1;  
                    insertRecs[0].PROCESSED = processed;  
  
                    insertRecs[1] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[1].TID = tid;  
                    insertRecs[1].ACCOUNT = account;  
                    insertRecs[1].AMOUNT = amount;  
                    insertRecs[1].TRANSDATE = transdate;  
                    insertRecs[1].DESCRIPTION = description2;  
                    insertRecs[1].PROCESSED = processed;  
  
                    try  
                    {  
                        recsInserted = aaTableClient.Insert(insertRecs, null, null);  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    Console.WriteLine("Insert Done: {0} records inserted", recsInserted);  
```  
  
### <a name="select-operation"></a><span data-ttu-id="ac950-190">Seleccione la operación</span><span class="sxs-lookup"><span data-stu-id="ac950-190">Select Operation</span></span>  
 <span data-ttu-id="ac950-191">En la tabla siguiente se muestra los parámetros para la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="ac950-191">The following table shows the parameters for the Select operation.</span></span>  
  
|<span data-ttu-id="ac950-192">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="ac950-192">COLUMN_NAMES</span></span>|<span data-ttu-id="ac950-193">FILTER</span><span class="sxs-lookup"><span data-stu-id="ac950-193">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="ac950-194">Una lista delimitada por comas de nombres de columna en el destino; Por ejemplo, "TID, cuenta".</span><span class="sxs-lookup"><span data-stu-id="ac950-194">A comma-delimited list of column names in the target; for example, "TID, ACCOUNT".</span></span> <span data-ttu-id="ac950-195">La lista de columnas especifica las columnas de destino que se deben devolver en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ac950-195">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="ac950-196">Las columnas no especificadas en la lista de columnas se establecerá en sus valores predeterminados de .NET en el conjunto de registros devuelto.</span><span class="sxs-lookup"><span data-stu-id="ac950-196">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="ac950-197">Columnas nillable, este valor es **null**.</span><span class="sxs-lookup"><span data-stu-id="ac950-197">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="ac950-198">El contenido de una cláusula WHERE de SQL que especifica las filas de destino de la consulta. Por ejemplo, "descripción = 'Insertar registro #1'".</span><span class="sxs-lookup"><span data-stu-id="ac950-198">The contents of a SQL WHERE clause that specifies the target rows of the query; for example, "DESCRIPTION = 'Insert Record #1'".</span></span> <span data-ttu-id="ac950-199">Puede establecer este parámetro en **null** para devolver todas las filas de destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-199">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="ac950-200">La operación de selección devuelve un conjunto de registros fuertemente tipada en función del tipo de fila del destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-200">The Select operation returns a strongly-typed record set based on the row type of the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac950-201">No hay ninguna compatibilidad de transmisión por secuencias para las operaciones básicas de SQL cuando se usa el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ac950-201">There is no streaming support for the basic SQL operations when you use the WCF service model.</span></span> <span data-ttu-id="ac950-202">Si la consulta devuelve un conjunto de registros de gran tamaño, puede mejorar el rendimiento mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="ac950-202">If your query returns a large record set, you might be able to improve performance by using the WCF channel model.</span></span> <span data-ttu-id="ac950-203">Para obtener más información, consulte [limitaciones de invocar las operaciones básicas de SQL mediante el modelo de servicio WCF](#BKMK_LimitationsInvoking).</span><span class="sxs-lookup"><span data-stu-id="ac950-203">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="ac950-204">El código siguiente muestra una operación de selección que tenga como destino de la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac950-204">The following code shows a Select operation that targets the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="ac950-205">Los registros devueltos se escriben en la consola.</span><span class="sxs-lookup"><span data-stu-id="ac950-205">The returned records are written to the console.</span></span>  
  
```  
// Declare a variable to hold the result set  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
  
// Select all records and write them to the console  
try  
{  
    selectRecords = aaTableClient.Select("*", null);  
}  
catch (Exception ex)  
{  
    // handle exception  
}  
  
Console.WriteLine("ACCOUNTACTIVITY before any operations");  
for (int i = 0; i \< selectRecords.Length; i++)  
{  
    Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", selectRecords[i].TID,  
    selectRecords[i].ACCOUNT,  
    selectRecords[i].AMOUNT,  
    selectRecords[i].TRANSDATE,  
    selectRecords[i].DESCRIPTION);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="ac950-206">Este código omite los pasos para crear, configurar y abra la instancia de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ac950-206">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="ac950-207">Para obtener un ejemplo que incluye estos pasos, consulte [operación Insert](#BKMK_InsertOperation).</span><span class="sxs-lookup"><span data-stu-id="ac950-207">For an example that includes these steps, see [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
### <a name="update-operation"></a><span data-ttu-id="ac950-208">La operación de actualización</span><span class="sxs-lookup"><span data-stu-id="ac950-208">Update Operation</span></span>  
 <span data-ttu-id="ac950-209">En la tabla siguiente se muestra los parámetros para la operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="ac950-209">The following table shows the parameters for the Update operation.</span></span>  
  
|<span data-ttu-id="ac950-210">CONJUNTO DE REGISTROS</span><span class="sxs-lookup"><span data-stu-id="ac950-210">RECORDSET</span></span>|<span data-ttu-id="ac950-211">FILTER</span><span class="sxs-lookup"><span data-stu-id="ac950-211">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="ac950-212">Un registro de plantilla fuertemente tipada en función del tipo de fila del destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-212">A strongly-typed template record based on the row type of the target.</span></span> <span data-ttu-id="ac950-213">El registro de plantilla especifica los valores de actualización para las filas de destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-213">The template record specifies the update values for the target rows.</span></span> <span data-ttu-id="ac950-214">Para las columnas de la fila nillable, puede especificar un valor null para indicar que no se debe actualizar la columna en las filas de destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-214">For nillable row columns, you can specify a null value to indicate that the column should not be updated in the target rows.</span></span>|<span data-ttu-id="ac950-215">El contenido de una cláusula WHERE de SQL que especifica las filas que se va a actualizarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-215">The contents of a SQL WHERE clause that specifies the rows to be updated in the target.</span></span> <span data-ttu-id="ac950-216">Por ejemplo, "descripción = 'Inserted Record #1'".</span><span class="sxs-lookup"><span data-stu-id="ac950-216">For example, "DESCRIPTION= 'Inserted Record #1'".</span></span>|  
  
 <span data-ttu-id="ac950-217">La operación de actualización devuelve el número de filas eliminadas del destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-217">The Update operation returns the number of rows deleted from the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac950-218">En el modelo de servicio WCF, el registro de plantilla que se usa en la operación de actualización está fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="ac950-218">In the WCF service model, the template record used in the Update operation is strongly-typed.</span></span> <span data-ttu-id="ac950-219">Si una columna es nillable, puede omitir la columna de la operación de actualización estableciendo su valor en **null** en el registro de plantilla; sin embargo, si una columna no es nillable, a continuación, debe establecer su valor en el registro de plantilla.</span><span class="sxs-lookup"><span data-stu-id="ac950-219">If a column is nillable, you can omit the column from the Update operation by setting its value to **null** in the template record; however, if a column is not nillable, then you must set its value in the template record.</span></span> <span data-ttu-id="ac950-220">Por ejemplo, si una columna es una clave principal, debe contener un valor.</span><span class="sxs-lookup"><span data-stu-id="ac950-220">For example, if a column is a primary key, it must contain a value.</span></span> <span data-ttu-id="ac950-221">Para obtener más información, consulte [limitaciones de invocar las operaciones básicas de SQL mediante el modelo de servicio WCF](#BKMK_LimitationsInvoking).</span><span class="sxs-lookup"><span data-stu-id="ac950-221">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="ac950-222">El código siguiente muestra una operación de actualización que tenga como destino de la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac950-222">The following code shows an Update operation that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
long recsUpdated;  
  
...  
  
// Create updated template. The TID, TIME, AMOUNT, and DESCRIPTION fields will be updated  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE updateRecord =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE();  
        updateRecord.TID = tidSequence.NextVal();  
        updateRecord.ACCOUNT = null;  
        updateRecord.AMOUNT = 300;  
        updateRecord.TRANSDATE = DateTime.Now.Date;  
        updateRecord.DESCRIPTION = "Updated Record #2";  
        updateRecord.PROCESSED = null;  
  
// Set filter string to specify the target record by using the DESCRIPTION field  
string filter = "DESCRIPTION = 'Inserted Record #2'";  
  
try  
{  
    recsUpdated = aaTableClient.Update(updateRecord, filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
    ...  
}  
  
Console.WriteLine("{0} records updated", recsUpdated);  
```  
  
> [!NOTE]
>  <span data-ttu-id="ac950-223">Este código omite los pasos para crear, configurar y abra la instancia de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ac950-223">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="ac950-224">Para obtener un ejemplo que incluye estos pasos, consulte [operación Insert](#BKMK_InsertOperation).</span><span class="sxs-lookup"><span data-stu-id="ac950-224">For an example that includes these steps, see [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
### <a name="delete-operation"></a><span data-ttu-id="ac950-225">Operación de eliminación</span><span class="sxs-lookup"><span data-stu-id="ac950-225">Delete Operation</span></span>  
 <span data-ttu-id="ac950-226">En la tabla siguiente se muestra los parámetros para la operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="ac950-226">The following table shows the parameters for the Delete operation.</span></span>  
  
|<span data-ttu-id="ac950-227">FILTER</span><span class="sxs-lookup"><span data-stu-id="ac950-227">FILTER</span></span>|  
|------------|  
|<span data-ttu-id="ac950-228">El contenido de una cláusula WHERE de SQL que especifica las filas que se van a eliminarse desde el destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-228">The contents of a SQL WHERE clause that specifies the rows to be deleted from the target.</span></span> <span data-ttu-id="ac950-229">Por ejemplo, "descripción = 'Inserted Record #1'".</span><span class="sxs-lookup"><span data-stu-id="ac950-229">For example, "DESCRIPTION= 'Inserted Record #1'".</span></span>|  
  
 <span data-ttu-id="ac950-230">La operación de eliminación, devuelve el número de filas eliminadas del destino.</span><span class="sxs-lookup"><span data-stu-id="ac950-230">The Delete operation returns the number of rows deleted from the target.</span></span> <span data-ttu-id="ac950-231">El código siguiente muestra una operación de eliminación que tenga como destino de la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac950-231">The following code shows a Delete operation that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
// Set filter string equal to the DESCRIPTION field of the target record  
string filter = "DESCRIPTION = 'Inserted Record #1'";  
  
try  
{  
    recsDeleted = aaTableClient.Delete(filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
  
    ...  
}  
Console.WriteLine("{0} records deleted", recsDeleted);  
```  
  
> [!NOTE]
>  <span data-ttu-id="ac950-232">Este código omite los pasos para crear, configurar y abra la instancia de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ac950-232">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="ac950-233">Para obtener un ejemplo que incluye estos pasos, consulte el [operación Insert](#BKMK_InsertOperation).</span><span class="sxs-lookup"><span data-stu-id="ac950-233">For an example that includes these steps, see the [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
##  <a name="BKMK_LimitationsInvoking"></a> <span data-ttu-id="ac950-234">Limitaciones de invocar las operaciones básicas de SQL mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="ac950-234">Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model</span></span>  
 <span data-ttu-id="ac950-235">Al invocar las operaciones básicas de SQL mediante el uso de un cliente de WCF, existen las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="ac950-235">The following limitations exist when you invoke the basic SQL operations by using a WCF client:</span></span>  
  
- <span data-ttu-id="ac950-236">**Operación de inserción.**</span><span class="sxs-lookup"><span data-stu-id="ac950-236">**Insert operation.**</span></span> <span data-ttu-id="ac950-237">El conjunto de registros que se usa en una operación de insertar varios registra está fuertemente tipada y, por tanto, incluye todas las columnas de fila.</span><span class="sxs-lookup"><span data-stu-id="ac950-237">The record set used in a multiple record Insert operation is strongly-typed and therefore includes all row columns.</span></span> <span data-ttu-id="ac950-238">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interpreta un valor null en un registro para indicar que la columna se debe excluir de la operación de inserción; sin embargo, no se puede excluir columnas que no sean nillable porque no se puede establecer en un valor null.</span><span class="sxs-lookup"><span data-stu-id="ac950-238">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a null value in a record to mean that the column should be excluded from the Insert operation; however, non-nillable columns cannot be excluded because you cannot set them to a null value.</span></span> <span data-ttu-id="ac950-239">Por lo tanto, debe especificar valores para las columnas que no sean nillable al realizar una operación de inserción varios registra.</span><span class="sxs-lookup"><span data-stu-id="ac950-239">Therefore, you must specify values for non-nillable columns when you perform a multiple record Insert operation.</span></span>  
  
- <span data-ttu-id="ac950-240">**Operación de inserción.**</span><span class="sxs-lookup"><span data-stu-id="ac950-240">**Insert operation.**</span></span> <span data-ttu-id="ac950-241">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interpreta un **DbNull** valor en una columna de datos nillable para indicar que la columna se debe excluir de una operación de inserción varios registra.</span><span class="sxs-lookup"><span data-stu-id="ac950-241">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a **DbNull** value in a nillable data column to mean that the column should be excluded from a multiple record Insert operation.</span></span> <span data-ttu-id="ac950-242">Esto significa que no se puede establecer una columna nillable **DbNull** operación de inserción en la base de datos de Oracle en un registro de varios.</span><span class="sxs-lookup"><span data-stu-id="ac950-242">This means that you cannot set a nillable column to **DbNull** on the Oracle database in a multiple record Insert operation.</span></span>  
  
- <span data-ttu-id="ac950-243">**Operación de inserción.**</span><span class="sxs-lookup"><span data-stu-id="ac950-243">**Insert operation.**</span></span> <span data-ttu-id="ac950-244">No hay ninguna compatibilidad de transmisión por secuencias para varias operaciones de inserción de registros que impliquen un gran conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="ac950-244">There is no streaming support for multiple record insert operations that involve a large record set.</span></span>  
  
- <span data-ttu-id="ac950-245">**La operación de actualización.**</span><span class="sxs-lookup"><span data-stu-id="ac950-245">**Update operation.**</span></span> <span data-ttu-id="ac950-246">El registro de plantilla que se usa en una operación de actualización está fuertemente tipada y, por tanto, incluye todas las columnas de fila.</span><span class="sxs-lookup"><span data-stu-id="ac950-246">The template record used in an Update operation is strongly-typed and therefore includes all row columns.</span></span> <span data-ttu-id="ac950-247">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interpreta un valor null en este registro para indicar que la columna se debe excluir de la operación de actualización; sin embargo, no se puede excluir columnas que no sean nillable porque no les puede en un valor null.</span><span class="sxs-lookup"><span data-stu-id="ac950-247">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a null value in this record to mean that the column should be excluded from the Update operation; however, non-nillable columns cannot be excluded because you cannot them to a null value.</span></span> <span data-ttu-id="ac950-248">Por lo tanto, debe especificar valores para las columnas que no sean nillable al realizar una operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="ac950-248">Therefore, you must specify values for non-nillable columns when you perform an Update operation.</span></span>  
  
- <span data-ttu-id="ac950-249">**La operación de actualización.**</span><span class="sxs-lookup"><span data-stu-id="ac950-249">**Update operation.**</span></span> <span data-ttu-id="ac950-250">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interpreta un **DbNull** valor en una columna de datos nillable en el registro de plantilla para indicar que la columna se debe excluir de la operación.</span><span class="sxs-lookup"><span data-stu-id="ac950-250">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a **DbNull** value in a nillable data column in the template record to mean that the column should be excluded from the operation.</span></span> <span data-ttu-id="ac950-251">Esto significa que no se puede establecer una columna nillable **DbNull** en la base de datos de Oracle mediante el uso de la operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="ac950-251">This means that you cannot set a nillable column to **DbNull** on the Oracle database by using the Update operation.</span></span>  
  
- <span data-ttu-id="ac950-252">**Operación de selección.**</span><span class="sxs-lookup"><span data-stu-id="ac950-252">**Select operation.**</span></span> <span data-ttu-id="ac950-253">No hay ninguna compatibilidad de transmisión por secuencias para consultas SELECT que devuelven un conjunto de registros de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="ac950-253">There is no streaming support for SELECT queries that return a large record set.</span></span>  
  
  <span data-ttu-id="ac950-254">Para escenarios donde estas limitaciones presentan desafíos, puede invocar la operación con el modelo del canal WCF porque:</span><span class="sxs-lookup"><span data-stu-id="ac950-254">For scenarios where these limitations present challenges, you can invoke the operation by using the WCF channel model because:</span></span>  
  
- <span data-ttu-id="ac950-255">Mediante el modelo de canal WCF, puede excluir columnas de datos específicos de las operaciones Update e Insert.</span><span class="sxs-lookup"><span data-stu-id="ac950-255">By using the WCF channel model, you can exclude specific data columns from Update and Insert operations.</span></span>  
  
- <span data-ttu-id="ac950-256">El modelo de canal WCF proporciona compatibilidad con streaming de nivel de nodo para las operaciones básicas de SQL que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone.</span><span class="sxs-lookup"><span data-stu-id="ac950-256">The WCF channel model provides node-level streaming support for the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes.</span></span>  
  
  <span data-ttu-id="ac950-257">Para obtener más información acerca de cómo utilizar el modelo de canal WCF con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [desarrollar Oracle base de datos de aplicaciones utilizando el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="ac950-257">For more information about using the WCF channel model with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Develop Oracle Database Applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac950-258">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac950-258">See Also</span></span>  
 [<span data-ttu-id="ac950-259">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="ac950-259">Develop Oracle Database Applications Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)