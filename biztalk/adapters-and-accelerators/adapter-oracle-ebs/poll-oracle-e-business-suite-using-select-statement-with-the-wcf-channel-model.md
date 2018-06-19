---
title: Sondeo Oracle E-Business Suite con la instrucción SELECT con el modelo del canal WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495b9010-856f-4782-bd19-1522bc3eb950
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1164cb59bf7fe0e168834f60364cd82f871b3ae0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965746"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model"></a><span data-ttu-id="aa441-102">Sondeo Oracle E-Business Suite con la instrucción SELECT con el modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="aa441-102">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>
<span data-ttu-id="aa441-103">Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos periódicos utilizando una instrucción SELECT para las tablas de interfaz un sondeo continuo, interfaz vistas, tablas y vistas de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="aa441-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="aa441-104">Puede especificar una instrucción SELECT como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="aa441-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="aa441-105">También puede especificar un bloque de código de PL/SQL de sondeo posterior a la que el adaptador se ejecuta después de ejecutar la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="aa441-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  
  
 <span data-ttu-id="aa441-106">Para habilitar el sondeo, debe especificar ciertas propiedades de enlace como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="aa441-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span> <span data-ttu-id="aa441-107">Para obtener más información sobre cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span><span class="sxs-lookup"><span data-stu-id="aa441-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="aa441-108">Configuración de una operación de sondeo con propiedades de enlace de Oracle E-Business Suite adaptador</span><span class="sxs-lookup"><span data-stu-id="aa441-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="aa441-109">La siguiente tabla resume los [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mensajes de cambio de propiedades de enlace que se utiliza para configurar el adaptador para recibir datos.</span><span class="sxs-lookup"><span data-stu-id="aa441-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="aa441-110">Debe especificar estas propiedades de enlace al ejecutar la aplicación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="aa441-110">You must specify these binding properties while running the polling application.</span></span>  
  
|<span data-ttu-id="aa441-111">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="aa441-111">Binding Property</span></span>|<span data-ttu-id="aa441-112">Description</span><span class="sxs-lookup"><span data-stu-id="aa441-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="aa441-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="aa441-113">**InboundOperationType**</span></span>|<span data-ttu-id="aa441-114">Especifica si desea realizar **sondeo** o **notificación** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="aa441-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="aa441-115">Valor predeterminado es **sondeo**.</span><span class="sxs-lookup"><span data-stu-id="aa441-115">Default is **Polling**.</span></span>|  
|<span data-ttu-id="aa441-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="aa441-116">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="aa441-117">Especifica la instrucción SQL que se ejecuta el adaptador para determinar si los datos están disponibles para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="aa441-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="aa441-118">Sólo si hay un registro, la instrucción SELECT especifique para la **PollingInput** se va a ejecutar la propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>|  
|<span data-ttu-id="aa441-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="aa441-119">**PollingInterval**</span></span>|<span data-ttu-id="aa441-120">Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se ejecuta la instrucción especificada para la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="aa441-121">El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="aa441-121">The default is 30 seconds.</span></span> <span data-ttu-id="aa441-122">El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos.</span><span class="sxs-lookup"><span data-stu-id="aa441-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="aa441-123">Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="aa441-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="aa441-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="aa441-124">**PollingInput**</span></span>|<span data-ttu-id="aa441-125">Especifica la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="aa441-125">Specifies the polling statement.</span></span> <span data-ttu-id="aa441-126">Para sondear mediante una instrucción SELECT, debe especificar una instrucción SELECT para esta propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="aa441-127">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="aa441-127">The default is null.</span></span><br /><br /> <span data-ttu-id="aa441-128">Debe especificar un valor para **PollingInput** propiedad para habilitar el sondeo de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="aa441-129">Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>|  
|<span data-ttu-id="aa441-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="aa441-130">**PollingAction**</span></span>|<span data-ttu-id="aa441-131">Especifica la acción para la operación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="aa441-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="aa441-132">Puede determinar la acción de sondeo de la interfaz de servicio generada para la operación con el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa441-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>|  
|<span data-ttu-id="aa441-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="aa441-133">**PostPollStatement**</span></span>|<span data-ttu-id="aa441-134">Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingInput** propiedad de enlace se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="aa441-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>|  
|<span data-ttu-id="aa441-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="aa441-135">**PollWhileDataFound**</span></span>|<span data-ttu-id="aa441-136">Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y ejecuta continuamente la instrucción de sondeo, si los datos están disponibles en la tabla que se va a sondear.</span><span class="sxs-lookup"><span data-stu-id="aa441-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="aa441-137">Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado.</span><span class="sxs-lookup"><span data-stu-id="aa441-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="aa441-138">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="aa441-138">Default is false.</span></span>|  
  
 <span data-ttu-id="aa441-139">Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="aa441-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="aa441-140">Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear la base de datos de Oracle, lea el resto de este tema.</span><span class="sxs-lookup"><span data-stu-id="aa441-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read the remainder of this topic.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="aa441-141">Cómo este tema muestra el sondeo</span><span class="sxs-lookup"><span data-stu-id="aa441-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="aa441-142">En este tema, para demostrar cómo [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de datos cambia mensajes mediante las instrucciones SELECT, se sondea el **MS_SAMPLE_EMPLOYEE** tabla de interfaz en el **biblioteca de objetos de aplicación**aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa441-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="aa441-143">Esta tabla se crea al ejecutar el script create_apps_artifacts.sql proporcionado con los ejemplos para crear estos objetos en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="aa441-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="aa441-144">Para mostrar una operación de sondeo, llevamos a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa441-144">To demonstrate a polling operation, we do the following:</span></span>  
  
-   <span data-ttu-id="aa441-145">Especifique una instrucción SELECT para la **PolledDataAvailableStatement** propiedad para determinar donde la tabla de interfaz sondea, (MS_SAMPLE_EMPLOYEE) de enlace tiene los datos.</span><span class="sxs-lookup"><span data-stu-id="aa441-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="aa441-146">En este ejemplo, puede establecer esta propiedad de enlace como:</span><span class="sxs-lookup"><span data-stu-id="aa441-146">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     <span data-ttu-id="aa441-147">Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla de interfaz MS_SAMPLE_EMPLOYEE tiene algunos registros.</span><span class="sxs-lookup"><span data-stu-id="aa441-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  
  
-   <span data-ttu-id="aa441-148">Especifique una instrucción SELECT para la **PollingInput** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="aa441-149">Esta instrucción recupera todas las filas de la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="aa441-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="aa441-150">En este ejemplo, puede establecer esta propiedad de enlace como:</span><span class="sxs-lookup"><span data-stu-id="aa441-150">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="aa441-151">Para obtener información acerca de la cláusula FOR UPDATE en la instrucción SELECT, vea [recibir mensajes de cambio de datos basado en sondeo de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="aa441-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  
  
-   <span data-ttu-id="aa441-152">Especificar una instrucción DELETE como parte de la **PostPollStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="aa441-153">Esta instrucción eliminará todos los datos de tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="aa441-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="aa441-154">En este ejemplo, puede establecer esta propiedad de enlace como:</span><span class="sxs-lookup"><span data-stu-id="aa441-154">In this example, you can set this binding property as:</span></span>  
  
    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     <span data-ttu-id="aa441-155">Después de que esto ocurra, la próxima vez que la instrucción especificada para **PollingInput** será ejecuta, no capturará los datos.</span><span class="sxs-lookup"><span data-stu-id="aa441-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  
  
-   <span data-ttu-id="aa441-156">Hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE, no obtendrá ningún mensaje de sondeo por lo que debe volver a rellenar la tabla de interfaz MS_SAMPLE_EMPLOYEE con nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="aa441-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="aa441-157">Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="aa441-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="aa441-158">Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.</span><span class="sxs-lookup"><span data-stu-id="aa441-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  
  
## <a name="consuming-the-polling-request-message"></a><span data-ttu-id="aa441-159">Consumir el mensaje de solicitud de sondeo</span><span class="sxs-lookup"><span data-stu-id="aa441-159">Consuming the Polling Request Message</span></span>  
 <span data-ttu-id="aa441-160">El adaptador, invoca la operación de sondeo en el código para sondear Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="aa441-160">The adapter invokes the polling operation on your code to poll the Oracle E-Business Suite.</span></span> <span data-ttu-id="aa441-161">Es decir, el adaptador envía un mensaje de solicitud de sondeo que recibe a través de una forma de canal de IInputChannel.</span><span class="sxs-lookup"><span data-stu-id="aa441-161">That is, the adapter sends a polling request message that you receive over an IInputChannel channel shape.</span></span> <span data-ttu-id="aa441-162">El mensaje de solicitud de sondeo contiene el conjunto de resultados de la consulta especificada por el **PollingInput** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-162">The polling request message contains the result set of the query specified by the **PollingInput** binding property.</span></span> <span data-ttu-id="aa441-163">Puede utilizar el mensaje de sondeo en uno de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="aa441-163">You can consume the polling message in one of two ways:</span></span>  
  
-   <span data-ttu-id="aa441-164">Para consumir el mensaje mediante la transmisión por secuencias de valor de nodo, debe llamar a la **WriteBodyContents** método en la respuesta de mensajes y pasarle una **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="aa441-164">To consume the message using node-value streaming, you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="aa441-165">Para consumir el mensaje mediante la transmisión por secuencias de nodo, se puede llamar a **GetReaderAtBodyContents** en el mensaje de respuesta para obtener un **XmlReader**.</span><span class="sxs-lookup"><span data-stu-id="aa441-165">To consume the message using node streaming, you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="aa441-166">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="aa441-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="aa441-167">Los ejemplos de este tema sondean la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="aa441-167">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="aa441-168">Una secuencia de comandos para generar la tabla se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="aa441-168">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="aa441-169">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="aa441-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="aa441-170">Obtener un ejemplo, **SelectPolling_ChannelModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="aa441-170">A sample, **SelectPolling_ChannelModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a><span data-ttu-id="aa441-171">Recibir mensajes de entrada para la operación de sondeo con el modelo del canal de WCF</span><span class="sxs-lookup"><span data-stu-id="aa441-171">Receiving Inbound Messages for Polling Operation Using the WCF Channel Model</span></span>  
 <span data-ttu-id="aa441-172">Esta sección proporciona instrucciones sobre cómo escribir una aplicación de .NET (modelo del canal) para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa441-172">This section provides instructions on how to write a .NET application (channel model) to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-adapter"></a><span data-ttu-id="aa441-173">Para recibir mensajes de sondeo del adaptador</span><span class="sxs-lookup"><span data-stu-id="aa441-173">To receive polling messages from the adapter</span></span>  
  
1.  <span data-ttu-id="aa441-174">Crear un proyecto de Microsoft Visual C#® en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa441-174">Create a Microsoft Visual C#® project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="aa441-175">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="aa441-175">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="aa441-176">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="aa441-176">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="aa441-177">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa441-177">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="aa441-178">Especifique un URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="aa441-178">Specify a connection URI.</span></span> <span data-ttu-id="aa441-179">Para obtener más información acerca de lo URI de conexión del adaptador, vea [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="aa441-179">For more information about the adapter connection URI, see [Create the Oracle E-Business Suite connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  
  
    ```  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    ```  
  
5.  <span data-ttu-id="aa441-180">Cree una instancia de **OracleEBSBinding** y establezca las propiedades de enlace necesarias para configurar el sondeo.</span><span class="sxs-lookup"><span data-stu-id="aa441-180">Create an instance of **OracleEBSBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="aa441-181">Como mínimo debe establecer el **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, y **PollingAction** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-181">At a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span> <span data-ttu-id="aa441-182">Para obtener más información sobre el enlace de propiedades que se usan para configurar el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span><span class="sxs-lookup"><span data-stu-id="aa441-182">For more information about binding properties used to configure polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
    binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
    binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
    binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
    ```  
  
6.  <span data-ttu-id="aa441-183">Dado que son sondear una tabla de interfaz, también debe establecer el contexto de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="aa441-183">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="aa441-184">Para obtener más información sobre el contexto de la aplicación y las propiedades de enlace requeridas para el contexto de la aplicación de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="aa441-184">For more information about application context and binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "<Enter user name here>";  
    binding.OraclePassword = "<Enter password here>";  
    binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
    ```  
  
7.  <span data-ttu-id="aa441-185">Crear una colección de parámetros de enlace y establecer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="aa441-185">Create a binding parameter collection and set the credentials.</span></span>  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
8.  <span data-ttu-id="aa441-186">Crear un agente de escucha de canal y ábralo.</span><span class="sxs-lookup"><span data-stu-id="aa441-186">Create a channel listener and open it.</span></span> <span data-ttu-id="aa441-187">Crear el agente de escucha mediante la invocación de **BuildChannelListener < IInputChannel\>**  método en el **OracleEBSBinding**.</span><span class="sxs-lookup"><span data-stu-id="aa441-187">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **OracleEBSBinding**.</span></span>  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
9. <span data-ttu-id="aa441-188">Obtener un **IInputChannel** canal invocando la **AcceptChannel** método en el agente de escucha y ábralo.</span><span class="sxs-lookup"><span data-stu-id="aa441-188">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
10. <span data-ttu-id="aa441-189">Invocar **recepción** en el canal que se va a obtener el siguiente mensaje entrante del adaptador.</span><span class="sxs-lookup"><span data-stu-id="aa441-189">Invoke **Receive** on the channel to get the next inbound message from the adapter.</span></span>  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
11. <span data-ttu-id="aa441-190">Consumir el conjunto de resultados devuelto por la operación de entrada.</span><span class="sxs-lookup"><span data-stu-id="aa441-190">Consume the result set returned by the inbound operation.</span></span> <span data-ttu-id="aa441-191">Puedes utilizar el mensaje mediante un **XmlReader** o un **XmlDictionaryWriter**.</span><span class="sxs-lookup"><span data-stu-id="aa441-191">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
12. <span data-ttu-id="aa441-192">Cierre el canal cuando se hayan completado de procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="aa441-192">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="aa441-193">Debe cerrar el canal cuando haya terminado de procesar la operación de entrada.</span><span class="sxs-lookup"><span data-stu-id="aa441-193">You must close the channel after you have finished processing the inbound operation.</span></span> <span data-ttu-id="aa441-194">Si no se cierra el canal puede afectar al comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="aa441-194">Failure to close the channel may affect the behavior of your code.</span></span>  
  
13. <span data-ttu-id="aa441-195">Cierre el agente de escucha cuando haya terminado de recibir mensajes de cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="aa441-195">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="aa441-196">Cerrando el agente de escucha no cierra los canales creados mediante el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="aa441-196">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="aa441-197">Debe cerrar explícitamente cada canal que se crea mediante el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="aa441-197">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aa441-198">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa441-198">Example</span></span>  
 <span data-ttu-id="aa441-199">En el ejemplo siguiente se muestra una aplicación de sondeo que sondea la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="aa441-199">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="aa441-200">El **PollingInput** propiedad contiene la instrucción select que lee todos los datos de la tabla MS_SAMPLE_EMPLOYEE y la instrucción de sondeo de envío, elimina todos los datos de la misma tabla.</span><span class="sxs-lookup"><span data-stu-id="aa441-200">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="aa441-201">Se escribe el mensaje de sondeo en `C:\PollingOutput.xml`.</span><span class="sxs-lookup"><span data-stu-id="aa441-201">The polling message is written to `C:\PollingOutput.xml`.</span></span>  
  
 <span data-ttu-id="aa441-202">Mensajes de sondeo subsiguiente no contendrá ningún registro hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="aa441-202">Subsequent polling messages will not contain any records until more data is added to the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="aa441-203">Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="aa441-203">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="aa441-204">Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.</span><span class="sxs-lookup"><span data-stu-id="aa441-204">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="aa441-205">El adaptador seguirá sondea hasta que cierre el host de servicio presionando \<devolver\>.</span><span class="sxs-lookup"><span data-stu-id="aa441-205">The adapter will continue to poll until you close the service host by pressing \<RETURN\>.</span></span>  
  
```  
using System;  
using Microsoft.Adapters.OracleEBS;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Xml;  
  
namespace SelectPolling_ChannelModel  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Console.WriteLine("Sample started. This sample will poll 5 times and will perform the following tasks:");  
            Console.WriteLine("Press any key to start polling...");  
            Console.ReadLine();  
            IChannelListener<IInputChannel> listener = null;  
  
            IInputChannel channel = null;  
  
            try  
            {  
                TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "<Enter user name here>";  
                binding.OraclePassword = "<Enter password here>";  
                binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  
  
                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  
  
                listener = binding.BuildChannelListener<IInputChannel>(ConnectionUri, bindingParams);  
                listener.Open();  
  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel and Listener opened...");  
                Console.WriteLine("\nWaiting for polled data...");  
                Console.WriteLine("Receive request timeout is {0}", messageTimeout);  
  
                // Poll five times with the specified message timeout   
                // If a timeout occurs polling will be aborted  
                for (int i = 0; i < 5; i++)  
                {  
                    Console.WriteLine("Polling: " + i);  
                    Message message = null;  
                    XmlReader reader = null;  
                    try  
                    {  
                        //Message is received so process the results  
                        message = channel.Receive(messageTimeout);  
                    }  
                    catch (System.TimeoutException toEx)  
                    {  
                        Console.WriteLine("\nNo data for request number {0}: {1}", i + 1, toEx.Message);  
                        continue;  
                    }  
  
                    // Get the query results using an XML reader  
                    try  
                    {  
                        reader = message.GetReaderAtBodyContents();  
                    }  
                    catch (Exception ex)  
                    {  
                        Console.WriteLine("Exception :" + ex);  
                        throw;                          
                    }  
  
                    XmlDocument doc = new XmlDocument();  
                    doc.Load(reader);  
                    using (XmlWriter writer = XmlWriter.Create("C:\\PollingOutput.xml"))  
                    {  
                        doc.WriteTo(writer);  
                        Console.WriteLine("The polling response is saved at 'C:\\PollingOutput.xml'");  
                    }  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    message.Close();  
                }  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                Console.ReadLine();  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: close the channel and listener to stop polling  
                if (channel != null)  
                {  
                    if (channel.State == CommunicationState.Opened)  
                        channel.Close();  
                    else  
                        channel.Abort();  
                }  
  
                if (listener != null)  
                {  
                    if (listener.State == CommunicationState.Opened)  
                        listener.Close();  
                    else  
                        listener.Abort();  
                }  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa441-206">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa441-206">See Also</span></span>  
 [<span data-ttu-id="aa441-207">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="aa441-207">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)