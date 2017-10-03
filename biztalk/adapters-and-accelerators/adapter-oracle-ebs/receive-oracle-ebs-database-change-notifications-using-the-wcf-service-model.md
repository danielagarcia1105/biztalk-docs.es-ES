---
title: Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 362193f5-2586-480f-a62e-1ed5e4ef342c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0350a6c16eca4a6639549cb5240f04fa1b8bebf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-the-wcf-service-model"></a><span data-ttu-id="69d81-102">Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="69d81-102">Receive Oracle E-Business Suite database change notifications using the WCF service model</span></span>
<span data-ttu-id="69d81-103">Este tema muestra cómo configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de notificación de consulta de una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="69d81-103">This topic demonstrates how to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive query notification messages from an Oracle database.</span></span> <span data-ttu-id="69d81-104">Para mostrar las notificaciones, considere la posibilidad de una tabla, ACCOUNTACTIVITY, con una columna "Procesados".</span><span class="sxs-lookup"><span data-stu-id="69d81-104">To demonstrate notifications, consider a table, ACCOUNTACTIVITY, with a “Processed” column.</span></span> <span data-ttu-id="69d81-105">Cuando se inserta un nuevo registro en esta tabla, el valor de la columna de estado se establece en "n".</span><span class="sxs-lookup"><span data-stu-id="69d81-105">When a new record is inserted to this table, the value of the Status column is set to “n.”</span></span> <span data-ttu-id="69d81-106">Puede configurar el adaptador para recibir notificaciones por registrarse para recibir notificaciones mediante una instrucción SQL que recupera todos los registros que tienen la columna "Procesados" como "n".</span><span class="sxs-lookup"><span data-stu-id="69d81-106">You can configure the adapter to receive notifications by registering for notifications using a SQL statement that retrieves all records that have “Processed” column as “n.”</span></span> <span data-ttu-id="69d81-107">Puede hacerlo mediante la especificación de la instrucción SQL para la **NotificationStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="69d81-107">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="69d81-108">Una vez que el cliente de adaptador recibe la notificación, puede contener la lógica para realizar las tareas siguientes en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="69d81-108">After the adapter client receives the notification, it can contain the logic to do any subsequent tasks on the Oracle database.</span></span> <span data-ttu-id="69d81-109">En este ejemplo, por simplicidad, el cliente de adaptador enumera todos los registros en la tabla que tienen la columna "Procesados" como "n".</span><span class="sxs-lookup"><span data-stu-id="69d81-109">In this example, for the sake of simplicity, the adapter client lists all the records in the table that have the “Processed” column as “n.”</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="69d81-110">Configuración de notificaciones con el adaptador de E-Business Oracle propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="69d81-110">Configuring Notifications with the Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="69d81-111">La siguiente tabla resume el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] propiedades de enlace que se utiliza para configurar la recepción de notificaciones de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="69d81-111">The table below summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure receiving notifications from Oracle E-Business Suite.</span></span> <span data-ttu-id="69d81-112">Debe especificar estas propiedades de enlace al ejecutar la aplicación .NET para recibir notificaciones.</span><span class="sxs-lookup"><span data-stu-id="69d81-112">You must specify these binding properties while running the .NET application to receive notifications.</span></span>  
  
|<span data-ttu-id="69d81-113">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="69d81-113">Binding Property</span></span>|<span data-ttu-id="69d81-114">Description</span><span class="sxs-lookup"><span data-stu-id="69d81-114">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="69d81-115">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="69d81-115">**InboundOperationType**</span></span>|<span data-ttu-id="69d81-116">Especifica la operación de entrada que se desea realizar.</span><span class="sxs-lookup"><span data-stu-id="69d81-116">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="69d81-117">Para recibir mensajes de notificación, establezca esta propiedad en **notificación**.</span><span class="sxs-lookup"><span data-stu-id="69d81-117">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="69d81-118">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="69d81-118">**NotificationPort**</span></span>|<span data-ttu-id="69d81-119">Especifica el número de puerto que debe abrir ODP.NET para realizar escuchas de notificación de cambio de base de datos de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="69d81-119">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="69d81-120">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="69d81-120">**NotificationStatement**</span></span>|<span data-ttu-id="69d81-121">Especifica la instrucción Select que se usa para registrar las notificaciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="69d81-121">Specifies the Select statement used to register for query notifications.</span></span> <span data-ttu-id="69d81-122">El adaptador obtiene un mensaje de notificación solo cuando el conjunto de resultados para que los cambios de la instrucción Select especificada.</span><span class="sxs-lookup"><span data-stu-id="69d81-122">The adapter gets a notification message only when the result set for the specified Select statement changes.</span></span>|  
|<span data-ttu-id="69d81-123">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="69d81-123">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="69d81-124">Especifica si el adaptador envía una notificación a los clientes de adaptador cuando se inicia el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="69d81-124">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="69d81-125">Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="69d81-125">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="69d81-126">Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir notificaciones de Oracle E-Business Suite, lea el resto de este tema.</span><span class="sxs-lookup"><span data-stu-id="69d81-126">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications from Oracle E-Business Suite, read the remainder of this topic.</span></span>  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a><span data-ttu-id="69d81-127">Configuración de notificaciones mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="69d81-127">Configuring Notifications Using the WCF Service Model</span></span>  
 <span data-ttu-id="69d81-128">Para recibir las notificaciones mediante el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="69d81-128">To receive the notifications using the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="69d81-129">Generar un contrato de servicio WCF (interfaz) para la **notificación** operación desde los metadatos expuestos por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="69d81-129">Generate a WCF service contract (interface) for the **Notification** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="69d81-130">Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69d81-130">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="69d81-131">Generar un cliente WCF para la **seleccione** operación en la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="69d81-131">Generate a WCF client for the **Select** operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="69d81-132">Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69d81-132">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="69d81-133">Implementar un servicio WCF de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="69d81-133">Implement a WCF service from this interface.</span></span>  
  
-   <span data-ttu-id="69d81-134">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="69d81-134">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="69d81-135">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="69d81-135">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="69d81-136">Los ejemplos de este tema recibe una notificación de la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="69d81-136">The examples in this topic receives notification for the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="69d81-137">Una secuencia de comandos para generar la tabla se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="69d81-137">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="69d81-138">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="69d81-138">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="69d81-139">Obtener un ejemplo, **Notification_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="69d81-139">A sample, **Notification_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="69d81-140">El contrato de servicio WCF y la clase</span><span class="sxs-lookup"><span data-stu-id="69d81-140">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="69d81-141">Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y las clases para que admite la **notificación** operación.</span><span class="sxs-lookup"><span data-stu-id="69d81-141">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Notification** operation.</span></span> <span data-ttu-id="69d81-142">Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="69d81-142">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="69d81-143">El contrato de servicio WCF (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69d81-143">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="69d81-144">El código siguiente muestra el contrato de servicio WCF (interfaz) que se genera para la **notificación** operación.</span><span class="sxs-lookup"><span data-stu-id="69d81-144">The following code shows the WCF service contract (interface) generated for the **Notification** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="Notification_")]  
public interface Notification_ {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/Notification/) of message Notification   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="69d81-145">Los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="69d81-145">The Message Contracts</span></span>  
 <span data-ttu-id="69d81-146">Aquí te mostramos el contrato de mensaje para la operación de notificación.</span><span class="sxs-lookup"><span data-stu-id="69d81-146">Following is the message contract for the Notification operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.Notification.NotificationDetails[] Details;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=1)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=2)]  
    public string[] ResourceNames;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=3)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=4)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(schemas.microsoft.com.OracleEBS._2008._05.Notification.NotificationDetails[] Details, string Info, string[] ResourceNames, string Source, string Type) {  
        this.Details = Details;  
        this.Info = Info;  
        this.ResourceNames = ResourceNames;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="69d81-147">Clase de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="69d81-147">WCF Service Class</span></span>  
 <span data-ttu-id="69d81-148">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF que implementa el contrato de servicio (interfaz).</span><span class="sxs-lookup"><span data-stu-id="69d81-148">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="69d81-149">El nombre del archivo es OracleEBSBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="69d81-149">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="69d81-150">Puede insertar la lógica para procesar el **notificación** operación directamente en esta clase.</span><span class="sxs-lookup"><span data-stu-id="69d81-150">You can insert the logic to process the **Notification** operation directly into this class.</span></span> <span data-ttu-id="69d81-151">El código siguiente muestra la clase de servicio WCF generada por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69d81-151">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleEBSBindingNamespace {  
  
    public class OracleEBSBindingService : Notification_ {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/Notification/) of message Notification   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a><span data-ttu-id="69d81-152">Recibir notificaciones de consulta mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="69d81-152">Receiving Query Notifications Using WCF Service Model</span></span>  
 <span data-ttu-id="69d81-153">Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir las notificaciones de consulta mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69d81-153">This section provides instructions on how to write a .NET application to receive query notifications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-query-notifications"></a><span data-ttu-id="69d81-154">Para recibir las notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="69d81-154">To receive query notifications</span></span>  
  
1.  <span data-ttu-id="69d81-155">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un cliente WCF para **seleccione** operación en el **ACCOUNTACTIVITY** tabla.</span><span class="sxs-lookup"><span data-stu-id="69d81-155">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client for **Select** operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="69d81-156">Usará a este cliente para realizar las operaciones Select después de recibir un mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="69d81-156">You will use this client to perform Select operations after receiving a notification message.</span></span> <span data-ttu-id="69d81-157">Agregue una nueva clase, TableOperation.cs, al proyecto y agregue el siguiente fragmento de código para llevar a cabo una operación de selección.</span><span class="sxs-lookup"><span data-stu-id="69d81-157">Add a new class, TableOperation.cs, to your project and add the following code snippet to perform a Select operation.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace Notification_ServiceModel  
    {  
        class TableOperation  
        {  
            public void TableOp()  
            {  
                //////////////////////////////////////////////////////////////////////  
                // CREATING THE CLIENT AND SETTING CLIENT CREDENTIALS  
                //////////////////////////////////////////////////////////////////////  
  
                Tables_APPS_ACCOUNTACTIVITYClient client = new Tables_APPS_ACCOUNTACTIVITYClient();  
                client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
                client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
                ////////////////////////////////////////////////////////////////////  
                // OPENING THE CLIENT  
                //////////////////////////////////////////////////////////////////////  
                try  
                {  
                    Console.WriteLine("Opening the client ...");  
                    client.Open();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                ////////////////////////////////////////////////////////////////////////////////////////  
                // SELECTING THE LAST INSERTED VALUES  
                ////////////////////////////////////////////////////////////////////////////////////////  
                Console.WriteLine("The application will now select the last inserted record");  
  
                schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.ACCOUNTACTIVITY.SelectRecord[] selectRecords;  
  
                try  
                {  
                    selectRecords = client.Select("*", "WHERE PROCESSED = 'n'");  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                Console.WriteLine("The details of the newly added records are:");  
                Console.WriteLine("********************************************");  
                for (int i = 0; i < selectRecords.Length; i++)  
                {  
                    Console.WriteLine("Transaction ID   : " + selectRecords[i].TID);  
                    Console.WriteLine("Account ID       : " + selectRecords[i].ACCOUNT);  
                    Console.WriteLine("Processed Status : " + selectRecords[i].PROCESSED);  
                    Console.WriteLine();  
                }  
                Console.WriteLine("********************************************");  
            }  
        }  
    }  
  
    ```  
  
2.  <span data-ttu-id="69d81-158">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y las clases auxiliares para el **notificación** operación.</span><span class="sxs-lookup"><span data-stu-id="69d81-158">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Notification** operation.</span></span>  
  
     <span data-ttu-id="69d81-159">Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="69d81-159">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="69d81-160">También puede especificar las propiedades de enlace al generar las clases de contrato y el Ayudante de servicio.</span><span class="sxs-lookup"><span data-stu-id="69d81-160">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="69d81-161">Esto garantiza que están establecidas correctamente en el archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="69d81-161">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
3.  <span data-ttu-id="69d81-162">Implementar un servicio WCF desde las clases de interfaz y auxiliar generado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="69d81-162">Implement a WCF service from the interface and helper classes generated in step 2.</span></span> <span data-ttu-id="69d81-163">El **notificación** método de esta clase puede producir una excepción para anular la operación, si se produce un error de procesamiento de los datos recibidos de la **notificación** operación; en caso contrario, el método no no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="69d81-163">The **Notification** method of this class can throw an exception to abort the operation, if an error is encountered processing the data received from the **Notification** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="69d81-164">La clase de servicio WCF debe atributo como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="69d81-164">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="69d81-165">En el **notificación** método, puede implementar la lógica de aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="69d81-165">Within the **Notification** method, you can implement your application logic directly.</span></span> <span data-ttu-id="69d81-166">Esta clase se puede encontrar en OracleEBSBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="69d81-166">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="69d81-167">Este código de este ejemplo Sub-clases el **OracleEBSBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="69d81-167">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="69d81-168">En este código, el mensaje de notificación recibido se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="69d81-168">In this code, the notification message received is written to the console.</span></span> <span data-ttu-id="69d81-169">Además, el **TableOp** método dentro de la **TableOperation** se invoca para llevar a cabo la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="69d81-169">Additionally, the **TableOp** method within the **TableOperation** class is invoked to perform the Select operation.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleEBSBindingNamespace.OracleEBSBindingService  
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
    ```  
  
4.  <span data-ttu-id="69d81-170">Debe implementar la clase siguiente para pasar las credenciales para Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="69d81-170">You must implement the following class to pass credentials for the Oracle E-Business Suite.</span></span> <span data-ttu-id="69d81-171">En la última parte de la aplicación, se creará una instancia de esta clase para pasar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="69d81-171">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
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
  
5.  <span data-ttu-id="69d81-172">Crear un **OracleEBSBinding** y configurar el adaptador para recibir las notificaciones de consulta mediante la especificación de las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="69d81-172">Create an **OracleEBSBinding** and configure the adapter to receive query notifications by specifying the binding properties.</span></span> <span data-ttu-id="69d81-173">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="69d81-173">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="69d81-174">Como mínimo, debe especificar el **InboundOperationType** y **NotificationStatement** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="69d81-174">At a minimum, you must specify the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Notification;  
    binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
    binding.NotifyOnListenerStart = true;  
    binding.NotificationPort = 10;  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="69d81-175">El valor de la **NotificationPort** debe establecer la propiedad binding en el mismo número de puerto que debe haber agregado a la lista de excepciones de Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="69d81-175">The value for the **NotificationPort** binding property must be set to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="69d81-176">Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, vea [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span><span class="sxs-lookup"><span data-stu-id="69d81-176">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="69d81-177">Si no establece la **NotificationPort** propiedad de enlace, el adaptador asumirá el valor predeterminado de -1 para esta propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="69d81-177">If you do not set the **NotificationPort** binding property, the adapter will assume the default value of -1 for this binding property.</span></span> <span data-ttu-id="69d81-178">En tal caso, tendrá que deshabilitar completamente el Firewall de Windows para recibir mensajes de notificación.</span><span class="sxs-lookup"><span data-stu-id="69d81-178">In such a case, you will have to completely disable Windows Firewall to receive notification messages.</span></span>  
  
6.  <span data-ttu-id="69d81-179">Especifique las credenciales de Oracle E-Business Suite creando el **NotificationCredentials** clase creada en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="69d81-179">Specify Oracle E-Business Suite credentials by instantiating the **NotificationCredentials** class you created in Step 4.</span></span>  
  
    ```  
    NotificationCredentials credentials = new NotificationCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
7.  <span data-ttu-id="69d81-180">Cree una instancia del servicio WCF que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="69d81-180">Create an instance of the WCF service created in step 3.</span></span>  
  
    ```  
    // create service instance  
    NotificationService service = new NotificationService();  
    ```  
  
8.  <span data-ttu-id="69d81-181">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio WCF y un URI de conexión base.</span><span class="sxs-lookup"><span data-stu-id="69d81-181">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="69d81-182">También debe especificar las credenciales aquí.</span><span class="sxs-lookup"><span data-stu-id="69d81-182">You must also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. <span data-ttu-id="69d81-183">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="69d81-183">Add a service endpoint to the service host.</span></span> <span data-ttu-id="69d81-184">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="69d81-184">To do this:</span></span>  
  
    -   <span data-ttu-id="69d81-185">Utilice el enlace creado en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="69d81-185">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="69d81-186">Especifica una URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.</span><span class="sxs-lookup"><span data-stu-id="69d81-186">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="69d81-187">Especifique el contrato como "Notification_".</span><span class="sxs-lookup"><span data-stu-id="69d81-187">Specify the contract as "Notification_".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify Notification_ as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  
    serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
    ```  
  
10. <span data-ttu-id="69d81-188">Para recibir el mensaje de notificación, abra el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="69d81-188">To receive notification message, open the service host.</span></span>  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="69d81-189">Para dejar de recibir notificaciones, cierre el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="69d81-189">To stop receiving notifications, close the service host.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="69d81-190">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69d81-190">Example</span></span>  
 <span data-ttu-id="69d81-191">En el ejemplo siguiente se muestra una aplicación .NET para recibir mensajes de notificación para la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="69d81-191">The following example shows a .NET application to receive notification messages for the ACCOUNTACTIVITY table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69d81-192">El fragmento de código siguiente crea un **TableOperation.cs** clase e invoca el **TableOp** método.</span><span class="sxs-lookup"><span data-stu-id="69d81-192">The following code snippet instantiates a **TableOperation.cs** class and invokes the **TableOp** method.</span></span> <span data-ttu-id="69d81-193">La clase y el método se describen en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="69d81-193">The class and the method are described in Step 1.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.OracleEBS;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleEBSBindingNamespace.OracleEBSBindingService  
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
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start receiving notifications...");  
                Console.ReadLine();  
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
                binding.NotifyOnListenerStart = true;  
                binding.NotificationPort = 10;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
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
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="69d81-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="69d81-194">See Also</span></span>  
 [<span data-ttu-id="69d81-195">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="69d81-195">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)