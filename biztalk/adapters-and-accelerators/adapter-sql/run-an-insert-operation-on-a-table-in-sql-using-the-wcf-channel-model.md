---
title: Ejecutar una operación de inserción en una tabla en SQL mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3df95d78-3a9c-48c0-81ab-1f3206c5e3f7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bceb236b660b80c1e46cb0410d799d994516c40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224412"
---
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a><span data-ttu-id="a3725-102">Ejecutar una operación de inserción en una tabla en SQL mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="a3725-102">Run an Insert Operation on a Table in SQL using the WCF Channel Model</span></span>
<span data-ttu-id="a3725-103">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta un conjunto de operaciones básicas de Insert, Select, Update y Delete en vistas y tablas de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3725-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on SQL Server database tables and views.</span></span> <span data-ttu-id="a3725-104">Mediante el uso de estas operaciones, puede realizar simple SQL Insert, Select, Update y eliminar instrucciones que califican Where cláusula en una tabla de destino o la vista.</span><span class="sxs-lookup"><span data-stu-id="a3725-104">By using these operations, you can perform simple SQL Insert, Select, Update, and Delete statements qualified by a Where clause on a target table or view.</span></span> <span data-ttu-id="a3725-105">Este tema proporciona instrucciones sobre cómo realizar una operación de inserción en una tabla de base de datos de SQL Server mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="a3725-105">This topic provides instructions on how to perform an Insert operation on a SQL Server database table using the WCF channel model.</span></span>  
  
 <span data-ttu-id="a3725-106">Para obtener más información sobre cómo el adaptador es compatible con estas operaciones, vea [Insert, Update, Delete y seleccione las operaciones en tablas y vistas con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a3725-106">For more information on how the adapter supports these operations, see [Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span></span> <span data-ttu-id="a3725-107">Para obtener más información acerca de cómo realizar operaciones en SQL Server con el modelo del canal de WCF, vea [información general del modelo del canal WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a3725-107">For more information about how to perform operations on SQL Server using the WCF Channel model, see [Overview of the WCF channel model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="a3725-108">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="a3725-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="a3725-109">El ejemplo de este tema realiza operaciones en la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="a3725-109">The example in this topic performs operations on the Employee table.</span></span> <span data-ttu-id="a3725-110">La tabla de empleados se crea al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a3725-110">The Employee table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="a3725-111">Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a3725-111">For more information about samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="a3725-112">Obtener un ejemplo, **EmployeeInsertOp**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a3725-112">A sample, **EmployeeInsertOp**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="a3725-113">El mensaje de inserción</span><span class="sxs-lookup"><span data-stu-id="a3725-113">The Insert Message</span></span>  
 <span data-ttu-id="a3725-114">Para realizar operaciones en la base de datos de SQL Server mediante el modelo de canal WCF, debe tener el mensaje de solicitud específico de la operación.</span><span class="sxs-lookup"><span data-stu-id="a3725-114">To perform operations on the SQL Server database using the WCF channel model, you must have the request message specific to the operation.</span></span> <span data-ttu-id="a3725-115">El mensaje de solicitud para realizar una operación de inserción en la tabla de empleados en la base de datos de SQL Server es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3725-115">The request message to perform an Insert operation on the Employee table in the SQL Server database resembles the following:</span></span>  
  
```  
<Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Rows>  
    <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
      <Name>Tom Smith</Name>  
      <Designation>Manager</Designation>  
      <Salary>500000</Salary>  
   </Employee>  
  </Rows>  
</Insert>  
```  
  
 <span data-ttu-id="a3725-116">Este mensaje de solicitud inserta un registro con los detalles siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3725-116">This request message inserts a record with following details:</span></span>  
  
```  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 <span data-ttu-id="a3725-117">Debe copiar el mensaje a un archivo, por ejemplo, InsertRequest.xml.</span><span class="sxs-lookup"><span data-stu-id="a3725-117">You must copy the message to a file, e.g. InsertRequest.xml.</span></span> <span data-ttu-id="a3725-118">Este archivo se usa en este ejemplo para enviar el mensaje de solicitud a SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3725-118">This file is used in this example to send the request message to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="a3725-119">Para obtener más información acerca del esquema de mensaje para las operaciones en la tabla, vea [esquemas de mensaje para Insert, Update, Delete y seleccione las operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span><span class="sxs-lookup"><span data-stu-id="a3725-119">For more information about the message schema for operations on table, see [Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
## <a name="creating-a-wcf-channel-application"></a><span data-ttu-id="a3725-120">Crear una aplicación de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="a3725-120">Creating a WCF Channel Application</span></span>  
 <span data-ttu-id="a3725-121">Esta sección proporciona instrucciones sobre cómo crear una aplicación de canal WCF para realizar una operación de inserción en la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="a3725-121">This section provides instructions on how to create a WCF channel application to perform an Insert operation on the Employee table.</span></span>  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a><span data-ttu-id="a3725-122">Para crear una aplicación de canal WCF para insertar registros en la tabla de empleados</span><span class="sxs-lookup"><span data-stu-id="a3725-122">To create a WCF channel application for inserting records into the Employee table</span></span>  
  
1.  <span data-ttu-id="a3725-123">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a3725-123">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="a3725-124">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="a3725-124">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="a3725-125">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="a3725-125">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="a3725-126">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3725-126">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="a3725-127">Crear el enlace y el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a3725-127">Create the binding and endpoint.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
    ```  
  
5.  <span data-ttu-id="a3725-128">Cree y abra el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="a3725-128">Create and open the channel factory.</span></span> <span data-ttu-id="a3725-129">Esta aplicación envía el mensaje de solicitud a SQL Server y recibe una respuesta, por lo tanto, debe implementar la interfaz IRequestChannel.</span><span class="sxs-lookup"><span data-stu-id="a3725-129">This application sends request message to SQL Server and receives a response, hence you must implement the IRequestChannel interface.</span></span>  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
6.  <span data-ttu-id="a3725-130">Crear y abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="a3725-130">Create and open the channel.</span></span>  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
7.  <span data-ttu-id="a3725-131">Crear y enviar el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="a3725-131">Create and send the request message.</span></span>  
  
    ```  
    XmlReader readerIn;  
    Console.WriteLine("Creating the message");  
    try  
    {  
       readerIn = XmlReader.Create("InsertRequest.xml");  
       Console.WriteLine("Reader created");  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Message messageIn = Message.CreateMessage(MessageVersion.Default, "TableOp/Insert/dbo/Employee", readerIn);  
    Message messageOut = channel.Request(messageIn);  
  
    ```  
  
     <span data-ttu-id="a3725-132">Al crear el mensaje de solicitud, debe especificar la acción de mensaje que indica la acción que realiza el adaptador en la tabla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3725-132">While creating the request message, you must specify the message action that indicates the action that the adapter performs on the SQL Server table.</span></span> <span data-ttu-id="a3725-133">Para llevar a cabo una operación de inserción en la tabla Employee, la acción de mensaje es `TableOp/Insert/dbo/Employee`.</span><span class="sxs-lookup"><span data-stu-id="a3725-133">To perform an Insert operation on the Employee table, the message action is `TableOp/Insert/dbo/Employee`.</span></span> <span data-ttu-id="a3725-134">Para obtener información acerca de cómo se puede determinar la acción de mensaje para realizar diversas operaciones en tablas, vea [esquemas de mensaje para Insert, Update, Delete y seleccione las operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span><span class="sxs-lookup"><span data-stu-id="a3725-134">For information about how you can determine the message action for various operations on tables, see [Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
8.  <span data-ttu-id="a3725-135">Obtiene el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a3725-135">Get the response message.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
9. <span data-ttu-id="a3725-136">Cierre el mensaje, el canal y el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="a3725-136">Close the message, channel, and channel factory.</span></span>  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
10. <span data-ttu-id="a3725-137">Generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a3725-137">Build the project.</span></span> <span data-ttu-id="a3725-138">Después de compilar el proyecto, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a3725-138">After building the project, you must perform the following tasks:</span></span>  
  
    -   <span data-ttu-id="a3725-139">Copie el mensaje de solicitud, InsertRequest.xml, en la misma ubicación que el proyecto ejecutable.</span><span class="sxs-lookup"><span data-stu-id="a3725-139">Copy the request message, InsertRequest.xml, at the same location as your project executable.</span></span> <span data-ttu-id="a3725-140">Normalmente, esta ubicación es \bin\Debug\ en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a3725-140">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
    -   <span data-ttu-id="a3725-141">La tabla "Employee" utilizada en este ejemplo tiene una columna de tipo definido por el usuario Point (UDT).</span><span class="sxs-lookup"><span data-stu-id="a3725-141">The "Employee" table used in this example has a column of Point user-defined type (UDT).</span></span> <span data-ttu-id="a3725-142">Por lo tanto, antes de ejecutar el proyecto, debe crear el ensamblado para el UDT Point tal y como se describe en [crear tipos](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="a3725-142">So, before running the project, you must create the assembly for the Point UDT as described at [Creating User-Defined Types](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types).</span></span> <span data-ttu-id="a3725-143">También debe copiar la DLL en la misma ubicación que el proyecto ejecutable del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a3725-143">You must also copy the assembly DLL at the same location as the project executable.</span></span> <span data-ttu-id="a3725-144">Normalmente, esta ubicación es \bin\Debug\ en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a3725-144">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
11. <span data-ttu-id="a3725-145">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3725-145">Run the application.</span></span> <span data-ttu-id="a3725-146">El mensaje de respuesta, Response.xml, se guarda en la ubicación especificada en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3725-146">The response message, Response.xml, is saved at the location you specified in the application.</span></span> <span data-ttu-id="a3725-147">El mensaje de respuesta contiene el identificador del empleado recién agregado y es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3725-147">The response message contains the ID of the newly added employee and resembles the following:</span></span>  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     <span data-ttu-id="a3725-148">Dado que la tabla Employee tiene la columna Id_Empleado como la columna de identidad, la operación de inserción devuelve el valor de la columna de identidad del registro recién insertado.</span><span class="sxs-lookup"><span data-stu-id="a3725-148">Because the Employee table has the Employee_ID column as the identity column, the Insert operation returns the value for the identity column of the newly inserted record.</span></span> <span data-ttu-id="a3725-149">Si no hay ninguna columna de identidad en una tabla, el valor devuelto es NULL.</span><span class="sxs-lookup"><span data-stu-id="a3725-149">If there is no identity column in a table, the return value is NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3725-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3725-150">See Also</span></span>  
[<span data-ttu-id="a3725-151">Desarrollar aplicaciones de SQL mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="a3725-151">Develop SQL applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)