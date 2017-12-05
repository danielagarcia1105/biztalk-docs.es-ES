---
title: Ejecutar operaciones en tablas y vistas con los tipos de datos grandes en SQL mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d33e17c-e09e-4a57-9acc-43095e67ed8c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1da0def828c1dbfa8511dc61b529fa02cb53ca5a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="e52e5-102">Ejecutar operaciones en tablas y vistas con los tipos de datos grandes en SQL mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="e52e5-102">Run Operations on Tables and Views with Large Data Types in SQL using the WCF Service Model</span></span>
<span data-ttu-id="e52e5-103">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes de adaptador para leer y actualizar datos en columnas de tipos de datos de gran tamaño, es decir, varchar (max), nvarchar (max) o varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="e52e5-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to read and update data in columns of large data types, that is, varchar(max), nvarchar(max), or varbinary(max).</span></span> <span data-ttu-id="e52e5-104">Para leer datos de esas columnas, los clientes de adaptador pueden usar la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="e52e5-104">To read data from such columns, adapter clients can use the Select operation.</span></span> <span data-ttu-id="e52e5-105">Para insertar o actualizar datos en estas columnas, el adaptador expone un conjunto\<*column_name* \> operación, donde \< *column_name* \> es el nombre de la columna de tipo varchar (max), nvarchar (max) o varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="e52e5-105">To insert or update data into such columns, the adapter exposes a Set\<*column_name*\> operation, where \<*column_name*\> is the name of the column of type varchar(max), nvarchar(max), or varbinary(max).</span></span>  
  
 <span data-ttu-id="e52e5-106">Además, en SQL Server, puede tener la columna varbinay(max) almacenar datos no estructurados, como documentos de texto e imágenes.</span><span class="sxs-lookup"><span data-stu-id="e52e5-106">Additionally, in SQL Server, you can have the varbinay(max) column store unstructured data such as text documents and images.</span></span> <span data-ttu-id="e52e5-107">Los datos no estructurados se denominan datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e52e5-107">Such unstructured data is called FILESTREAM data.</span></span> <span data-ttu-id="e52e5-108">Los datos de FILESTREAM se pueden almacenar como archivos en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="e52e5-108">FILESTREAM data can be stored as files on the file system.</span></span> <span data-ttu-id="e52e5-109">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite al cliente especificar datos FILESTREAM en columnas de tipo varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="e52e5-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables the client to enter FILESTREAM data into columns of type varbinary(max).</span></span> <span data-ttu-id="e52e5-110">[Almacenamiento de FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server) se proporciona más información.</span><span class="sxs-lookup"><span data-stu-id="e52e5-110">[FILESTREAM storage](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server) has more information.</span></span> 
  
 <span data-ttu-id="e52e5-111">Este tema proporciona información acerca de ciertas tareas que debe realizar en el equipo que ejecuta SQL Server y el equipo que ejecuta el cliente de adaptador para que pueda insertar o actualizar los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e52e5-111">This topic provides information about certain tasks you must perform on the computer running SQL Server and the computer running the adapter client to be able to insert or update FILESTREAM data.</span></span> <span data-ttu-id="e52e5-112">Este tema también proporciona instrucciones acerca de cómo realizar conjunto\<*column_name* \> operaciones para insertar datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e52e5-112">This topic also provides instructions on performing Set\<*column_name*\> operations to insert FILESTREAM data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e52e5-113">Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e52e5-113">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e52e5-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e52e5-114">Prerequisites</span></span>  
 <span data-ttu-id="e52e5-115">Debe realizar las siguientes tareas en el equipo que ejecuta SQL Server y el equipo que ejecuta al cliente de adaptador.</span><span class="sxs-lookup"><span data-stu-id="e52e5-115">You must perform the following tasks on the computer running SQL Server and the computer running the adapter client.</span></span>  
  
-   <span data-ttu-id="e52e5-116">**En el equipo que ejecuta SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e52e5-116">**On the computer running SQL Server**</span></span>  
  
    -   <span data-ttu-id="e52e5-117">Debe habilitar FILESTREAM en la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e52e5-117">You must enable FILESTREAM on the SQL Server instance.</span></span> <span data-ttu-id="e52e5-118">Vea [habilitar y configurar FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream).</span><span class="sxs-lookup"><span data-stu-id="e52e5-118">See [Enable and Configure FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream).</span></span>
  
    -   <span data-ttu-id="e52e5-119">Debe crear una base de datos habilitada para FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e52e5-119">You must create a FILESTREAM-enabled database.</span></span> <span data-ttu-id="e52e5-120">Vea [crear una base de datos habilitada para FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database).</span><span class="sxs-lookup"><span data-stu-id="e52e5-120">See [Create a FILESTREAM-Enabled Database](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database).</span></span>
  
    -   <span data-ttu-id="e52e5-121">Debe tener una tabla para almacenar datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e52e5-121">You must have a table for storing FILESTREAM data.</span></span> <span data-ttu-id="e52e5-122">Vea [crear una tabla para almacenar datos FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data),</span><span class="sxs-lookup"><span data-stu-id="e52e5-122">See [Create a Table for Storing FILESTREAM Data](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data),</span></span>
  
-   <span data-ttu-id="e52e5-123">**En el equipo que ejecuta al cliente de adaptador**</span><span class="sxs-lookup"><span data-stu-id="e52e5-123">**On the computer running the adapter client**</span></span>  
  
    -   <span data-ttu-id="e52e5-124">Debe tener instalado el SDK de conectividad de cliente de SQL.</span><span class="sxs-lookup"><span data-stu-id="e52e5-124">You must have the SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="e52e5-125">Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccionar **SDK de conectividad de cliente de SQL** en el **selección de características** página del asistente.</span><span class="sxs-lookup"><span data-stu-id="e52e5-125">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="e52e5-126">El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e52e5-126">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
 <span data-ttu-id="e52e5-127">Después de completar estas tareas, está preparado para insertar o actualizar los datos FILESTREAM en tablas de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e52e5-127">After you have completed these tasks, you are all set to insert or update FILESTREAM data in SQL Server database tables.</span></span>  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a><span data-ttu-id="e52e5-128">Cómo en este tema muestra las operaciones en tipos de datos de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="e52e5-128">How This Topic Demonstrates Operations on Large Data Types</span></span>  
 <span data-ttu-id="e52e5-129">Para demostrar cómo realizar conjunto\<*column_name* \> operaciones en tablas con tipos de datos de gran tamaño, usan una tabla, **registros**, que tiene columnas **deId.** y **documento**:</span><span class="sxs-lookup"><span data-stu-id="e52e5-129">To demonstrate how to perform Set\<*column_name*\> operations on tables with large data types, take a table, **Records**, that has columns **Id** and **Document**:</span></span>  
  
-   <span data-ttu-id="e52e5-130">El **registros** tabla, con todos los datos, se crea al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e52e5-130">The **Records** table, with all the data, is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="e52e5-131">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e52e5-131">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
-   <span data-ttu-id="e52e5-132">El **identificador** columna es de tipo uniqueidentifier y toma un GUID.</span><span class="sxs-lookup"><span data-stu-id="e52e5-132">The **Id** column is of type uniqueidentifier and takes a GUID.</span></span> <span data-ttu-id="e52e5-133">Se asume que el **identificador** columna ya tiene un GUID '`438B7B4C-5491-409F-BCC1-78817C399EC3`'.</span><span class="sxs-lookup"><span data-stu-id="e52e5-133">Assume that the **Id** column already has a GUID ‘`438B7B4C-5491-409F-BCC1-78817C399EC3`’.</span></span>  
  
-   <span data-ttu-id="e52e5-134">El **documento** columna es de tipo varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="e52e5-134">The **Document** column is of type VARBINARY(MAX).</span></span> <span data-ttu-id="e52e5-135">Para actualizar la **documento** columna, el adaptador expone la **SetDocument** operación.</span><span class="sxs-lookup"><span data-stu-id="e52e5-135">To update the **Document** column, the adapter exposes the **SetDocument** operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e52e5-136">Para SQL Server, para demostrar operaciones de FILESTREAM, se asume que el **documento** columna puede almacenar datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e52e5-136">For SQL Server, to demonstrate FILESTREAM operations, assume that the **Document** column can store FILESTREAM data.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e52e5-137">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="e52e5-137">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e52e5-138">El ejemplo de este tema realiza operaciones en el **registros** tabla.</span><span class="sxs-lookup"><span data-stu-id="e52e5-138">The example in this topic performs operations on the **Records** table.</span></span> <span data-ttu-id="e52e5-139">El **registros** tabla se crea al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e52e5-139">The **Records** table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="e52e5-140">Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e52e5-140">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="e52e5-141">Obtener un ejemplo, **Records_FILESTREAM_Op**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e52e5-141">A sample, **Records_FILESTREAM_Op**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="e52e5-142">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="e52e5-142">The WCF Client Class</span></span>  
 <span data-ttu-id="e52e5-143">El nombre del cliente WCF generado para las operaciones en datos de gran tamaño de los tipos que la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta, se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e52e5-143">The name of the WCF client generated for the operations on large data types that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers, is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="e52e5-144">Artefactos de base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="e52e5-144">SQL Server Database Artifact</span></span>|<span data-ttu-id="e52e5-145">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="e52e5-145">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="e52e5-146">Tabla</span><span class="sxs-lookup"><span data-stu-id="e52e5-146">Table</span></span>|<span data-ttu-id="e52e5-147">Cliente de TableOp_ [esquema] _ [NombreTabla]</span><span class="sxs-lookup"><span data-stu-id="e52e5-147">TableOp_[Schema]_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="e52e5-148">Ver</span><span class="sxs-lookup"><span data-stu-id="e52e5-148">View</span></span>|<span data-ttu-id="e52e5-149">Cliente de ViewOp_ [esquema] _ [VIEW_NAME]</span><span class="sxs-lookup"><span data-stu-id="e52e5-149">ViewOp_[Schema]_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="e52e5-150">[Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.</span><span class="sxs-lookup"><span data-stu-id="e52e5-150">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a><span data-ttu-id="e52e5-151">Firma de método para llamar a operaciones en las columnas de tipos de datos de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="e52e5-151">Method Signature for Invoking Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="e52e5-152">La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla.</span><span class="sxs-lookup"><span data-stu-id="e52e5-152">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="e52e5-153">Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e52e5-153">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="e52e5-154">Operación</span><span class="sxs-lookup"><span data-stu-id="e52e5-154">Operation</span></span>|<span data-ttu-id="e52e5-155">Firma de método</span><span class="sxs-lookup"><span data-stu-id="e52e5-155">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="e52e5-156">Establecer\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="e52e5-156">Set\<*column_name*\></span></span>|<span data-ttu-id="e52e5-157">Set void público\<*column_name*\>(cadena de filtro, byte [] datos;)</span><span class="sxs-lookup"><span data-stu-id="e52e5-157">public void Set\<*column_name*\>(string Filter, byte[] Data);</span></span>|  
  
 <span data-ttu-id="e52e5-158">\<*column_name* \> = nombre de la columna de tipo de datos de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e52e5-158">\<*column_name*\> = Name of the column of large data type.</span></span>  
  
 <span data-ttu-id="e52e5-159">Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **SetDocument** operación en el **registros** tabla en el esquema predeterminado de "dbo".</span><span class="sxs-lookup"><span data-stu-id="e52e5-159">As an example, the following code shows the method signatures for a WCF client class generated for the **SetDocument** operation on the **Records** table under the default “dbo” schema.</span></span>  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 <span data-ttu-id="e52e5-160">En este fragmento de código, **TableOp_dbo_RecordsClient** es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e52e5-160">In this snippet, **TableOp_dbo_RecordsClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a><span data-ttu-id="e52e5-161">Parámetros para las operaciones en las columnas de tipos de datos de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="e52e5-161">Parameters for Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="e52e5-162">Esta sección proporciona los parámetros requeridos por el conjunto de\<*column_name* \> operación.</span><span class="sxs-lookup"><span data-stu-id="e52e5-162">This section provides the parameters required by the Set\<*column_name*\> operation.</span></span>  
  
|<span data-ttu-id="e52e5-163">Nombre del parámetro</span><span class="sxs-lookup"><span data-stu-id="e52e5-163">Parameter name</span></span>|<span data-ttu-id="e52e5-164">Description</span><span class="sxs-lookup"><span data-stu-id="e52e5-164">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e52e5-165">cadena de filtro</span><span class="sxs-lookup"><span data-stu-id="e52e5-165">string Filter</span></span>|<span data-ttu-id="e52e5-166">Especifica la cláusula WHERE basada en el que el adaptador actualiza el registro de la columna de tipo de datos de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e52e5-166">Specifies the WHERE clause based on which the adapter updates the record for the column of large data type.</span></span>|  
|<span data-ttu-id="e52e5-167">Byte [] datos</span><span class="sxs-lookup"><span data-stu-id="e52e5-167">byte[] Data</span></span>|<span data-ttu-id="e52e5-168">Especifica el valor que se debe actualizar para la columna de tipo de datos de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e52e5-168">Specifies the value that must be updated for the column of large data type.</span></span>|  
  
 <span data-ttu-id="e52e5-169">El conjunto de\<*column_name* \> operación no devuelve ningún valor.</span><span class="sxs-lookup"><span data-stu-id="e52e5-169">The Set\<*column_name*\> operation does not return any values.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a><span data-ttu-id="e52e5-170">Creación de un cliente WCF para invocar operaciones en las columnas de tipos de datos de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="e52e5-170">Creating a WCF Client to Invoke Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="e52e5-171">El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e52e5-171">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="e52e5-172">Esta sección describe cómo crear un cliente WCF para invocar la **SetDocument** operación en el **registros** tabla.</span><span class="sxs-lookup"><span data-stu-id="e52e5-172">This section describes how to create a WCF client to invoke the **SetDocument** operation on the **Records** table.</span></span> <span data-ttu-id="e52e5-173">El adaptador expone la **SetDocument** operación para actualizar los datos en columnas de tipos de datos de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e52e5-173">The adapter exposes the **SetDocument** operation to update data in columns of large data types.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="e52e5-174">Para crear a un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="e52e5-174">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="e52e5-175">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e52e5-175">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="e52e5-176">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="e52e5-176">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="e52e5-177">Generar la clase de cliente WCF para la **SetDocument** operación en el **registros** tabla.</span><span class="sxs-lookup"><span data-stu-id="e52e5-177">Generate the WCF client class for the **SetDocument** operation on the **Records** table.</span></span> <span data-ttu-id="e52e5-178">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="e52e5-178">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3.  <span data-ttu-id="e52e5-179">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, y `System.Transactions`.</span><span class="sxs-lookup"><span data-stu-id="e52e5-179">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, and `System.Transactions`.</span></span>  
  
4.  <span data-ttu-id="e52e5-180">Abra el archivo Program.cs y agregue el `System.Transactions` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e52e5-180">Open the Program.cs file and add the `System.Transactions` namespace.</span></span>  
  
5.  <span data-ttu-id="e52e5-181">En Program.cs, cree a un cliente tal y como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="e52e5-181">In the Program.cs, create a client as described in the snippet below.</span></span>  
  
    ```  
  
              TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
    client.ClientCredentials.UserName.UserName = "";  
    client.ClientCredentials.UserName.Password = "";  
  
    ```  
  
     <span data-ttu-id="e52e5-182">En este fragmento de código, `TableOp_dbo_RecordsClient` es el cliente WCF definido en SqlAdapterBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="e52e5-182">In this snippet, `TableOp_dbo_RecordsClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="e52e5-183">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e52e5-183">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="e52e5-184">`SqlAdapterBinding_TableOp_dbo_Records`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="e52e5-184">`SqlAdapterBinding_TableOp_dbo_Records` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e52e5-185">Para llevar a cabo operaciones en los datos FILESTREAM, siempre debe conectarse a SQL Server mediante autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e52e5-185">To perform operations on FILESTREAM data, you must always connect to SQL Server using Windows authentication.</span></span> <span data-ttu-id="e52e5-186">Para conectarse mediante la autenticación de Windows, debe proporcionar un nombre de usuario vacío y una contraseña, tal y como se muestra en el fragmento de código anterior.</span><span class="sxs-lookup"><span data-stu-id="e52e5-186">To connect using Windows authentication, you must provide empty username and password, as shown in the preceding snippet.</span></span> <span data-ttu-id="e52e5-187">Además, antes de usar la autenticación de Windows para conectarse a SQL Server, debe haber realizado los pasos mencionados en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e52e5-187">Also, before using Windows authentication to connect to SQL Server, you must have performed the steps mentioned in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e52e5-188">En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e52e5-188">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="e52e5-189">Puede especificar también explícitamente estos valores en el código.</span><span class="sxs-lookup"><span data-stu-id="e52e5-189">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="e52e5-190">Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e52e5-190">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
6.  <span data-ttu-id="e52e5-191">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="e52e5-191">Open the client as described in the snippet below:</span></span>  
  
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
  
7.  <span data-ttu-id="e52e5-192">Invocar la **SetDocument** operación en el **registros** tabla.</span><span class="sxs-lookup"><span data-stu-id="e52e5-192">Invoke the **SetDocument** operation on the **Records** table.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e52e5-193">El conjunto de*< column_name >* siempre se deben realizar las operaciones en una transacción.</span><span class="sxs-lookup"><span data-stu-id="e52e5-193">The Set*<column_name>* operations must always be performed in a transaction.</span></span> <span data-ttu-id="e52e5-194">Para asegurarse de esto, el conjunto de*< column_name >* se debe invocar la operación dentro de un ámbito de transacción y el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **true**en el archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="e52e5-194">To ensure this, the Set*<column_name>* operation must be invoked within a transaction scope and the **UseAmbientTransaction** binding property must be set to **true** in the app.config.</span></span>  
  
    ```  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
        byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
        client.SetDocument(filter, data);  
        tx.Complete();  
    }  
    ```  
  
     <span data-ttu-id="e52e5-195">En este caso, la aplicación convierte la cadena "Datos de ejemplo" en una cadena codificada en base64 y se actualiza en el registro que satisface los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="e52e5-195">Here, the application converts the string “Sample data” into a base64 encoded string, and updates it in the record that satisfies the filter criteria.</span></span>  
  
8.  <span data-ttu-id="e52e5-196">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="e52e5-196">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
9. <span data-ttu-id="e52e5-197">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="e52e5-197">Build the project and then run it.</span></span> <span data-ttu-id="e52e5-198">Las actualizaciones de la aplicación la **documento** columna en el **registros** tabla.</span><span class="sxs-lookup"><span data-stu-id="e52e5-198">The application updates the **Document** column in the **Records** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e52e5-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="e52e5-199">See Also</span></span>  
[<span data-ttu-id="e52e5-200">Desarrollar aplicaciones con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="e52e5-200">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)