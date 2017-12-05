---
title: Recibir notificaciones de consulta de SQL mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9def31-3c5a-4326-b798-31bde0ff2568
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b21d2123b646a02669a9da65efc5069931e64c69
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="receive-query-notifications-from-sql-using-the-wcf-service-model"></a><span data-ttu-id="75479-102">Recibir notificaciones de consulta de SQL mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="75479-102">Receive Query Notifications from SQL using the WCF Service Model</span></span>
<span data-ttu-id="75479-103">Este tema muestra cómo configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de notificación de consulta de una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75479-103">This topic demonstrates how to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive query notification messages from a SQL Server database.</span></span> <span data-ttu-id="75479-104">Para mostrar las notificaciones, considere la posibilidad de una tabla de empleados, con una columna de "Status".</span><span class="sxs-lookup"><span data-stu-id="75479-104">To demonstrate notifications, consider a table, Employee, with a “Status” column.</span></span> <span data-ttu-id="75479-105">Cuando se inserta un nuevo registro en esta tabla, el valor de la columna de estado se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="75479-105">When a new record is inserted to this table, the value of the Status column is set to 0.</span></span> <span data-ttu-id="75479-106">Puede configurar el adaptador para recibir notificaciones por registrarse para recibir notificaciones mediante una instrucción SQL que recupera todos los registros que tienen la columna de estado como "0".</span><span class="sxs-lookup"><span data-stu-id="75479-106">You can configure the adapter to receive notifications by registering for notifications using a SQL statement that retrieves all records that have Status column as “0.”</span></span> <span data-ttu-id="75479-107">Puede hacerlo mediante la especificación de la instrucción SQL para la **NotificationStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="75479-107">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="75479-108">Una vez que el cliente de adaptador recibe la notificación, puede contener la lógica para realizar las tareas siguientes en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75479-108">After the adapter client receives the notification, it can contain the logic to do any subsequent tasks on the SQL Server database.</span></span> <span data-ttu-id="75479-109">En este ejemplo, por simplicidad, el cliente de adaptador enumera todos los registros en la tabla que tienen la columna de estado como "0".</span><span class="sxs-lookup"><span data-stu-id="75479-109">In this example, for the sake of simplicity, the adapter client lists all the records in the table that have the Status column as “0.”</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75479-110">Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) tema antes de empezar a desarrollar la aplicación .</span><span class="sxs-lookup"><span data-stu-id="75479-110">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on tables and views with user-defined types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) topic before you start developing your application.</span></span>  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="75479-111">Configuración de notificaciones con el adaptador SQL propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="75479-111">Configuring Notifications with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="75479-112">La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades de enlace que se utiliza para configurar la recepción de notificaciones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75479-112">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure receiving notifications from SQL Server.</span></span> <span data-ttu-id="75479-113">Debe especificar estas propiedades de enlace al ejecutar la aplicación .NET para recibir las notificaciones de una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75479-113">You must specify these binding properties while running the .NET application to receive the notifications from a SQL Server database.</span></span>  
  
|<span data-ttu-id="75479-114">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="75479-114">Binding Property</span></span>|<span data-ttu-id="75479-115">Description</span><span class="sxs-lookup"><span data-stu-id="75479-115">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="75479-116">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="75479-116">**InboundOperationType**</span></span>|<span data-ttu-id="75479-117">Especifica la operación de entrada que se desea realizar.</span><span class="sxs-lookup"><span data-stu-id="75479-117">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="75479-118">Para recibir mensajes de notificación, establezca esta propiedad en **notificación**.</span><span class="sxs-lookup"><span data-stu-id="75479-118">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="75479-119">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="75479-119">**NotificationStatement**</span></span>|<span data-ttu-id="75479-120">Especifica la instrucción SQL (SELECT o EXEC \< *procedimiento almacenado*\>) usa para registrar las notificaciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="75479-120">Specifies the SQL statement (SELECT or EXEC \<*stored procedure*\>) used to register for query notifications.</span></span> <span data-ttu-id="75479-121">El adaptador obtiene un mensaje de notificación de SQL Server sólo cuando el conjunto de resultados para que los cambios de instrucción SQL especificados.</span><span class="sxs-lookup"><span data-stu-id="75479-121">The adapter gets a notification message from SQL Server only when the result set for the specified SQL statement changes.</span></span>|  
|<span data-ttu-id="75479-122">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="75479-122">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="75479-123">Especifica si el adaptador envía una notificación a los clientes de adaptador cuando se inicia el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="75479-123">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="75479-124">Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="75479-124">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="75479-125">Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir notificaciones de SQL Server, seguir leyendo.</span><span class="sxs-lookup"><span data-stu-id="75479-125">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive notifications from SQL Server, read further.</span></span>  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a><span data-ttu-id="75479-126">Configuración de notificaciones mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="75479-126">Configuring Notifications Using the WCF Service Model</span></span>  
 <span data-ttu-id="75479-127">Para recibir las notificaciones mediante el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="75479-127">To receive the notifications using the WCF service model, you must:</span></span>  
  
1.  <span data-ttu-id="75479-128">Generar un contrato de servicio WCF (interfaz) para la **notificación** operación desde los metadatos expuestos por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="75479-128">Generate a WCF service contract (interface) for the **Notification** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="75479-129">Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75479-129">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
2.  <span data-ttu-id="75479-130">Generar un cliente WCF para la **seleccione** operación en la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="75479-130">Generate a WCF client for the **Select** operation on the Employee table.</span></span> <span data-ttu-id="75479-131">Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75479-131">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
3.  <span data-ttu-id="75479-132">Implementar un servicio WCF de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="75479-132">Implement a WCF service from this interface.</span></span>  
  
4.  <span data-ttu-id="75479-133">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="75479-133">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="75479-134">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="75479-134">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="75479-135">Los ejemplos de este tema reciban una notificación para la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="75479-135">The examples in this topic receive notification for the Employee table.</span></span> <span data-ttu-id="75479-136">Una secuencia de comandos para generar la tabla se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="75479-136">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="75479-137">Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="75479-137">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="75479-138">Obtener un ejemplo, **Notification_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="75479-138">A sample, **Notification_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="75479-139">El contrato de servicio WCF y la clase</span><span class="sxs-lookup"><span data-stu-id="75479-139">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="75479-140">Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y las clases para que admite la **notificación** operación.</span><span class="sxs-lookup"><span data-stu-id="75479-140">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Notification** operation.</span></span> <span data-ttu-id="75479-141">Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="75479-141">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="75479-142">El contrato de servicio WCF (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75479-142">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="75479-143">El código siguiente muestra el contrato de servicio WCF (interfaz) que se genera para la **notificación** operación.</span><span class="sxs-lookup"><span data-stu-id="75479-143">The following code shows the WCF service contract (interface) generated for the **Notification** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="NotificationOperation")]  
public interface NotificationOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/) of message  
    // Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="75479-144">Los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="75479-144">The Message Contracts</span></span>  
 <span data-ttu-id="75479-145">Aquí te mostramos el contrato de mensaje para la operación de notificación.</span><span class="sxs-lookup"><span data-stu-id="75479-145">Following is the message contract for the Notification operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=0)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=1)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=2)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(string Info, string Source, string Type) {  
        this.Info = Info;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="75479-146">Clase de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="75479-146">WCF Service Class</span></span>  
 <span data-ttu-id="75479-147">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF que implementa el contrato de servicio (interfaz).</span><span class="sxs-lookup"><span data-stu-id="75479-147">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="75479-148">El nombre del archivo es SqlAdapterBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="75479-148">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="75479-149">Puede insertar la lógica para procesar el **notificación** operación directamente en esta clase.</span><span class="sxs-lookup"><span data-stu-id="75479-149">You can insert the logic to process the **Notification** operation directly into this class.</span></span> <span data-ttu-id="75479-150">El código siguiente muestra la clase de servicio WCF generada por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75479-150">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : NotificationOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/)   
        // of message Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a><span data-ttu-id="75479-151">Recibir notificaciones de consulta mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="75479-151">Receiving Query Notifications Using WCF Service Model</span></span>  
 <span data-ttu-id="75479-152">Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir las notificaciones de consulta mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75479-152">This section provides instructions on how to write a .NET application to receive query notifications using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-query-notifications"></a><span data-ttu-id="75479-153">Para recibir las notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="75479-153">To receive query notifications</span></span>  
  
1.  <span data-ttu-id="75479-154">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un cliente WCF para **seleccione** operación en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="75479-154">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client for **Select** operation on the **Employee** table.</span></span> <span data-ttu-id="75479-155">Usará a este cliente para realizar las operaciones Select después de recibir un mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="75479-155">You will use this client to perform Select operations after receiving a notification message.</span></span> <span data-ttu-id="75479-156">Agregue una nueva clase, TableOperation.cs al proyecto y agregue el siguiente fragmento de código para llevar a cabo una operación de selección.</span><span class="sxs-lookup"><span data-stu-id="75479-156">Add a new class, TableOperation.cs to your project and add the following code snippet to perform a Select operation.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace Notification_ServiceModel  
    {  
        public class TableOperation  
        {  
            public void TableOp()  
            {  
                ///////////////////////////////////////////////////////////////////////  
                // CREATING THE CLIENT  
                ///////////////////////////////////////////////////////////////////////  
  
                TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
  
                client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
                client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
                ///////////////////////////////////////////////////////////////////////  
                // OPENING THE CLIENT  
                ///////////////////////////////////////////////////////////////////////  
  
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
  
                ///////////////////////////////////////////////////////////////////////  
                // SELECTING THE LAST INSERTED RECORD FROM THE TABLE  
                ///////////////////////////////////////////////////////////////////////  
                schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
                try  
                {  
                    selectRecords = client.Select("*", "where Status=0");  
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
                    Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
                    Console.WriteLine("Employee Designation: " + selectRecords[i].Designation);  
                    Console.WriteLine("Employee Status    : " + selectRecords[i].Status);  
                    Console.WriteLine();  
                }  
                Console.WriteLine("********************************************");  
  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="75479-157">Dado que este fragmento de código realiza operaciones en la tabla de empleados que contiene una columna UDT Point, asegúrese de que colocar la DLL de UDT en la carpeta \bin\Debug del proyecto mientras se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75479-157">Because this code snippet performs operations on the Employee table that contains a Point UDT column, make sure you put the UDT DLL under the project’s \bin\Debug folder while running the application.</span></span>  
  
2.  <span data-ttu-id="75479-158">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y las clases auxiliares para el **notificación** operación.</span><span class="sxs-lookup"><span data-stu-id="75479-158">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Notification** operation.</span></span>  
  
     <span data-ttu-id="75479-159">Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="75479-159">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="75479-160">También puede especificar las propiedades de enlace al generar las clases de contrato y el Ayudante de servicio.</span><span class="sxs-lookup"><span data-stu-id="75479-160">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="75479-161">Esto garantiza que están establecidas correctamente en el archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="75479-161">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
3.  <span data-ttu-id="75479-162">Implementar un servicio WCF desde las clases de interfaz y auxiliar generado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="75479-162">Implement a WCF service from the interface and helper classes generated in step 2.</span></span> <span data-ttu-id="75479-163">El **notificación** método de esta clase puede producir una excepción para anular la operación, si se produce un error de procesamiento de los datos recibidos de la **notificación** operación; en caso contrario, el método no no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="75479-163">The **Notification** method of this class can throw an exception to abort the operation, if an error is encountered processing the data received from the **Notification** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="75479-164">La clase de servicio WCF debe atributo como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="75479-164">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="75479-165">En el **notificación** método, puede implementar la lógica de aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="75479-165">Within the **Notification** method, you can implement your application logic directly.</span></span> <span data-ttu-id="75479-166">Esta clase se puede encontrar en SqlAdapterBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="75479-166">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="75479-167">Este código de este ejemplo Sub-clases el **SqlAdapterBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="75479-167">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="75479-168">En este código, el mensaje de notificación recibido se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="75479-168">In this code, the notification message received is written to the console.</span></span> <span data-ttu-id="75479-169">Además, el **TableOp** método dentro de la **TableOperation** se invoca para llevar a cabo la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="75479-169">Additionally, the **TableOp** method within the **TableOperation** class is invoked to perform the Select operation.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
  
            // Invoke th TableOp method in the TableOperation class  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="75479-170">Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no acepta credenciales como parte del URI de conexión, debe implementar la clase siguiente para pasar las credenciales de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75479-170">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="75479-171">En la última parte de la aplicación, se creará una instancia de esta clase para pasar las credenciales de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75479-171">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  
  
    ```  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new NotificationCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="75479-172">Crear un **SqlAdapterBinding** y configurar el adaptador para recibir las notificaciones de consulta mediante la especificación de las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="75479-172">Create a **SqlAdapterBinding** and configure the adapter to receive query notifications by specifying the binding properties.</span></span> <span data-ttu-id="75479-173">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="75479-173">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="75479-174">Como mínimo, debe especificar el **InboundOperationType** y **NotificationStatement** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="75479-174">At a minimum, you must specify the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Notification;  
    binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
    binding.NotifyOnListenerStart = true;  
    ```  
  
6.  <span data-ttu-id="75479-175">Especifique las credenciales de base de datos de SQL Server creando el **NotificationCredentials** clase creada en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="75479-175">Specify SQL Server database credentials by instantiating the **NotificationCredentials** class you created in Step 4.</span></span>  
  
    ```  
    NotificationCredentials credentials = new NotificationCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
7.  <span data-ttu-id="75479-176">Cree una instancia del servicio WCF que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="75479-176">Create an instance of the WCF service created in step 3.</span></span>  
  
    ```  
    // create service instance  
    NotificationService service = new NotificationService();  
    ```  
  
8.  <span data-ttu-id="75479-177">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio WCF y un URI de conexión base.</span><span class="sxs-lookup"><span data-stu-id="75479-177">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="75479-178">También debe especificar las credenciales aquí.</span><span class="sxs-lookup"><span data-stu-id="75479-178">You must also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. <span data-ttu-id="75479-179">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="75479-179">Add a service endpoint to the service host.</span></span> <span data-ttu-id="75479-180">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="75479-180">To do this:</span></span>  
  
    -   <span data-ttu-id="75479-181">Utilice el enlace creado en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="75479-181">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="75479-182">Especifica una URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.</span><span class="sxs-lookup"><span data-stu-id="75479-182">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="75479-183">Especifique el contrato como "NotificationOperation".</span><span class="sxs-lookup"><span data-stu-id="75479-183">Specify the contract as "NotificationOperation".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify NotificationOperation as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
    ```  
  
10. <span data-ttu-id="75479-184">Para recibir el mensaje de notificación, abra el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="75479-184">To receive notification message, open the service host.</span></span>  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="75479-185">Para dejar de recibir notificaciones, cierre el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="75479-185">To stop receiving notifications, close the service host.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="75479-186">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75479-186">Example</span></span>  
 <span data-ttu-id="75479-187">En el ejemplo siguiente se muestra una aplicación .NET para recibir mensajes de notificación para la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="75479-187">The following example shows a .NET application to receive notification messages for the Employee table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75479-188">El fragmento de código siguiente crea un **TableOperation.cs** clase e invoca el **TableOp** método.</span><span class="sxs-lookup"><span data-stu-id="75479-188">The following code snippet instantiates a **TableOperation.cs** class and invokes the **TableOp** method.</span></span> <span data-ttu-id="75479-189">La clase y el método se describen en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="75479-189">The class and the method are described in Step 1.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
        }  
    }  
  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new NotificationCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
                binding.NotifyOnListenerStart = true;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Waiting for notification...");  
  
                Console.WriteLine("\nHit <RETURN> to stop receiving notification");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                // If there is an error it will be specified in the inner exception   
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop receiving notifications  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="75479-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="75479-190">See Also</span></span>  
[<span data-ttu-id="75479-191">Desarrollar aplicaciones de SQL con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="75479-191">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)