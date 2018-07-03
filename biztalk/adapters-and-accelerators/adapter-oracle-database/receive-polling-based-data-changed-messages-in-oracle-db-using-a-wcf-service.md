---
title: Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving polling-based messages
- how to, receive polling-based message
- polling-based messages, receiving by using the WCF service model
ms.assetid: 0324e8bf-d9d1-46f5-b896-b9fc8e61d514
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda98a1600df28fab476114e697cd47e24316251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012605"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="59c62-102">Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="59c62-102">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="59c62-103">Puede configurar el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] recibir datos basados en sondeos cambiado mensajes con respecto a una tabla de Oracle o la vista.</span><span class="sxs-lookup"><span data-stu-id="59c62-103">You can configure the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to receive polling-based data changed messages against an Oracle table or view.</span></span> <span data-ttu-id="59c62-104">Para recibir mensajes de cambio de datos, el adaptador ejecuta periódicamente una consulta SQL en una tabla de Oracle o la vista seguido de un bloque de código PL/SQL opcional.</span><span class="sxs-lookup"><span data-stu-id="59c62-104">To receive data-changed messages, the adapter periodically executes a SQL query against an Oracle table or view followed by an optional PL/SQL code block.</span></span> <span data-ttu-id="59c62-105">A continuación, se devuelven los resultados de la consulta SQL mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a la aplicación como un conjunto en una operación POLLINGSTMT entrante fuertemente tipada de resultados.</span><span class="sxs-lookup"><span data-stu-id="59c62-105">The results of the SQL query are then returned by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to your application as a strongly-typed result set in an inbound POLLINGSTMT operation.</span></span> <span data-ttu-id="59c62-106">Para obtener más información sobre el mecanismo utilizado para configurar y realizar el sondeo de Oracle database mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="59c62-106">For more information about the mechanism used to configure and perform polling on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="59c62-107">Se recomienda encarecidamente que lea este tema antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="59c62-107">We strongly recommended that you read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="59c62-108">Para recibir la operación POLLINGSTMT cuando se usa el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="59c62-108">To receive the POLLINGSTMT operation when you use the WCF service model, you must:</span></span>  
  
- <span data-ttu-id="59c62-109">Generar un contrato de servicio WCF (interfaz) para la operación POLLINGSTMT desde los metadatos expuestos por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="59c62-109">Generate a WCF service contract (interface) for the POLLINGSTMT operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="59c62-110">Para ello, usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o ServiceModel Metadata Utility Tool (svcutil.exe).</span><span class="sxs-lookup"><span data-stu-id="59c62-110">To do this, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe).</span></span>  
  
- <span data-ttu-id="59c62-111">Implementar un servicio WCF desde esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="59c62-111">Implement a WCF service from this interface.</span></span>  
  
- <span data-ttu-id="59c62-112">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="59c62-112">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
  <span data-ttu-id="59c62-113">Los temas de esta sección proporcionan información y procedimientos que le ayudarán a realizar el sondeo en las tablas de base de datos de Oracle y las vistas en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="59c62-113">The topics in this section provide information and procedures to help you perform polling on Oracle database tables and views in the WCF service model.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="59c62-114">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="59c62-114">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="59c62-115">Los ejemplos en este tema usan la tabla /SCOTT/ACCOUNTACTIVITY y la función /SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="59c62-115">The examples in this topic use the /SCOTT/ACCOUNTACTIVITY table and the /SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY function.</span></span> <span data-ttu-id="59c62-116">Una secuencia de comandos para generar estos artefactos se suministra con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="59c62-116">A script to generate these artifacts is supplied with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="59c62-117">Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59c62-117">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="59c62-118">Configuración de sondeo en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="59c62-118">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="59c62-119">Configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para realizar el sondeo en vistas y tablas de base de datos de Oracle estableciendo las propiedades de enlace y una propiedad de conexión opcional (parámetro).</span><span class="sxs-lookup"><span data-stu-id="59c62-119">You configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to perform polling on Oracle database tables and views by setting binding properties and an optional connection property (parameter).</span></span> <span data-ttu-id="59c62-120">Algunas de estas propiedades son obligatorias, y algunos, tener un efecto, deben establecerse en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59c62-120">Some of these properties are mandatory, and some, to have an effect, must be set both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="59c62-121">En tiempo de diseño, se establecen los parámetros de conexión y las propiedades de enlace cuando se conecta a la base de datos de Oracle para generar un contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="59c62-121">At design-time, you set connection parameters and binding properties when you connect to the Oracle Database to generate a WCF service contract.</span></span>  
  
- <span data-ttu-id="59c62-122">En tiempo de ejecución definir propiedades de enlace en el objeto OracleDBBinding que usó para crear el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="59c62-122">At runtime you set binding properties on the OracleDBBinding object that you use to create the service host.</span></span> <span data-ttu-id="59c62-123">Establece el parámetro de conexión al agregar un agente de escucha del servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="59c62-123">You set the connection parameter when you add a service listener to the service host.</span></span>  
  
  <span data-ttu-id="59c62-124">En la lista siguiente proporciona una breve descripción de las propiedades de enlace y los parámetros de conexión utilizados para configurar sondeo:</span><span class="sxs-lookup"><span data-stu-id="59c62-124">The following list provides a brief overview of the binding properties and connection parameters used to configure polling:</span></span>  
  
- <span data-ttu-id="59c62-125">El **PollingStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="59c62-125">The **PollingStatement** binding property.</span></span> <span data-ttu-id="59c62-126">Debe establecer esta propiedad de enlace en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59c62-126">You must set this binding property both at design-time and at run-time.</span></span>  
  
- <span data-ttu-id="59c62-127">Propiedades de enlace opcional.</span><span class="sxs-lookup"><span data-stu-id="59c62-127">Optional binding properties.</span></span> <span data-ttu-id="59c62-128">Estos solo deben establecerse en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59c62-128">These only have to be set at run-time.</span></span>  
  
- <span data-ttu-id="59c62-129">El **AcceptCredentialsInUri** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="59c62-129">The **AcceptCredentialsInUri** binding property.</span></span> <span data-ttu-id="59c62-130">Debe establecer esta propiedad de enlace en **true** durante el tiempo de ejecución si desea habilitar las credenciales en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="59c62-130">You must set this binding property to **true** during run-time if you want to enable credentials in the connection URI.</span></span> <span data-ttu-id="59c62-131">El nombre de usuario y la contraseña deben estar presentes en el URI de conexión cuando se agrega un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="59c62-131">The user name and password must be present in the connection URI when you add a service endpoint to the service host.</span></span>  
  
- <span data-ttu-id="59c62-132">El **PollingId** parámetro de cadena en el URI de conexión de consulta.</span><span class="sxs-lookup"><span data-stu-id="59c62-132">The **PollingId** query string parameter in the connection URI.</span></span> <span data-ttu-id="59c62-133">Si desea cambiar el espacio de nombres de la operación POLLINGSTMT, debe establecer esta propiedad de conexión en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59c62-133">If you want to change the namespace of the POLLINGSTMT operation, you must set this connection property both at design-time and run-time.</span></span>  
  
  <span data-ttu-id="59c62-134">Para obtener una descripción completa de las propiedades de enlace y los parámetros de conexión que se usa para configurar el sondeo, consulte [recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="59c62-134">For a complete description of the binding properties and connection parameters used to configure polling, see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="59c62-135">El contrato de servicio WCF y la clase</span><span class="sxs-lookup"><span data-stu-id="59c62-135">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="59c62-136">Usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para crear un WCF del servicio de contrato (interfaz) y clases auxiliares para la operación POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="59c62-136">You use either the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to create a WCF service contract (interface) and supporting classes for the POLLINGSTMT operation.</span></span>  
  
 <span data-ttu-id="59c62-137">Cuando se conecta a la base de datos de Oracle con cualquiera de estas herramientas para generar un contrato de servicio para la operación POLLINGSTMT:</span><span class="sxs-lookup"><span data-stu-id="59c62-137">When you connect to the Oracle database with either of these tools to generate a service contract for the POLLINGSTMT operation:</span></span>  
  
- <span data-ttu-id="59c62-138">Debe especificar el **PollingStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="59c62-138">You must specify the **PollingStatement** binding property.</span></span> <span data-ttu-id="59c62-139">El adaptador utiliza la instrucción SELECT en esta propiedad de enlace para generar los metadatos correctos para el conjunto de resultados fuertemente tipado devuelto por la operación POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="59c62-139">The adapter uses the SELECT statement in this binding property to generate the correct metadata for the strongly-typed result set returned by the POLLINGSTMT operation.</span></span>  
  
- <span data-ttu-id="59c62-140">También puede especificar un parámetro PollingId en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="59c62-140">You can optionally specify a PollingId parameter in the connection URI.</span></span> <span data-ttu-id="59c62-141">El adaptador utiliza este parámetro para generar el espacio de nombres para la operación POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="59c62-141">The adapter uses this parameter to generate the namespace for the POLLINGSTMT operation.</span></span>  
  
  <span data-ttu-id="59c62-142">En los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="59c62-142">In the following examples:</span></span>  
  
- <span data-ttu-id="59c62-143">**PollingStatement** está establecido en "SELECT \* desde ACCOUNTACTIVITY FOR UPDATE".</span><span class="sxs-lookup"><span data-stu-id="59c62-143">**PollingStatement** is set to "SELECT \* FROM ACCOUNTACTIVITY FOR UPDATE".</span></span>  
  
- <span data-ttu-id="59c62-144">**PollingId** está establecido en "AcctActivity".</span><span class="sxs-lookup"><span data-stu-id="59c62-144">**PollingId** is set to "AcctActivity".</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="59c62-145">El contrato de servicio WCF (interfaz)</span><span class="sxs-lookup"><span data-stu-id="59c62-145">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="59c62-146">El código siguiente muestra el contrato de servicio WCF (interfaz) generado para la operación POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="59c62-146">The following code shows the WCF service contract (interface) generated for the POLLINGSTMT operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="POLLINGSTMT_OperationGroup")]  
public interface POLLINGSTMT_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)  
    // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT")]  
    void POLLINGSTMT(POLLINGSTMT request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="59c62-147">Los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="59c62-147">The Message Contracts</span></span>  
 <span data-ttu-id="59c62-148">El espacio de nombres de contrato de mensaje se modifica mediante el parámetro PollingId en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="59c62-148">The message contract namespace is modified by the PollingId parameter in the connection URI.</span></span> <span data-ttu-id="59c62-149">El mensaje de solicitud devuelve un conjunto de registros fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="59c62-149">The request message returns a set of strongly-typed records.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="POLLINGSTMT", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", IsWrapped=true)]  
public partial class POLLINGSTMT {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD;  
  
    public POLLINGSTMT() {  
    }  
  
    public POLLINGSTMT(microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD) {  
        this.POLLINGSTMTRECORD = POLLINGSTMTRECORD;  
    }  
}  
```  
  
### <a name="the-data-contract-namespace"></a><span data-ttu-id="59c62-150">El Namespace de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="59c62-150">The Data Contract Namespace</span></span>  
 <span data-ttu-id="59c62-151">Un contrato de datos es un acuerdo formal entre un servicio y un cliente que abstractamente describe los datos que se van a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="59c62-151">A data contract is a formal agreement between a service and a client that abstractly describes the data to be exchanged.</span></span> <span data-ttu-id="59c62-152">Es decir, con el fin de comunicarse, el cliente y el servicio no debe compartir los mismos tipos, los mismos contratos de datos.</span><span class="sxs-lookup"><span data-stu-id="59c62-152">That is, in order to communicate, the client and the service do not have to share the same types, only the same data contracts.</span></span>  
  
 <span data-ttu-id="59c62-153">Mensajes de cambio en el caso de datos, el espacio de nombres de contrato de datos también se ha modificado por el parámetro PollingId (si se especifica) en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="59c62-153">In case of data change messages, the data contract namespace is also modified by the PollingId parameter (if specified) in the connection URI.</span></span> <span data-ttu-id="59c62-154">El contrato de datos se compone de una clase que representa un registro en el conjunto de resultados de consulta fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="59c62-154">The data contract is composed of a class that represents a strongly-typed record in the query result set.</span></span> <span data-ttu-id="59c62-155">En este ejemplo, se omiten los detalles de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="59c62-155">The details of the class definition are omitted in this example.</span></span> <span data-ttu-id="59c62-156">La clase contiene propiedades que representan las columnas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="59c62-156">The class contains properties that represent the columns in the result set.</span></span>  
  
 <span data-ttu-id="59c62-157">En el ejemplo siguiente, se usa el PollingId "AcctActivity".</span><span class="sxs-lookup"><span data-stu-id="59c62-157">In the following example, the PollingId “AcctActivity” is used.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity {  
    using System.Runtime.Serialization;  
  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute(Name="POLLINGSTMTRECORD", Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity")]  
    public partial class POLLINGSTMTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
     }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="59c62-158">Clase de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="59c62-158">WCF Service Class</span></span>  
 <span data-ttu-id="59c62-159">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF implementa el contrato de servicio (interfaz).</span><span class="sxs-lookup"><span data-stu-id="59c62-159">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="59c62-160">El nombre del archivo es OracleDBBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="59c62-160">The name of the file is OracleDBBindingService.cs.</span></span> <span data-ttu-id="59c62-161">Puede insertar la lógica para procesar la operación POLLINGSTMT directamente en esta clase.</span><span class="sxs-lookup"><span data-stu-id="59c62-161">You can insert the logic to process the POLLINGSTMT operation directly into this class.</span></span> <span data-ttu-id="59c62-162">Si utiliza svcutil.exe para generar la interfaz de contrato de servicio, debe implementar esta clase.</span><span class="sxs-lookup"><span data-stu-id="59c62-162">If you use svcutil.exe to generate the service contract interface, you must implement this class yourself.</span></span> <span data-ttu-id="59c62-163">El código siguiente muestra la clase de servicio WCF generada por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59c62-163">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : POLLINGSTMT_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)   
        // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void POLLINGSTMT(POLLINGSTMT request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-the-pollingstmt-operation"></a><span data-ttu-id="59c62-164">Recepción de la operación POLLINGSTMT</span><span class="sxs-lookup"><span data-stu-id="59c62-164">Receiving the POLLINGSTMT Operation</span></span>  
  
#### <a name="to-receive-polling-data-from-the-oracle-database-adapter"></a><span data-ttu-id="59c62-165">Para recibir datos de sondeo del adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="59c62-165">To receive polling data from the Oracle Database adapter</span></span>  
  
1. <span data-ttu-id="59c62-166">Use el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o svcutil.exe para generar un WCF service contrato (interfaz) y clases auxiliares para la operación POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="59c62-166">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or svcutil.exe to generate a WCF service contract (interface) and helper classes for the POLLINGSTMT operation.</span></span> <span data-ttu-id="59c62-167">Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="59c62-167">For more information, see [Generate a WCF client or a WCF service contract for Oracle Database solution artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span> <span data-ttu-id="59c62-168">Como mínimo, debe establecer el **PollingStatement** enlaza la propiedad cuando se conecta al adaptador.</span><span class="sxs-lookup"><span data-stu-id="59c62-168">At a minimum, you must set the **PollingStatement** binding property when you connect to the adapter.</span></span> <span data-ttu-id="59c62-169">También puede especificar un parámetro PollingId en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="59c62-169">You can optionally specify a PollingId parameter in the connection URI.</span></span> <span data-ttu-id="59c62-170">Si usas el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], debe establecer todos los parámetros de enlace necesarios para la configuración.</span><span class="sxs-lookup"><span data-stu-id="59c62-170">If you are using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], you should set all of the binding parameters necessary for your configuration.</span></span> <span data-ttu-id="59c62-171">Esto garantiza que están establecidas correctamente en el archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="59c62-171">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2. <span data-ttu-id="59c62-172">Implementar un servicio WCF desde las clases auxiliares y la interfaz generada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="59c62-172">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="59c62-173">El método POLLINGSTMT de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la operación POLLINGSTMT; en caso contrario, el método no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="59c62-173">The POLLINGSTMT method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the POLLINGSTMT operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="59c62-174">Debe atributo la clase de servicio WCF como sigue:</span><span class="sxs-lookup"><span data-stu-id="59c62-174">You must attribute the WCF service class as follows:</span></span>  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
   1. <span data-ttu-id="59c62-175">Si ha usado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar la interfaz, puede implementar la lógica directamente en el **POLLINGSTMT** método generado **OracleDBBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="59c62-175">If you used the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate the interface, you can implement your logic directly in the **POLLINGSTMT** method in the generated **OracleDBBindingService** class.</span></span> <span data-ttu-id="59c62-176">Esta clase puede encontrarse en OracleDBBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="59c62-176">This class can be found in OracleDBBindingService.cs.</span></span> <span data-ttu-id="59c62-177">Este código en este ejemplo Sub clases el **OracleDBBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="59c62-177">This code in this example sub-classes the **OracleDBBindingService** class.</span></span>  
  
      ```  
      [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
      public class PollingStmtService : OracleDBBindingService  
      {  
          public override void POLLINGSTMT(POLLINGSTMT request)  
          {  
              Console.WriteLine("\nNew Polling Records Received");  
              Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
              for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
              {  
                  Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                      request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                      request.POLLINGSTMTRECORD[i].AMOUNT,  
                                      request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                      request.POLLINGSTMTRECORD[i].DESCRIPTION);  
              }  
          }  
      }  
      ```  
  
   2. <span data-ttu-id="59c62-178">Si utiliza svcutil.exe para generar la interfaz, debe crear un servicio WCF que implementa la interfaz e implementar la lógica en el **POLLINGSTMT** método de esta clase.</span><span class="sxs-lookup"><span data-stu-id="59c62-178">If you used svcutil.exe to generate the interface, you must create a WCF service that implements the interface and implement your logic in the **POLLINGSTMT** method of this class.</span></span>  
  
3. <span data-ttu-id="59c62-179">Cree una instancia del servicio WCF que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="59c62-179">Create an instance of the WCF service created in step 2.</span></span>  
  
   ```  
   // create service instance  
   PollingStmtService pollingInstance = new PollingStmtService();  
   ```  
  
4. <span data-ttu-id="59c62-180">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio de WCF y un URI de conexión de base.</span><span class="sxs-lookup"><span data-stu-id="59c62-180">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="59c62-181">El URI de conexión base no puede contener userinfoparams o un query_string.</span><span class="sxs-lookup"><span data-stu-id="59c62-181">The base connection URI cannot contain userinfoparams or a query_string.</span></span>  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracledb://Adapter") };  
   ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
   ```  
  
5. <span data-ttu-id="59c62-182">Crear un **OracleDBBinding** y configurar la operación de sondeo estableciendo sus propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="59c62-182">Create an **OracleDBBinding** and configure the polling operation by setting its binding properties.</span></span> <span data-ttu-id="59c62-183">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="59c62-183">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="59c62-184">Como mínimo, debe especificar la instrucción de sondeo y el intervalo de sondeo.</span><span class="sxs-lookup"><span data-stu-id="59c62-184">At a minimum, you must specify the polling statement and polling interval.</span></span> <span data-ttu-id="59c62-185">En este ejemplo, especifique las credenciales como parte del URI por lo que debe establecer también la **AcceptCredentialsInUri** a **true**.</span><span class="sxs-lookup"><span data-stu-id="59c62-185">In this example, you specify the credentials as part of the URI so you must also set the **AcceptCredentialsInUri** to **true**.</span></span>  
  
   ```  
   // Create and configure a binding for the service endpoint. NOTE: binding  
   // parameters are set here for clarity, but these are already set in the  
   // the generated configuration file  
   OracleDBBinding binding = new OracleDBBinding();  
  
   // The credentials are included in the connection URI, so set this property to true  
   binding.AcceptCredentialsInUri = true;  
  
   // Same as statement specified in Configure Adapter dialog box  
   binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
   // Be sure to set the interval long enough to complete processing before  
   // the next poll  
   binding.PollingInterval = 15;  
   // Polling is transactional; be sure to set an adequate isolation level   
   // for your environment  
   binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
   ```  
  
6. <span data-ttu-id="59c62-186">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="59c62-186">Add a service endpoint to the service host.</span></span> <span data-ttu-id="59c62-187">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="59c62-187">To do this:</span></span>  
  
   -   <span data-ttu-id="59c62-188">Utilice el enlace creado en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="59c62-188">Use the binding created in step 5.</span></span>  
  
   -   <span data-ttu-id="59c62-189">Especifique un URI que contiene las credenciales de conexión y, si es necesario, un PollingId.</span><span class="sxs-lookup"><span data-stu-id="59c62-189">Specify a connection URI that contains credentials and, if needed, a PollingId.</span></span>  
  
   -   <span data-ttu-id="59c62-190">Especifique el contrato como "POLLINGSTMT_OperationGroup".</span><span class="sxs-lookup"><span data-stu-id="59c62-190">Specify the contract as "POLLINGSTMT_OperationGroup".</span></span>  
  
   ```  
   // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
   Uri serviceUri = new Uri("oracledb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
   srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
   ```  
  
7. <span data-ttu-id="59c62-191">Para recibir datos de sondeo, abra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="59c62-191">To receive polling data, open the service host.</span></span> <span data-ttu-id="59c62-192">El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="59c62-192">The adapter will return data whenever the query returns a result set.</span></span>  
  
   ```  
   // Open the service host to begin polling  
   srvHost.Open();  
   ```  
  
8. <span data-ttu-id="59c62-193">Para finalizar el sondeo, cierre el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="59c62-193">To terminate polling, close the service host.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="59c62-194">El adaptador seguirá sondeando hasta que se cierra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="59c62-194">The adapter will continue to poll until the service host is closed.</span></span>  
  
   ```  
   srvHost.Close();  
   ```  
  
### <a name="example"></a><span data-ttu-id="59c62-195">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59c62-195">Example</span></span>  
 <span data-ttu-id="59c62-196">El ejemplo siguiente muestra una consulta de sondeo que se ejecuta en la tabla ACCOUNTACTIVITY/SCOTT /.</span><span class="sxs-lookup"><span data-stu-id="59c62-196">The following example shows a polling query that executes against the /SCOTT/ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="59c62-197">La instrucción de sondeo posterior a la invoca una función de Oracle que mueve los registros procesados a /SCOTT/ACCOUNTHISTORY de otra tabla.</span><span class="sxs-lookup"><span data-stu-id="59c62-197">The post-poll statement invokes an Oracle function that moves the processed records to another table /SCOTT/ACCOUNTHISTORY.</span></span> <span data-ttu-id="59c62-198">El espacio de nombres de la operación POLLINGSTMT se modifica estableciendo el parámetro PollingId "AccountActivity" en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="59c62-198">The namespace of the POLLINGSTMT operation is modified by setting the PollingId parameter to "AccountActivity" in the connection URI.</span></span> <span data-ttu-id="59c62-199">En este ejemplo, se crea el servicio WCF para la operación POLLINGSTMT subclasificando generado **OracleDBBindingService** clase; sin embargo, puede implementar la lógica directamente en la clase generada.</span><span class="sxs-lookup"><span data-stu-id="59c62-199">In this example, the WCF service for the POLLINGSTMT operation is created by sub-classing the generated **OracleDBBindingService** class; however, you can implement your logic directly in the generated class.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add these three references to use the Oracle adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
using microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity;  
using OracleDBBindingNamespace;  
  
namespace OraclePollingSM  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingStmtService : OracleDBBindingService  
    {  
        public override void POLLINGSTMT(POLLINGSTMT request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
            for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                    request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                    request.POLLINGSTMTRECORD[i].AMOUNT,  
                                    request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                    request.POLLINGSTMTRECORD[i].DESCRIPTION);  
  
            }  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
         }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost srvHost = null;  
  
            // This URI is used to specify the address for the ServiceEndpoint  
            // It must contain credentials and the PollingId (if any) that was used to generate  
            // the WCF service callback interface  
            Uri serviceUri = new Uri("OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
  
            // This URI is used to initialize the ServiceHost. It cannot contain  
            // userinfoparms (credentials) or a query_string (PollingId); otherwise,  
            // an exception is thrown when the ServiceHost is initialized.  
            Uri[] baseUri = new Uri[] { new Uri("OracleDb://Adapter") };  
  
            Console.WriteLine("Sample started, initializing service host -- please wait");  
  
            // create an instanc of the WCF service callback class  
            PollingStmtService pollingInstance = new PollingStmtService();  
  
            try  
            {  
                // Create a ServiceHost with the service callback instance and a base URI (address)  
                srvHost = new ServiceHost(pollingInstance, baseUri);  
  
                // Create and configure a binding for the service endpoint. Note: binding  
                // parameters are set here for clarity but these are already set in the  
                // generated configuration file  
                //  
                // The following properties are set  
                //    AcceptCredentialsInUri (true) to enable credentials in the connection URI for AddServiceEndpoint  
                //    PollingStatement  
                //    PostPollStatement calls PROCESS_ACTIVITY on Oracle. This procedure moves the queried records to  
                //                      the ACCOUNTHISTORY table  
                //    PollingInterval (15 seconds)  
                //    TransactionIsolationLevel   
  
                OracleDBBinding binding = new OracleDBBinding();  
  
                // The Credentials are included in the Connection Uri so set this property true  
                binding.AcceptCredentialsInUri = true;  
  
                // Same as statement specified in Configure Adapter dialog box  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Be sure to set the interval long enough to complete processing before  
                // the next poll  
                binding.PollingInterval = 15;  
  
                // Polling is transactional, be sure to set an adequate isolation level   
                // for your environment  
                binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
  
                // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
                srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
  
                Console.WriteLine("Opening the service host");  
                // Open the service host to begin polling  
                srvHost.Open();  
  
                // Wait to receive request  
                Console.WriteLine("\nPolling started. Returned records will be written to the console.");  
                Console.WriteLine("Hit <RETURN> to stop polling");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an Oracle Error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (srvHost.State == CommunicationState.Opened)  
                    srvHost.Close();  
                else  
                    srvHost.Abort();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="59c62-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="59c62-200">See Also</span></span>  
 [<span data-ttu-id="59c62-201">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="59c62-201">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)