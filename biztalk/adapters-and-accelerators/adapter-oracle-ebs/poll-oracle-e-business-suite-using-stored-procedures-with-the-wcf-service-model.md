---
title: Utilizar procedimientos almacenados con el modelo de servicio WCF de sondeo Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47dcb866-9161-4b28-9481-2761794ce805
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3fb7ebcbccb1f0edb3370176192f55f0db4985a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967722"
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model"></a><span data-ttu-id="36339-102">Sondeo Oracle E-Business Suite mediante procedimientos almacenados con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="36339-102">Poll Oracle E-Business Suite using stored procedures with the WCF service model</span></span>
<span data-ttu-id="36339-103">Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos periódicos mediante procedimientos almacenados que éstos sondeen periódicamente la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="36339-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using stored procedures to periodically poll the Oracle database.</span></span> <span data-ttu-id="36339-104">Puede especificar un procedimiento almacenado como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="36339-104">You can specify a stored procedure as a polling statement that the adapter executes periodically to poll the Oracle database.</span></span>  
  
 <span data-ttu-id="36339-105">Para habilitar el sondeo, debe especificar ciertas propiedades de enlace como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="36339-105">To enable polling, you must specify certain binding properties as described in this topic.</span></span>  <span data-ttu-id="36339-106">Para obtener más información sobre cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span><span class="sxs-lookup"><span data-stu-id="36339-106">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="36339-107">Configuración de una operación de sondeo con propiedades de enlace adaptador para Oracle E-Business</span><span class="sxs-lookup"><span data-stu-id="36339-107">Configuring a Polling Operation with Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="36339-108">La siguiente tabla resume el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] propiedades de enlace que se utiliza para configurar el adaptador para recibir mensajes de cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="36339-108">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="36339-109">Debe especificar estas propiedades de enlace al ejecutar la aplicación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="36339-109">You must specify these binding properties while running the polling application.</span></span>  
  
|<span data-ttu-id="36339-110">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="36339-110">Binding Property</span></span>|<span data-ttu-id="36339-111">Description</span><span class="sxs-lookup"><span data-stu-id="36339-111">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="36339-112">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="36339-112">**InboundOperationType**</span></span>|<span data-ttu-id="36339-113">Especifica si desea realizar un **sondeo** o **notificación** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="36339-113">Specifies whether you want to perform a **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="36339-114">Valor predeterminado es **sondeo**.</span><span class="sxs-lookup"><span data-stu-id="36339-114">Default is **Polling**.</span></span>|  
|<span data-ttu-id="36339-115">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="36339-115">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="36339-116">Especifica la instrucción SQL que se ejecuta el adaptador para determinar si los datos están disponibles para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="36339-116">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="36339-117">Sólo si hay un registro, el procedimiento almacenado que especificó para la **PollingInput** se va a ejecutar la propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-117">Only if a record is available, the stored procedure you specified for the **PollingInput** binding property will be executed.</span></span>|  
|<span data-ttu-id="36339-118">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="36339-118">**PollingInterval**</span></span>|<span data-ttu-id="36339-119">Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se ejecuta la instrucción especificada para la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-119">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="36339-120">El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="36339-120">The default is 30 seconds.</span></span> <span data-ttu-id="36339-121">El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos.</span><span class="sxs-lookup"><span data-stu-id="36339-121">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="36339-122">Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="36339-122">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="36339-123">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="36339-123">**PollingInput**</span></span>|<span data-ttu-id="36339-124">Especifica la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="36339-124">Specifies the polling statement.</span></span> <span data-ttu-id="36339-125">Para sondear mediante un procedimiento almacenado, debe especificar el mensaje de solicitud completo para esta propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-125">To poll using a stored procedure, you must specify the entire request message for this binding property.</span></span> <span data-ttu-id="36339-126">El mensaje de solicitud debe ser el mismo que envíe al adaptador para invocar el procedimiento almacenado como una operación de salida.</span><span class="sxs-lookup"><span data-stu-id="36339-126">The request message must be the same that you send to the adapter for invoking the stored procedure as an outbound operation.</span></span> <span data-ttu-id="36339-127">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="36339-127">The default is null.</span></span><br /><br /> <span data-ttu-id="36339-128">Debe especificar un valor para **PollingInput** propiedad para habilitar el sondeo de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="36339-129">Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>|  
|<span data-ttu-id="36339-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="36339-130">**PollingAction**</span></span>|<span data-ttu-id="36339-131">Especifica la acción para la operación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="36339-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="36339-132">Puede determinar la acción de sondeo de la interfaz de servicio generada para la operación con el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36339-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>|  
|<span data-ttu-id="36339-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="36339-133">**PostPollStatement**</span></span>|<span data-ttu-id="36339-134">Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingInput** propiedad de enlace se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="36339-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>|  
|<span data-ttu-id="36339-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="36339-135">**PollWhileDataFound**</span></span>|<span data-ttu-id="36339-136">Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y ejecuta continuamente la instrucción de sondeo, si los datos están disponibles en la tabla que se va a sondear.</span><span class="sxs-lookup"><span data-stu-id="36339-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="36339-137">Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado.</span><span class="sxs-lookup"><span data-stu-id="36339-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="36339-138">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="36339-138">Default is false.</span></span>|  
  
 <span data-ttu-id="36339-139">Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="36339-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="36339-140">Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] sondear, lea las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="36339-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll, read the following sections.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="36339-141">Cómo este tema muestra el sondeo</span><span class="sxs-lookup"><span data-stu-id="36339-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="36339-142">En este tema, para demostrar cómo [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de mensajes mediante procedimientos almacenados, usas la GET_ACTIVITYS de cambio de datos procedimiento almacenado para sondear la tabla ACCOUNTACTIVITY en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="36339-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using stored procedures, you use the GET_ACTIVITYS stored procedure to poll the ACCOUNTACTIVITY table in the Oracle database.</span></span> <span data-ttu-id="36339-143">Este procedimiento almacenado está disponible con el paquete ACCOUNT_PKG.</span><span class="sxs-lookup"><span data-stu-id="36339-143">This stored procedure is available with the ACCOUNT_PKG package.</span></span> <span data-ttu-id="36339-144">Puede ejecutar los scripts SQL que se proporciona con los ejemplos para crear estos objetos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="36339-144">You can run the SQL scripts provided with the samples to create these objects in the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36339-145">El ejemplo de sondeos de este tema la ACCOUNTACTIVITY de tabla, que es una tabla de base de datos creada mediante la ejecución de las secuencias de comandos que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="36339-145">The example in this topic polls the ACCOUNTACTIVITY table, which is a base database table created by running the scripts provided with the samples.</span></span> <span data-ttu-id="36339-146">Debe realizar procesos similares tal como se describe en este tema para sondear cualquier otra tabla, incluidas las tablas de interfaz.</span><span class="sxs-lookup"><span data-stu-id="36339-146">You must perform similar procedures as described in this topic to poll any other table, including interface tables.</span></span>  
  
 <span data-ttu-id="36339-147">Para mostrar una operación de sondeo, llevamos a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="36339-147">To demonstrate a polling operation, we do the following:</span></span>  
  
-   <span data-ttu-id="36339-148">Especifique una instrucción SELECT para la **PolledDataAvailableStatement** propiedad para determinar donde la tabla se sondea, (ACCOUNTACTIVITY) de enlace tiene los datos.</span><span class="sxs-lookup"><span data-stu-id="36339-148">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the table being polled (ACCOUNTACTIVITY) has any data.</span></span> <span data-ttu-id="36339-149">En este ejemplo, puede establecer esta propiedad de enlace como:</span><span class="sxs-lookup"><span data-stu-id="36339-149">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  
  
     <span data-ttu-id="36339-150">Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla ACCOUNTACTIVITY tiene algunos registros.</span><span class="sxs-lookup"><span data-stu-id="36339-150">This ensures that the adapter executes the polling statement only when the ACCOUNTACTIVITY table has some records.</span></span>  
  
-   <span data-ttu-id="36339-151">Ejecutar un procedimiento almacenado, GET_ACTIVITYS, proporcionando el mensaje de solicitud como parte de la **PollingInput** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-151">Execute a stored procedure, GET_ACTIVITYS, by providing the request message as part of the **PollingInput** binding property.</span></span> <span data-ttu-id="36339-152">Este procedimiento almacenado recuperará todas las filas de la tabla ACCOUNTACTIVITY y aparecerá un mensaje de respuesta desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="36339-152">This stored procedure will retrieve all the rows in the ACCOUNTACTIVITY table and you will get a response message from the adapter.</span></span>  
  
-   <span data-ttu-id="36339-153">Ejecutar un bloque de PL/SQL como parte de la **PostPollStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-153">Execute a PL/SQL block as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="36339-154">Esta instrucción moverá todos los datos de tabla ACCOUNTACTIVITY a otra tabla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="36339-154">This statement will move all data from ACCOUNTACTIVITY table to another table in the database.</span></span> <span data-ttu-id="36339-155">Cuando esto ocurra, la próxima vez que **PollingInput** es ejecutar, no capturará los datos y, por tanto, el procedimiento almacenado de GET_ACTIVITYS devolverá un mensaje de respuesta vacío.</span><span class="sxs-lookup"><span data-stu-id="36339-155">After this happens, the next time **PollingInput** is executed, it will not fetch any data and hence the GET_ACTIVITYS stored procedure will return an empty response message.</span></span>  
  
-   <span data-ttu-id="36339-156">Hasta que se agregan más datos a la tabla ACCOUNTACTIVITY, se seguirá pudiendo obtener mensajes de respuesta vacío por lo que debe volver a rellenar la tabla ACCOUNTACTIVITY con nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="36339-156">Until more data is added to the ACCOUNTACTIVITY table, you will continue to get empty response messages so you must repopulate the ACCOUNTACTIVITY table with new records.</span></span> <span data-ttu-id="36339-157">Puede hacerlo ejecutando el script more_activity_data.sql proporcionado con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="36339-157">You can do so by running the more_activity_data.sql script provided with the samples.</span></span> <span data-ttu-id="36339-158">Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.</span><span class="sxs-lookup"><span data-stu-id="36339-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="36339-159">Configuración de sondeo en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="36339-159">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="36339-160">Para sondear mediante procedimientos almacenados con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="36339-160">To poll using stored procedures with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="36339-161">Generar un contrato de servicio WCF (interfaz) para el procedimiento almacenado con la que se va a sondear.</span><span class="sxs-lookup"><span data-stu-id="36339-161">Generate a WCF service contract (interface) for the stored procedure using which you are going to poll.</span></span> <span data-ttu-id="36339-162">En este ejemplo, debe generar el contrato de servicio WCF para la **GET_ACTIVITYS** procedimiento almacenado como una operación de entrada.</span><span class="sxs-lookup"><span data-stu-id="36339-162">For this example, you must generate the WCF service contract for the **GET_ACTIVITYS** stored procedure as an inbound operation.</span></span> <span data-ttu-id="36339-163">Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36339-163">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="36339-164">Implementar un servicio WCF de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="36339-164">Implement a WCF service from this interface.</span></span>  
  
-   <span data-ttu-id="36339-165">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="36339-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="36339-166">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="36339-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="36339-167">Los ejemplos de este sondeo tema la tabla de base de datos ACCOUNTACTIVITY mediante el GET_ACTIVITYS el procedimiento almacenan.</span><span class="sxs-lookup"><span data-stu-id="36339-167">The examples in this topic poll the ACCOUNTACTIVITY database table using the GET_ACTIVITYS stored procedure.</span></span> <span data-ttu-id="36339-168">Una secuencia de comandos para generar la tabla y el procedimiento almacenado se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="36339-168">A script to generate the table and the stored procedure is supplied with the samples.</span></span> <span data-ttu-id="36339-169">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="36339-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="36339-170">Obtener un ejemplo, **StoredProcPolling_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="36339-170">A sample, **StoredProcPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="36339-171">El contrato de servicio WCF y la clase</span><span class="sxs-lookup"><span data-stu-id="36339-171">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="36339-172">Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y las clases para que admite la **GET_ACTIVITYS** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="36339-172">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **GET_ACTIVITYS** inbound operation.</span></span> <span data-ttu-id="36339-173">Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="36339-173">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="36339-174">El contrato de servicio WCF (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36339-174">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="36339-175">El código siguiente muestra el contrato de servicio WCF (interfaz) que se genera para la **GET_ACTIVITYS** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="36339-175">The following code shows the WCF service contract (interface) generated for the **GET_ACTIVITYS** inbound operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="PollingPackageApis_APPS_ACCOUNT_PKG")]  
public interface PollingPackageApis_APPS_ACCOUNT_PKG {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS")]  
    void GET_ACTIVITYS(GET_ACTIVITYS request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="36339-176">Los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="36339-176">The Message Contracts</span></span>  
 <span data-ttu-id="36339-177">Aquí te mostramos el contrato de mensaje para la **GET_ACTIVITYS** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="36339-177">Following is the message contract for the **GET_ACTIVITYS** inbound operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="GET_ACTIVITYS", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
    "G", IsWrapped=true)]  
public partial class GET_ACTIVITYS {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
        "G", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS;  
  
    public GET_ACTIVITYS() {  
    }  
  
    public GET_ACTIVITYS(schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS) {  
        this.OUTRECS = OUTRECS;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="36339-178">Clase de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="36339-178">WCF Service Class</span></span>  
 <span data-ttu-id="36339-179">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF que implementa el contrato de servicio (interfaz).</span><span class="sxs-lookup"><span data-stu-id="36339-179">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="36339-180">El nombre del archivo es OracleEBSBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="36339-180">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="36339-181">Puede insertar la lógica para procesar el **GET_ACTIVITYS** operación directamente en esta clase.</span><span class="sxs-lookup"><span data-stu-id="36339-181">You can insert the logic to process the **GET_ACTIVITYS** operation directly into this class.</span></span> <span data-ttu-id="36339-182">El código siguiente muestra la clase de servicio WCF generada por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36339-182">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleEBSBindingNamespace {  
  
    public class OracleEBSBindingService : PollingPackageApis_APPS_ACCOUNT_PKG {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void GET_ACTIVITYS(GET_ACTIVITYS request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-inbound-messages-for-polling-using-a-stored-procedure"></a><span data-ttu-id="36339-183">Recibir mensajes de entrada para el sondeo de mediante un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="36339-183">Receiving Inbound Messages For Polling Using a Stored Procedure</span></span>  
 <span data-ttu-id="36339-184">Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36339-184">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-using-a-stored-procedure"></a><span data-ttu-id="36339-185">Para recibir mensajes de sondeo mediante un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="36339-185">To receive polling messages using a stored procedure</span></span>  
  
1.  <span data-ttu-id="36339-186">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y las clases auxiliares para el **GET_ACTIVITYS** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="36339-186">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **GET_ACTIVITYS** inbound operation.</span></span> <span data-ttu-id="36339-187">Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="36339-187">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="36339-188">También puede especificar las propiedades de enlace al generar las clases de contrato y el Ayudante de servicio.</span><span class="sxs-lookup"><span data-stu-id="36339-188">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="36339-189">Esto garantiza que están establecidas correctamente en el archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="36339-189">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="36339-190">Implementar un servicio WCF desde las clases de interfaz y auxiliar generado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="36339-190">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="36339-191">El **GET_ACTIVITYS** método de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la **GET_ACTIVITYS** operación; en caso contrario el método no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="36339-191">The **GET_ACTIVITYS** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **GET_ACTIVITYS** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="36339-192">La clase de servicio WCF debe atributo como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="36339-192">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="36339-193">En el **GET_ACTIVITYS** método, puede implementar la lógica de aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="36339-193">Within the **GET_ACTIVITYS** method, you can implement your application logic directly.</span></span> <span data-ttu-id="36339-194">Esta clase se puede encontrar en OracleEBSBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="36339-194">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="36339-195">Este código de este ejemplo Sub-clases el **OracleEBSBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="36339-195">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="36339-196">En este código, el mensaje de sondeo recibe y se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="36339-196">In this code, the polling message received and is written to the console.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
            for (int i = 0; i < request.OUTRECS.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.OUTRECS[i].TID,  
                request.OUTRECS[i].ACCOUNT,  
                request.OUTRECS[i].AMOUNT,  
                request.OUTRECS[i].PROCESSED);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="36339-197">Debe implementar la clase siguiente para evitar pasar las credenciales como parte del URI.</span><span class="sxs-lookup"><span data-stu-id="36339-197">You must implement the following class to avoid passing credentials as part of the URI.</span></span> <span data-ttu-id="36339-198">En la última parte de la aplicación, se creará una instancia de esta clase para pasar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="36339-198">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
    ```  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
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
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="36339-199">Crear un **OracleEBSBinding** y configure la operación de sondeo mediante la especificación de las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-199">Create an **OracleEBSBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="36339-200">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="36339-200">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="36339-201">Como mínimo, debe especificar el **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, y **PollingAction**propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-201">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
    binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
    binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="36339-202">Tenga en cuenta que el valor de la **PollingInput** propiedad de enlace contiene el mensaje de solicitud para invocar la **GET_ACTIVITYS** procedimiento almacenado como una operación de salida.</span><span class="sxs-lookup"><span data-stu-id="36339-202">Note that the value for the **PollingInput** binding property contains the request message for invoking the **GET_ACTIVITYS** stored procedure as an outbound operation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="36339-203">En este ejemplo, porque se sondear una tabla de base de datos, es necesario establecer el contexto de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="36339-203">In this example, because you are polling a database table, you do not need to set the applications context.</span></span> <span data-ttu-id="36339-204">Sin embargo, si se sondear una tabla de interfaz, debe establecer el contexto de las aplicaciones mediante la especificación de la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="36339-204">However, if you were polling an interface table, you must set the applications context by specifying the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="36339-205">Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="36339-205">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
5.  <span data-ttu-id="36339-206">Especifique las credenciales de Oracle E-Business Suite creando el **PollingCredentials** clase creada en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="36339-206">Specify Oracle E-Business Suite credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  <span data-ttu-id="36339-207">Cree una instancia del servicio WCF que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="36339-207">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  <span data-ttu-id="36339-208">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio WCF y un URI de conexión base.</span><span class="sxs-lookup"><span data-stu-id="36339-208">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="36339-209">El URI de conexión base no puede contener el identificador de entrada, si se especifica.</span><span class="sxs-lookup"><span data-stu-id="36339-209">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="36339-210">También debe pasar las credenciales aquí.</span><span class="sxs-lookup"><span data-stu-id="36339-210">You must also pass the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  <span data-ttu-id="36339-211">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="36339-211">Add a service endpoint to the service host.</span></span> <span data-ttu-id="36339-212">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="36339-212">To do this:</span></span>  
  
    -   <span data-ttu-id="36339-213">Utilice el enlace creado en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="36339-213">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="36339-214">Especifica una URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.</span><span class="sxs-lookup"><span data-stu-id="36339-214">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="36339-215">Especifique el contrato como "PollingPackageApis_APPS_ACCOUNT_PKG" para sondear la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="36339-215">Specify the contract as "PollingPackageApis_APPS_ACCOUNT_PKG" to poll the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify PollingPackageApis_APPS_ACCOUNT_PKG as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
    ```  
  
9. <span data-ttu-id="36339-216">Para recibir datos de sondeo, abra el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="36339-216">To receive polling data, open the service host.</span></span> <span data-ttu-id="36339-217">El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="36339-217">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. <span data-ttu-id="36339-218">Para finalizar el sondeo, cierre el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="36339-218">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="36339-219">El adaptador seguirá sondea hasta que se cierra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="36339-219">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="36339-220">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36339-220">Example</span></span>  
 <span data-ttu-id="36339-221">En el ejemplo siguiente se muestra una aplicación de sondeo que sondea la tabla de base de datos ACCOUNTACTIVITY mediante el GET_ACTIVITYS de procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="36339-221">The following example shows a polling application that polls the ACCOUNTACTIVITY database table using the GET_ACTIVITYS stored procedure.</span></span> <span data-ttu-id="36339-222">El **PollingInput** propiedad de enlace contiene el mensaje de solicitud para invocar el procedimiento almacenado de GET_ACTIVITYS que lee todos los datos de la tabla ACCOUNTACTIVITY y la instrucción de sondeo de envío pasa todos los datos de ACCOUNTACTIVITY en la tabla ACTIVITYHISTORY.</span><span class="sxs-lookup"><span data-stu-id="36339-222">The **PollingInput** binding property contains the request message to invoke the GET_ACTIVITYS stored procedure that reads all the data from the ACCOUNTACTIVITY table and the post poll statement moves all the data from ACCOUNTACTIVITY to ACTIVITYHISTORY table.</span></span>  
  
 <span data-ttu-id="36339-223">El primer mensaje de sondeo proporciona todos los registros de la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="36339-223">The first polling message gives all the records from the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="36339-224">Mensajes de sondeo subsiguiente no contendrá ningún registro porque la instrucción de sondeo de envío elimina los registros.</span><span class="sxs-lookup"><span data-stu-id="36339-224">Subsequent polling messages will not contain any records because the post poll statement deletes the records.</span></span> <span data-ttu-id="36339-225">Hasta que se agregan más datos a la tabla ACCOUNTACTIVITY, no obtendrá ningún mensaje de sondeo por lo que debe volver a rellenar la tabla ACCOUNTACTIVITY con nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="36339-225">Until more data is added to the ACCOUNTACTIVITY table, you will not get any polling messages so you must repopulate the ACCOUNTACTIVITY table with new records.</span></span> <span data-ttu-id="36339-226">Puede hacerlo ejecutando el script more_activity_data.sql proporcionado con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="36339-226">You can do so by running the more_activity_data.sql script provided with the samples.</span></span>  
  
 <span data-ttu-id="36339-227">Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.</span><span class="sxs-lookup"><span data-stu-id="36339-227">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="36339-228">El adaptador seguirá sondea hasta que cierre el host de servicio presionando `<RETURN>`.</span><span class="sxs-lookup"><span data-stu-id="36339-228">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
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
  
namespace StoredProcPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
            for (int i = 0; i < request.OUTRECS.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.OUTRECS[i].TID,  
                request.OUTRECS[i].ACCOUNT,  
                request.OUTRECS[i].AMOUNT,  
                request.OUTRECS[i].PROCESSED);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
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
            ClientCredentials clone = new PollingCredentials();  
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
                Console.WriteLine("Press any key to start polling...");  
                Console.ReadLine();  
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
                binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
                binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Polling started...");  
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
  
## <a name="see-also"></a><span data-ttu-id="36339-229">Vea también</span><span class="sxs-lookup"><span data-stu-id="36339-229">See Also</span></span>  
 [<span data-ttu-id="36339-230">Sondeo Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="36339-230">Poll Oracle E-Business Suite using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)