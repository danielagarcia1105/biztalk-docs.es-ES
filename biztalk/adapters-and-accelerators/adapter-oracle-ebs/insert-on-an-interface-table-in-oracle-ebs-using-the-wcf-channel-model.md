---
title: "Ejecutar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el modelo de canal WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a2e5ee3-552b-40a2-aaa6-5391347f1146
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703b00adeb373fe66c4a96c324f13f9c3c5ec655
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a><span data-ttu-id="e9c34-102">Ejecutar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="e9c34-102">Run an insert operation on an interface table in Oracle E-Business Suite using the WCF channel model</span></span>
<span data-ttu-id="e9c34-103">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] detecta un conjunto de operaciones Insert, Select, Update y Delete en tablas de la interfaz de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="e9c34-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of Insert, Select, Update, and Delete operations on Oracle E-Business Suite interface tables.</span></span> <span data-ttu-id="e9c34-104">Mediante el uso de estas operaciones, puede realizar simple Insert, Select, Update y eliminar instrucciones que califican Where cláusula en una tabla de la interfaz de destino.</span><span class="sxs-lookup"><span data-stu-id="e9c34-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a Where clause on a target interface table.</span></span> <span data-ttu-id="e9c34-105">Este tema proporciona instrucciones sobre cómo realizar una operación de inserción en una tabla de interfaz mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="e9c34-105">This topic provides instructions on how to perform an Insert operation on an interface table using the WCF channel model.</span></span>  
  
 <span data-ttu-id="e9c34-106">Para obtener más información sobre cómo el adaptador es compatible con estas operaciones, vea [operaciones en tablas de interfaz y vistas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span><span class="sxs-lookup"><span data-stu-id="e9c34-106">For more information on how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span> <span data-ttu-id="e9c34-107">Para obtener más información acerca de cómo realizar operaciones en Oracle E-Business Suite utilizando el modelo del canal de WCF, vea [información general del modelo del canal WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e9c34-107">For more information about how to perform operations on Oracle E-Business Suite using the WCF Channel model, see [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e9c34-108">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="e9c34-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e9c34-109">El ejemplo de este tema realiza operaciones en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e9c34-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="e9c34-110">La tabla se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e9c34-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="e9c34-111">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e9c34-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="e9c34-112">Obtener un ejemplo, **InsertOperation**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e9c34-112">A sample, **InsertOperation**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="e9c34-113">El mensaje de inserción</span><span class="sxs-lookup"><span data-stu-id="e9c34-113">The Insert Message</span></span>  
 <span data-ttu-id="e9c34-114">Para llevar a cabo operaciones en Oracle E-Business Suite mediante el modelo de canal WCF, debe tener el mensaje de solicitud específico de la operación.</span><span class="sxs-lookup"><span data-stu-id="e9c34-114">To perform operations on the Oracle E-Business Suite using the WCF channel model, you must have the request message specific to the operation.</span></span> <span data-ttu-id="e9c34-115">El mensaje de solicitud para realizar una operación de inserción en la tabla de interfaz MS_SAMPLE_EMPLOYEE es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9c34-115">The request message to perform an Insert operation on the MS_SAMPLE_EMPLOYEE interface table resembles the following:</span></span>  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">  
      <EMP_NO>10050</EMP_NO>  
      <NAME>John Smith</NAME>  
      <DESIGNATION>Manager</DESIGNATION>  
      <SALARY>500000</SALARY>  
      <JOIN_DATE>1999-05-31</JOIN_DATE>  
    </InsertRecord>  
  </RECORDSET>  
</Insert>  
```  
  
 <span data-ttu-id="e9c34-116">Este mensaje de solicitud inserta un registro con los detalles siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9c34-116">This request message inserts a record with following details:</span></span>  
  
```  
Employee Number = 10050  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 <span data-ttu-id="e9c34-117">Debe copiar el mensaje a un archivo, por ejemplo, InsertRequest.xml.</span><span class="sxs-lookup"><span data-stu-id="e9c34-117">You must copy the message to a file, e.g. InsertRequest.xml.</span></span> <span data-ttu-id="e9c34-118">Este archivo se usa en este ejemplo para enviar el mensaje de solicitud a Oracle E-Business Suite mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9c34-118">This file is used in this example to send the request message to Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="e9c34-119">Para obtener más información acerca del esquema de mensaje para las operaciones en la tabla, vea [esquemas de mensaje para Insert, Update, Delete y las operaciones de Select](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e9c34-119">For more information about the message schema for operations on table, see [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
## <a name="creating-a-wcf-channel-application"></a><span data-ttu-id="e9c34-120">Crear una aplicación de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e9c34-120">Creating a WCF Channel Application</span></span>  
 <span data-ttu-id="e9c34-121">Esta sección proporciona instrucciones sobre cómo crear una aplicación de canal WCF para realizar una operación de inserción en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e9c34-121">This section provides instructions on how to create a WCF channel application to perform an Insert operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a><span data-ttu-id="e9c34-122">Para crear una aplicación de canal WCF para insertar registros en la tabla</span><span class="sxs-lookup"><span data-stu-id="e9c34-122">To create a WCF channel application for inserting records into the table</span></span>  
  
1.  <span data-ttu-id="e9c34-123">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e9c34-123">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="e9c34-124">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="e9c34-124">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="e9c34-125">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="e9c34-125">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="e9c34-126">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9c34-126">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="e9c34-127">Crear el enlace y el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e9c34-127">Create the binding and endpoint.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
  
    ```  
  
5.  <span data-ttu-id="e9c34-128">Dado que está realizando una operación en una tabla de interfaz, debe establecer el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9c34-128">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="e9c34-129">En este ejemplo, para establecer el contexto de la aplicación, especifique la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="e9c34-129">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="e9c34-130">Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="e9c34-130">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  <span data-ttu-id="e9c34-131">Cree y abra el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="e9c34-131">Create and open the channel factory.</span></span> <span data-ttu-id="e9c34-132">Esta aplicación envía el mensaje de solicitud para Oracle E-Business Suite y recibe una respuesta, por lo tanto, debe implementar la interfaz IRequestChannel.</span><span class="sxs-lookup"><span data-stu-id="e9c34-132">This application sends request message to Oracle E-Business Suite and receives a response, hence you must implement the IRequestChannel interface.</span></span>  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
7.  <span data-ttu-id="e9c34-133">Crear y abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="e9c34-133">Create and open the channel.</span></span>  
  
    ```  
    IRequestChannel channel;  
    try  
    {  
       channel = factory.CreateChannel();  
       channel.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception :" + ex.Message);  
       throw;  
    }  
    ```  
  
8.  <span data-ttu-id="e9c34-134">Crear y enviar el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="e9c34-134">Create and send the request message.</span></span>  
  
    ```  
    XmlReader readerIn;  
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
    Message messageIn;  
    Message messageOut;  
    try  
    {  
       messageIn = Message.CreateMessage(MessageVersion.Default, "InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE", readerIn);  
       messageOut = channel.Request(messageIn);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    ```  
  
     <span data-ttu-id="e9c34-135">Al crear el mensaje de solicitud, debe especificar la acción de mensaje que indica la acción que realiza el adaptador en la tabla de interfaz.</span><span class="sxs-lookup"><span data-stu-id="e9c34-135">While creating the request message, you must specify the message action that indicates the action that the adapter performs on the interface table.</span></span> <span data-ttu-id="e9c34-136">Para llevar a cabo una operación de inserción en la tabla MS_SAMPLE_EMPLOYEE, la acción de mensaje es `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`.</span><span class="sxs-lookup"><span data-stu-id="e9c34-136">To perform an Insert operation on the MS_SAMPLE_EMPLOYEE table, the message action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`.</span></span> <span data-ttu-id="e9c34-137">Para obtener información acerca de cómo se puede determinar la acción de mensaje para realizar diversas operaciones en tablas, vea [esquemas de mensaje para Insert, Update, Delete y las operaciones de Select](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e9c34-137">For information about how you can determine the message action for various operations on tables, see [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
9. <span data-ttu-id="e9c34-138">Obtiene el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e9c34-138">Get the response message.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
10. <span data-ttu-id="e9c34-139">Cierre el mensaje, el canal y el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="e9c34-139">Close the message, channel, and channel factory.</span></span>  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
11. <span data-ttu-id="e9c34-140">Generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9c34-140">Build the project.</span></span> <span data-ttu-id="e9c34-141">Después de compilar el proyecto, debe copiar el mensaje de solicitud, InsertRequest.xml, en la misma ubicación que el proyecto ejecutable.</span><span class="sxs-lookup"><span data-stu-id="e9c34-141">After building the project, you must copy the request message, InsertRequest.xml, at the same location as your project executable.</span></span> <span data-ttu-id="e9c34-142">Normalmente, esta ubicación es \bin\Debug\ en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9c34-142">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
12. <span data-ttu-id="e9c34-143">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9c34-143">Run the application.</span></span> <span data-ttu-id="e9c34-144">El mensaje de respuesta, Response.xml, se guarda en la ubicación especificada en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9c34-144">The response message, Response.xml, is saved at the location you specified in the application.</span></span> <span data-ttu-id="e9c34-145">El mensaje de respuesta contiene el número o registros insertados y es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9c34-145">The response message contains the number or records inserted and resembles the following:</span></span>  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     <span data-ttu-id="e9c34-146">El valor "1" indica que se inserta un registro único en la tabla MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="e9c34-146">The value “1” denotes that a single record is inserted into the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c34-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9c34-147">See Also</span></span>  
 [<span data-ttu-id="e9c34-148">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e9c34-148">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)