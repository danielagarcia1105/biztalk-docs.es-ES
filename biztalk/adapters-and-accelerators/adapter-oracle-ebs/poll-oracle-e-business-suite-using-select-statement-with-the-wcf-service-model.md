---
title: Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 521d58e4-73b1-48a8-9a0a-9e733386c1b5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8484acc15d2328ab444a8df6e55dc0ff952899a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000701"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model"></a><span data-ttu-id="c8ef2-102">Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="c8ef2-102">Poll Oracle E-Business Suite using SELECT statement with the WCF service model</span></span>
<span data-ttu-id="c8ef2-103">Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos periódica mediante el uso de una instrucción SELECT para las tablas de interfaz un sondeo continuo, interfaz vistas, tablas y vistas de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="c8ef2-104">Puede especificar una instrucción SELECT como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="c8ef2-105">También puede especificar un bloque de código posterior a la encuesta PL/SQL que el adaptador se ejecuta después de ejecutar la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  

 <span data-ttu-id="c8ef2-106">Para habilitar el sondeo, debe especificar ciertas propiedades de enlace como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span>  <span data-ttu-id="c8ef2-107">Para obtener más información acerca de cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="c8ef2-108">Configuración de una operación de sondeo con enlazar propiedades de adaptador para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="c8ef2-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="c8ef2-109">La siguiente tabla resume el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mensajes de cambio de propiedades de enlace que usan para configurar el adaptador para recibir datos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="c8ef2-110">Debe especificar estas propiedades de enlace al ejecutar la aplicación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-110">You must specify these binding properties while running the polling application.</span></span>  


|         <span data-ttu-id="c8ef2-111">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="c8ef2-111">Binding Property</span></span>         |                                                                                                                                                                                                                            <span data-ttu-id="c8ef2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8ef2-112">Description</span></span>                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="c8ef2-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="c8ef2-113">**InboundOperationType**</span></span>     |                                                                                                                                                                          <span data-ttu-id="c8ef2-114">Especifica si desea realizar **sondeo** o **notificación** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="c8ef2-115">El valor predeterminado es **sondeo**.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-115">Default is **Polling**.</span></span>                                                                                                                                                                          |
| <span data-ttu-id="c8ef2-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="c8ef2-116">**PolledDataAvailableStatement**</span></span> |                                                                                                             <span data-ttu-id="c8ef2-117">Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="c8ef2-118">Solo si hay un registro, la instrucción SELECT especifique para la **PollingInput** se ejecutará el enlace de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>                                                                                                              |
|       <span data-ttu-id="c8ef2-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="c8ef2-119">**PollingInterval**</span></span>        | <span data-ttu-id="c8ef2-120">Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="c8ef2-121">El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-121">The default is 30 seconds.</span></span> <span data-ttu-id="c8ef2-122">El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="c8ef2-123">Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span> |
|         <span data-ttu-id="c8ef2-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="c8ef2-124">**PollingInput**</span></span>         |                         <span data-ttu-id="c8ef2-125">Especifica la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-125">Specifies the polling statement.</span></span> <span data-ttu-id="c8ef2-126">Para sondear con una instrucción SELECT, debe especificar una instrucción SELECT para esta propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="c8ef2-127">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-127">The default is null.</span></span><br /><br /> <span data-ttu-id="c8ef2-128">Debe especificar un valor para **PollingInput** enlace de propiedad para habilitar el sondeo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="c8ef2-129">Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>                          |
|        <span data-ttu-id="c8ef2-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="c8ef2-130">**PollingAction**</span></span>         |                                                                                                                <span data-ttu-id="c8ef2-131">Especifica la acción para la operación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="c8ef2-132">Puede determinar la acción de sondeo de la interfaz de servicio generada para la operación mediante la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8ef2-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>                                                                                                                |
|      <span data-ttu-id="c8ef2-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="c8ef2-133">**PostPollStatement**</span></span>       |                                                                                                                                                                  <span data-ttu-id="c8ef2-134">Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingInput** propiedad de enlace se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>                                                                                                                                                                  |
|      <span data-ttu-id="c8ef2-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="c8ef2-135">**PollWhileDataFound**</span></span>      |                                    <span data-ttu-id="c8ef2-136">Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y la instrucción de sondeo, se ejecuta continuamente si hay datos disponibles en la tabla que se sondea.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="c8ef2-137">Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="c8ef2-138">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-138">Default is false.</span></span>                                     |

 <span data-ttu-id="c8ef2-139">Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="c8ef2-140">Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear la base de datos de Oracle, siga leyendo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read further.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="c8ef2-141">Cómo este tema muestra el sondeo</span><span class="sxs-lookup"><span data-stu-id="c8ef2-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="c8ef2-142">En este tema, para demostrar cómo el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de datos cambia mensajes mediante las instrucciones SELECT, sondea la **MS_SAMPLE_EMPLOYEE** tabla de interfaz en el **biblioteca de objetos de aplicación**aplicación.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="c8ef2-143">Esta tabla se crea al ejecutar el script de create_apps_artifacts.sql proporcionado con los ejemplos para crear estos objetos en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  

 <span data-ttu-id="c8ef2-144">Para demostrar una operación de sondeo, llevamos a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8ef2-144">To demonstrate a polling operation, we do the following:</span></span>  

-   <span data-ttu-id="c8ef2-145">Especifique una instrucción SELECT para la **PolledDataAvailableStatement** enlaza la propiedad para determinar donde la interfaz tabla sondea (MS_SAMPLE_EMPLOYEE) tiene los datos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="c8ef2-146">En este ejemplo, puede establecer esta propiedad de enlace como:</span><span class="sxs-lookup"><span data-stu-id="c8ef2-146">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="c8ef2-147">Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla de interfaz MS_SAMPLE_EMPLOYEE tiene algunos registros.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  

-   <span data-ttu-id="c8ef2-148">Especifique una instrucción SELECT para la **PollingInput** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="c8ef2-149">Esta instrucción recupera todas las filas de la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c8ef2-150">En este ejemplo, puede establecer esta propiedad de enlace como:</span><span class="sxs-lookup"><span data-stu-id="c8ef2-150">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="c8ef2-151">Para obtener información acerca de la cláusula FOR UPDATE en la instrucción SELECT, vea [recibir los mensajes basados en sondeos de cambio de datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  

-   <span data-ttu-id="c8ef2-152">Especifique una instrucción DELETE como parte de la **PostPollStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="c8ef2-153">Esta instrucción eliminará todos los datos de tabla de la interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c8ef2-154">En este ejemplo, puede establecer esta propiedad de enlace como:</span><span class="sxs-lookup"><span data-stu-id="c8ef2-154">In this example, you can set this binding property as:</span></span>  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="c8ef2-155">Tras esto, la próxima vez que la instrucción especificada para **PollingInput** será ejecuta, no capturará todos los datos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  

-   <span data-ttu-id="c8ef2-156">Hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE, no obtendrá ningún mensaje de sondeo por lo que debe volver a llenar la tabla de interfaz MS_SAMPLE_EMPLOYEE con nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="c8ef2-157">Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="c8ef2-158">Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  

## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="c8ef2-159">Configuración de sondeo en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="c8ef2-159">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="c8ef2-160">Para sondear una tabla de interfaz mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="c8ef2-160">To poll an interface table using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF service model, you must:</span></span>  

- <span data-ttu-id="c8ef2-161">Generar un contrato de servicio WCF (interfaz) para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-161">Generate a WCF service contract (interface) for the **Poll** operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c8ef2-162">Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8ef2-162">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

- <span data-ttu-id="c8ef2-163">Implementar un servicio WCF desde esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-163">Implement a WCF service from this interface.</span></span>  

- <span data-ttu-id="c8ef2-164">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-164">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="c8ef2-165">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-165">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="c8ef2-166">Los ejemplos de este tema sondean la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-166">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c8ef2-167">Se proporciona un script para generar la tabla con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-167">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="c8ef2-168">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-168">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="c8ef2-169">Un ejemplo, **SelectPolling_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-169">A sample, **SelectPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="c8ef2-170">El contrato de servicio WCF y la clase</span><span class="sxs-lookup"><span data-stu-id="c8ef2-170">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="c8ef2-171">Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y la compatibilidad con las clases para el **sondeo** operación.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-171">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="c8ef2-172">Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-172">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="c8ef2-173">El contrato de servicio WCF (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8ef2-173">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="c8ef2-174">El código siguiente muestra el contrato de servicio WCF (interfaz) generado para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-174">The following code shows the WCF service contract (interface) generated for the **Poll** operation on MS_SAMPLE_EMPLOYEE interface table.</span></span>  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE")]  
public interface InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE")]  
    void Poll(Poll request);  
}  
```  

### <a name="the-message-contracts"></a><span data-ttu-id="c8ef2-175">Los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="c8ef2-175">The Message Contracts</span></span>  
 <span data-ttu-id="c8ef2-176">La siguiente es el contrato de mensaje para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-176">Following is the message contract for the **Poll** operation on MS_SAMPLE_EMPLOYEE interface table.</span></span>  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Poll", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
    "_EMPLOYEE", IsWrapped=true)]  
public partial class Poll {  

    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
        "_EMPLOYEE", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA;  

    public Poll() {  
    }  

    public Poll(schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA) {  
        this.DATA = DATA;  
    }  
}  
```  

### <a name="wcf-service-class"></a><span data-ttu-id="c8ef2-177">Clase de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="c8ef2-177">WCF Service Class</span></span>  
 <span data-ttu-id="c8ef2-178">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF implementa el contrato de servicio (interfaz).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-178">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="c8ef2-179">El nombre del archivo es OracleEBSBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-179">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="c8ef2-180">Puede insertar la lógica para procesar el **sondeo** operación directamente en esta clase.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-180">You can insert the logic to process the **Poll** operation directly into this class.</span></span> <span data-ttu-id="c8ef2-181">El código siguiente muestra la clase de servicio WCF generada por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8ef2-181">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

```  
namespace OracleEBSBindingNamespace {  

    public class OracleEBSBindingService : InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Poll(Poll request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receiving-inbound-messages-for-the-poll-operation-using-a-select-statement"></a><span data-ttu-id="c8ef2-182">Recibir mensajes de entrada para la operación de sondeo con una instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="c8ef2-182">Receiving Inbound Messages for the Poll Operation Using a SELECT Statement</span></span>  
 <span data-ttu-id="c8ef2-183">Esta sección proporciona instrucciones sobre cómo escribir una aplicación de .NET para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8ef2-183">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

#### <a name="to-receive-polling-messages-using-a-select-statement"></a><span data-ttu-id="c8ef2-184">Para recibir mensajes de sondeo mediante una instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="c8ef2-184">To receive polling messages using a SELECT statement</span></span>  

1. <span data-ttu-id="c8ef2-185">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y clases auxiliares para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-185">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Poll** operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c8ef2-186">Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-186">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="c8ef2-187">También puede especificar las propiedades de enlace al generar las clases auxiliares y de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-187">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="c8ef2-188">Esto garantiza que están establecidas correctamente en el archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-188">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="c8ef2-189">Implementar un servicio WCF desde las clases auxiliares y la interfaz generada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-189">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="c8ef2-190">El **sondeo** método de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la **sondeo** operación; en caso contrario, el método no lo hace devolver nada.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-190">The **Poll** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Poll** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="c8ef2-191">Debe atributo la clase de servicio WCF como sigue:</span><span class="sxs-lookup"><span data-stu-id="c8ef2-191">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="c8ef2-192">Dentro de la **sondeo** método, puede implementar la lógica de aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-192">Within the **Poll** method, you can implement your application logic directly.</span></span> <span data-ttu-id="c8ef2-193">Esta clase puede encontrarse en OracleEBSBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-193">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="c8ef2-194">Este código en este ejemplo Sub clases el **OracleEBSBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-194">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="c8ef2-195">En este código, el mensaje de sondeo recibe y se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-195">In this code, the polling message received and is written to the console.</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
   {  
       public override void Poll(Poll request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
           for (int i = 0; i < request.DATA.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.DATA[i].EMP_NO,  
               request.DATA[i].NAME,  
               request.DATA[i].DESIGNATION,  
               request.DATA[i].SALARY);  
           }  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. <span data-ttu-id="c8ef2-196">Debe implementar la clase siguiente para evitar pasar las credenciales como parte del URI.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-196">You must implement the following class to avoid passing credentials as part of the URI.</span></span> <span data-ttu-id="c8ef2-197">En la última parte de la aplicación, se creará instancias de esta clase para pasar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-197">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  

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

4. <span data-ttu-id="c8ef2-198">Crear un **OracleEBSBinding** y configurar la operación de sondeo mediante la especificación de las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-198">Create an **OracleEBSBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="c8ef2-199">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-199">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="c8ef2-200">Como mínimo, debe especificar el **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, y **PollingAction**propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-200">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span>  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

5. <span data-ttu-id="c8ef2-201">Dado que sondean una tabla de interfaz, también debe establecer el contexto de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-201">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="c8ef2-202">Para obtener más información sobre el contexto de la aplicación y las propiedades de enlace necesarias para el contexto de la aplicación de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="c8ef2-202">For more information about application context and the binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  

6. <span data-ttu-id="c8ef2-203">Especifique las credenciales de Oracle E-Business Suite creando el **PollingCredentials** clase creada en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-203">Specify Oracle E-Business Suite credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

7. <span data-ttu-id="c8ef2-204">Cree una instancia del servicio WCF que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-204">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

8. <span data-ttu-id="c8ef2-205">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio de WCF y un URI de conexión de base.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-205">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="c8ef2-206">El URI de conexión base no puede contener el identificador de entrada, si se especifica.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-206">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="c8ef2-207">También se deben pasar las credenciales aquí.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-207">You must also pass the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

9. <span data-ttu-id="c8ef2-208">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-208">Add a service endpoint to the service host.</span></span> <span data-ttu-id="c8ef2-209">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="c8ef2-209">To do this:</span></span>  

   - <span data-ttu-id="c8ef2-210">Utilice el enlace creado en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-210">Use the binding created in step 4.</span></span>  

   - <span data-ttu-id="c8ef2-211">Especifique un URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-211">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   - <span data-ttu-id="c8ef2-212">Especifique el contrato como "InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE" para sondear la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-212">Specify the contract as "InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE" to poll the MS_SAMPLE_EMPLOYEE interface table.</span></span>  

     ```  
     // Add service endpoint: be sure to specify InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE as the contract  
     Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
     serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
     ```  

10. <span data-ttu-id="c8ef2-213">Para recibir datos de sondeo, abra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-213">To receive polling data, open the service host.</span></span> <span data-ttu-id="c8ef2-214">El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-214">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

11. <span data-ttu-id="c8ef2-215">Para finalizar el sondeo, cierre el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-215">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="c8ef2-216">El adaptador seguirá sondeando hasta que se cierra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-216">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="c8ef2-217">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8ef2-217">Example</span></span>  
 <span data-ttu-id="c8ef2-218">El ejemplo siguiente muestra una aplicación de sondeo que sondea la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-218">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c8ef2-219">El **PollingInput** propiedad contiene la instrucción select que lee todos los datos de la tabla MS_SAMPLE_EMPLOYEE y la instrucción de sondeo de envío, elimina todos los datos de la misma tabla.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-219">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="c8ef2-220">El primer mensaje de sondeo proporciona todos los registros de la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-220">The first polling message gives all the records from the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c8ef2-221">Mensajes de sondeo subsiguiente no contendrá ningún registro porque la instrucción de sondeo de envío elimina los registros.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-221">Subsequent polling messages will not contain any records because the post poll statement deletes the records.</span></span> <span data-ttu-id="c8ef2-222">Hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE, no obtendrá ningún mensaje de sondeo.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-222">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages.</span></span> <span data-ttu-id="c8ef2-223">Por lo tanto, debe volver a llenar la tabla de interfaz MS_SAMPLE_EMPLOYEE con nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-223">So, you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="c8ef2-224">Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-224">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="c8ef2-225">Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-225">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="c8ef2-226">El adaptador seguirá sondeando hasta que cierre el host de servicio presionando `<RETURN>`.</span><span class="sxs-lookup"><span data-stu-id="c8ef2-226">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

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

namespace SelectPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Poll(Poll request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
            for (int i = 0; i < request.DATA.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.DATA[i].EMP_NO,  
                request.DATA[i].NAME,  
                request.DATA[i].DESIGNATION,  
                request.DATA[i].SALARY);  
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
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "myOracleEBSUserName";  
                binding.OraclePassword = "myOracleEBSPassword";  
                binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  

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
                serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
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

## <a name="see-also"></a><span data-ttu-id="c8ef2-227">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8ef2-227">See Also</span></span>  
 [<span data-ttu-id="c8ef2-228">Sondear Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="c8ef2-228">Poll Oracle E-Business Suite using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)