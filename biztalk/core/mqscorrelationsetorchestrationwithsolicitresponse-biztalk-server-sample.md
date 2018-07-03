---
title: MQSCorrelationSetOrchestrationWithSolicitResponse (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: 5127d743-bb79-4e97-a2f3-446892e1bfa0
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3780aa186146d0cc1b7bca90f7934f4823882ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014525"
---
# <a name="mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample"></a><span data-ttu-id="ae520-102">MQSCorrelationSetOrchestrationWithSolicitResponse (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="ae520-102">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server Sample)</span></span>
<span data-ttu-id="ae520-103">En el ejemplo MQSCorrelationSetOrchestrationWithSolicitResponse se muestra cómo usar un identificador de correlación producido por MQSeries Server en lugar de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae520-103">The MQSCorrelationSetOrchestrationWithSolicitResponse sample demonstrates how to use a correlation identifier produced by the MQSeries Server instead of by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ae520-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae520-104">What This Sample Does</span></span>  
 <span data-ttu-id="ae520-105">La orquestación envía un mensaje con un valor vacío para el **MQMD_MsgID** propiedad en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ae520-105">The orchestration sends a message with an empty value for the **MQMD_MsgID** property in the message header.</span></span> <span data-ttu-id="ae520-106">MQSeries genera MessageID y CorrelationID y devuelve un mensaje con un valor asignado a **MQMD_MsgID** y **MQMD_CorrelId** como parte de la respuesta de petición-respuesta de puerto del adaptador de envío .</span><span class="sxs-lookup"><span data-stu-id="ae520-106">MQSeries generates the MessageID and CorrelationID and returns a message with a value assigned to **MQMD_MsgID** and **MQMD_CorrelId** as part of the response in the solicit-response send port of the adapter.</span></span> <span data-ttu-id="ae520-107">La orquestación usa el identificador de correlación generado para inicializar el conjunto de correlaciones y ubicación de recepción se indica a continuación, Establece la correlación en una posterior activando el **MQMD_CorrelId** propiedad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ae520-107">The orchestration uses the generated correlation identifier to initialize the correlation set and follows the correlation set in a subsequent receive location by checking the **MQMD_CorrelId** property of the message.</span></span> <span data-ttu-id="ae520-108">El adaptador también asigna el identificador de correlación para **BizTalk_CorrelationID**, que también se podría usar en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="ae520-108">The adapter also assigns the correlation identifier to **BizTalk_CorrelationID**, which you could also use in an orchestration.</span></span> <span data-ttu-id="ae520-109">Para obtener más información sobre el uso de identificadores de correlación con el adaptador, vea [correlación de solicitud y respuesta utilizando mensajes](../core/correlating-messages-using-request-reply.md).</span><span class="sxs-lookup"><span data-stu-id="ae520-109">For more information about using correlation identifiers with the adapter, see [Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae520-110">Las orquestaciones que utilizan esta técnica pueden experimentar problemas si el mensaje de MQSeries Server llega antes que el identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="ae520-110">Orchestrations using this technique may experience problems if the message from the MQSeries Server arrives before the correlation identifier.</span></span> <span data-ttu-id="ae520-111">Asegúrese de diseñar las orquestaciones de modo que otorgue el tiempo suficiente a MQSeries Server para devolver el identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="ae520-111">Make sure that you design your orchestrations to allow enough time for the MQSeries Server to return the correlation identifier.</span></span> <span data-ttu-id="ae520-112">Este ejemplo no considera esta posible condición de anticipación.</span><span class="sxs-lookup"><span data-stu-id="ae520-112">This example does not consider this possible race condition.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ae520-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae520-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="ae520-114">*\<Ejemplos de la ruta de acceso\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="ae520-114">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse</span></span>  
  
 <span data-ttu-id="ae520-115">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="ae520-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ae520-116">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="ae520-116">**File**</span></span>|<span data-ttu-id="ae520-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ae520-117">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="ae520-118">**MQSCorrelationSolicitResponse.btproj,**</span><span class="sxs-lookup"><span data-stu-id="ae520-118">**MQSCorrelationSolicitResponse.btproj,**</span></span><br /><br /> <span data-ttu-id="ae520-119">**MQSCorrelationSolicitResponse.sln**</span><span class="sxs-lookup"><span data-stu-id="ae520-119">**MQSCorrelationSolicitResponse.sln**</span></span>|<span data-ttu-id="ae520-120">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae520-120">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="ae520-121">**MQSCorrelationSolicitResponse.odx**</span><span class="sxs-lookup"><span data-stu-id="ae520-121">**MQSCorrelationSolicitResponse.odx**</span></span>|<span data-ttu-id="ae520-122">El archivo de orquestación de BizTalk para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae520-122">The BizTalk orchestration file for the application.</span></span>|  
|<span data-ttu-id="ae520-123">**MQSCorrelationSolicitResponse.snk**</span><span class="sxs-lookup"><span data-stu-id="ae520-123">**MQSCorrelationSolicitResponse.snk**</span></span>|<span data-ttu-id="ae520-124">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="ae520-124">The strong naming key file.</span></span>|  
|<span data-ttu-id="ae520-125">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="ae520-125">Setup.bat</span></span>|<span data-ttu-id="ae520-126">Crea e inicializa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ae520-126">Builds and initializes this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="ae520-127">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae520-127">How to Use This Sample</span></span>  
 <span data-ttu-id="ae520-128">Para crear la aplicación, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ae520-128">To create the application, you must complete the following steps:</span></span>  
  
- <span data-ttu-id="ae520-129">Crear dos colas MQSeries.</span><span class="sxs-lookup"><span data-stu-id="ae520-129">Create two MQSeries queues.</span></span>  
  
- <span data-ttu-id="ae520-130">Configurar una ubicación de recepción y un puerto de envío de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae520-130">Set up a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and send port.</span></span>  
  
- <span data-ttu-id="ae520-131">Habilitar la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="ae520-131">Enable the receive location.</span></span>  
  
- <span data-ttu-id="ae520-132">Iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ae520-132">Start the send port.</span></span>  
  
- <span data-ttu-id="ae520-133">Crear las carpetas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ae520-133">Create the appropriate folders.</span></span>  
  
- <span data-ttu-id="ae520-134">Modificar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ae520-134">Modify the orchestration.</span></span>  
  
- <span data-ttu-id="ae520-135">Implementar, enlazar e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ae520-135">Deploy, bind and start the orchestration.</span></span>  
  
  <span data-ttu-id="ae520-136">Si dispone de los permisos necesarios para la instalación de MQSeries Server para Windows, puede crear la cola MQSeries mediante los cuadros de diálogo del adaptador y puede omitir el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="ae520-136">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="ae520-137">Si no dispone de este acceso, puede crear la cola con IBM WebSphere MQ Explorer.</span><span class="sxs-lookup"><span data-stu-id="ae520-137">If you do not have such access, you can create the queue using the IBM WebSphere MQ Explorer.</span></span> <span data-ttu-id="ae520-138">Para crear las colas con WebSphere MQ Explorer, realice los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="ae520-138">To create the queues through the WebSphere MQ Explorer, complete the following steps.</span></span>  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="ae520-139">Crear las colas MQSeries con WebSphere MQ Explorer</span><span class="sxs-lookup"><span data-stu-id="ae520-139">Creating the MQSeries Queues Through the WebSphere MQ Explorer</span></span>  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="ae520-140">Para crear las colas MQSeries con WebSphere MQ Explorer</span><span class="sxs-lookup"><span data-stu-id="ae520-140">To create the MQSeries queues through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="ae520-141">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ae520-141">Click **Start**, point to **All Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="ae520-142">Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ae520-142">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="ae520-143">El Administrador de cola predeterminado se denomina normalmente ***** QM_ < nombre_equipo >* donde *nombre_equipo* es el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ae520-143">The default queue manager is typically named **QM_***<machine_name>* where *machine_name* is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="ae520-144">Haga clic en **colas**, apunte a **New**y, a continuación, haga clic en **cola Local**.</span><span class="sxs-lookup"><span data-stu-id="ae520-144">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="ae520-145">En **Create Local Queue** cuadro de diálogo **nombre de la cola**, escriba "REPLYTOQ" y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-145">In **Create Local Queue** dialog box, in **Queue Name**, type "REPLYTOQ", and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ae520-146">Haga clic en **colas**, haga clic en **New**y, a continuación, haga clic en **cola Local**.</span><span class="sxs-lookup"><span data-stu-id="ae520-146">Right-click **Queues**, click **New**, and then click **Local Queue**.</span></span>  
  
6.  <span data-ttu-id="ae520-147">En el **Create Local Queue** cuadro de diálogo **nombre de la cola**, escriba "SOLICITRESPONSEQ" y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-147">In the **Create Local Queue** dialog box, in **Queue Name**, type "SOLICITRESPONSEQ", and then click **OK**.</span></span>  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="ae520-148">Crear la ubicación de recepción y la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="ae520-148">Creating the Receive Location and the MQSeries Queue</span></span>  
 <span data-ttu-id="ae520-149">Este procedimiento crea el puerto de envío y la ubicación de recepción para enviar el mensaje y recibir el mensaje de correlación de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="ae520-149">This procedure creates the send port and receive location to send the message to and receive the correlation message from MQSeries.</span></span> <span data-ttu-id="ae520-150">La cola MQSeries también se creará al crear la ubicación de recepción si no se ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae520-150">The MQSeries queue will also be created when you create the receive location if not already created.</span></span>  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="ae520-151">Para crear la ubicación de recepción y la cola de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ae520-151">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="ae520-152">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ae520-152">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="ae520-153">Expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación necesaria.</span><span class="sxs-lookup"><span data-stu-id="ae520-153">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="ae520-154">Haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="ae520-154">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="ae520-155">En el **propiedades del puerto de recepción unidireccional** cuadro de diálogo el **nombre** cuadro, escriba "MQReply" y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-155">In the **One-way Receive Port Properties** dialog box, in the **Name** box, type "MQReply", and click **OK**.</span></span>  
  
5.  <span data-ttu-id="ae520-156">En el panel izquierdo, haga clic en **ubicaciones de recepción** pestaña y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="ae520-156">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="ae520-157">En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** , escriba "MQReply".</span><span class="sxs-lookup"><span data-stu-id="ae520-157">In the **Receive Location Properties** dialog box, in the **Name** box, type "MQReply”.</span></span>  
  
7.  <span data-ttu-id="ae520-158">En el **tipo de transporte** cuadro, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="ae520-158">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="ae520-159">En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="ae520-159">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="ae520-160">En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="ae520-160">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="ae520-161">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-161">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="ae520-162">En el **propiedades de transporte MQSeries** cuadro de diálogo el **intervalo de sondeo** , escriba "10".</span><span class="sxs-lookup"><span data-stu-id="ae520-162">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type "10".</span></span>  
  
12. <span data-ttu-id="ae520-163">En el **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="ae520-163">In the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
13. <span data-ttu-id="ae520-164">En el **definición de la cola** cuadro de diálogo el **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ae520-164">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="ae520-165">En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ae520-165">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
15. <span data-ttu-id="ae520-166">En el **cola** , escriba "REPLYTOQ" y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-166">In the **Queue** box, type " REPLYTOQ", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="ae520-167">En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en**Aceptar**o **realiza** hasta que haya salido de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae520-167">In the **Export** dialog box, click **Create Queue**, and then click**OK**or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="ae520-168">Crear el puerto de envío y la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="ae520-168">Creating the Send Port and MQSeries Queue</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="ae520-169">Para crear el puerto de envío y la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="ae520-169">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="ae520-170">Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="ae520-170">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ae520-171">En el **propiedades de puerto de envío** cuadro de diálogo el **nombre** , escriba "MQSolicitResponse".</span><span class="sxs-lookup"><span data-stu-id="ae520-171">In the **Send Port Properties** dialog box, in the **Name** box, type "MQSolicitResponse".</span></span>  
  
3.  <span data-ttu-id="ae520-172">En el **tipo de transporte** cuadro, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="ae520-172">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="ae520-173">En el **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="ae520-173">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="ae520-174">En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="ae520-174">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
6.  <span data-ttu-id="ae520-175">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-175">Click **Configure**.</span></span>  
  
7.  <span data-ttu-id="ae520-176">En el **propiedades de transporte MQSeries** cuadro de diálogo el **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="ae520-176">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
8.  <span data-ttu-id="ae520-177">En el **definición de la cola** cuadro de diálogo el **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ae520-177">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
9. <span data-ttu-id="ae520-178">En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ae520-178">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
10. <span data-ttu-id="ae520-179">En el **cola** , escriba "SOLICITRESPONSEQ" y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-179">In the **Queue** box, type " SOLICITRESPONSEQ", and then click **Export**.</span></span>  
  
11. <span data-ttu-id="ae520-180">En el cuadro de diálogo Exportar, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** o **realiza** hasta que haya salido de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae520-180">In the Export dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a><span data-ttu-id="ae520-181">Habilitar la ubicación de recepción e iniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="ae520-181">Enabling the Receive Location and Starting the Send Port</span></span>  
 <span data-ttu-id="ae520-182">Este procedimiento crea las carpetas requeridas para recibir el archivo en la orquestación y envía el mensaje correlacionado y el mensaje de respuesta a las carpetas de salida.</span><span class="sxs-lookup"><span data-stu-id="ae520-182">This procedure creates the folders required to receive the file into the orchestration and sends the correlated message and response message to the output folders.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="ae520-183">Para habilitar la ubicación de recepción e iniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="ae520-183">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="ae520-184">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="ae520-184">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="ae520-185">En el panel de detalles, haga clic en el **MQIn** ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-185">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="ae520-186">En el panel de detalles, haga clic en el **MQOut** puerto de envío y haga clic en **iniciar.**</span><span class="sxs-lookup"><span data-stu-id="ae520-186">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
## <a name="creating-the-folders-used-by-the-application"></a><span data-ttu-id="ae520-187">Crear las carpetas usadas por la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae520-187">Creating the Folders Used by the Application</span></span>  
  
#### <a name="to-create-the-folders-used-by-the-application"></a><span data-ttu-id="ae520-188">Para crear las carpetas usadas por la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae520-188">To create the folders used by the application</span></span>  
  
1.  <span data-ttu-id="ae520-189">Si no existe ninguna, cree una carpeta denominada "temp" en la unidad C:\.</span><span class="sxs-lookup"><span data-stu-id="ae520-189">If one does not already exist, create a folder named "temp" on your C:\ drive.</span></span>  
  
2.  <span data-ttu-id="ae520-190">Crear carpetas en el **C:\temp** directorio denominado "Pickup2", "Dropit2" y "MoveIt".</span><span class="sxs-lookup"><span data-stu-id="ae520-190">Create folders under the **C:\temp** directory named "Pickup2", "Dropit2", and "MoveIt".</span></span>  
  
## <a name="modifying-the-orchestration-used-by-the-application"></a><span data-ttu-id="ae520-191">Modificar la orquestación usada por la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae520-191">Modifying the Orchestration Used by the Application</span></span>  
 <span data-ttu-id="ae520-192">Este procedimiento modifica la orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae520-192">This procedure modifies the orchestration used by the application.</span></span>  
  
||  
|-|  
|<span data-ttu-id="ae520-193">Para modificar la orquestación usada por la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae520-193">To modify the Orchestration used by the application</span></span>|  
|<span data-ttu-id="ae520-194">-En Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], haga doble clic en el archivo de solución, **MQSCorrelationSolicitResponse.sln**para abrir la solución.</span><span class="sxs-lookup"><span data-stu-id="ae520-194">- In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], double-click the solution file, **MQSCorrelationSolicitResponse.sln**, to open the solution.</span></span><br /><br /> <span data-ttu-id="ae520-195">-Desde el panel Explorador de soluciones, haga doble clic en la orquestación **MQSCorrelationSolicitResponse.odx** para ver la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ae520-195">- From the Solution Explorer pane, double-click the orchestration **MQSCorrelationSolicitResponse.odx** to view the orchestration.</span></span><br /><br /> <span data-ttu-id="ae520-196">-Haga doble clic en la forma asignación de mensajes **MessageAssignment_1** para iniciar el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ae520-196">- Double-click the message assignment shape **MessageAssignment_1** to launch the BizTalk Expression Editor.</span></span><br /><br /> <span data-ttu-id="ae520-197">-Escriba el nombre de administrador de cola de MQSeries adecuado de la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="ae520-197">- Enter the appropriate MQSeries queue manager name for the following expression:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_ReplyToQMgr) = "QM_<machine_name>";`<br /><br /> <span data-ttu-id="ae520-198">-Si desea que el mensaje de respuesta enviado desde BizTalk contenga todo el contenido del mensaje original en lugar de únicamente los 100 primeros bytes, modifique la línea siguiente en el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ae520-198">- If you would like for the response message sent from BizTalk to contain the entire contents of the original message instead of only the first 100 bytes, modify the following line in the BizTalk Expression Editor.</span></span><br /><br /> <span data-ttu-id="ae520-199">-Línea original:</span><span class="sxs-lookup"><span data-stu-id="ae520-199">- Original line:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 768;`<br /><br /> <span data-ttu-id="ae520-200">Cambiar por:</span><span class="sxs-lookup"><span data-stu-id="ae520-200">Change to:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 1792;`<br /><br /> <span data-ttu-id="ae520-201">-En el Editor de expresiones de BizTalk, haga clic en **Aceptar** para guardar la expresión modificada.</span><span class="sxs-lookup"><span data-stu-id="ae520-201">- In the BizTalk Expression Editor, click **OK** to save the modified expression.</span></span><br /><br /> <span data-ttu-id="ae520-202">-En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione **archivo**y, a continuación, seleccione **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="ae520-202">- In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select **File**, and then select **Save All**.</span></span>|  
  
## <a name="building-and-deploying-the-sample"></a><span data-ttu-id="ae520-203">Generar e implementar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae520-203">Building and Deploying the Sample</span></span>  
 <span data-ttu-id="ae520-204">Este procedimiento genera e implementa la solución que contiene la orquestación usada en esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae520-204">This procedure builds and deploys the solution that contains the orchestration used in this application.</span></span>  
  
#### <a name="to-build-and-deploy-the-sample"></a><span data-ttu-id="ae520-205">Para generar e implementar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae520-205">To build and deploy the sample</span></span>  
  
1.  <span data-ttu-id="ae520-206">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="ae520-206">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse`  
  
2.  <span data-ttu-id="ae520-207">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae520-207">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    1.  <span data-ttu-id="ae520-208">Crea una clave de nombre seguro para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ae520-208">Creates a strong name key for the project.</span></span>  
  
    2.  <span data-ttu-id="ae520-209">Compila e implementa el proyecto de orquestación.</span><span class="sxs-lookup"><span data-stu-id="ae520-209">Compiles and deploys the orchestration project.</span></span>  
  
    3.  <span data-ttu-id="ae520-210">Crea un puerto de envío y un puerto de recepción con el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="ae520-210">Creates a send port and a receive port with the File adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae520-211">Puesto que esta orquestación especifica los enlaces para el envío y la recepción de archivos con el adaptador de archivos, al implementar la orquestación, se crearán los puertos de envío, puertos de recepción y la ubicación de recepción necesarios para la recepción de un archivo en la orquestación y la salida del mensaje de correlación y el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ae520-211">Since this orchestration specifies the bindings for sending and receiving files with the file adapter, when you deploy the orchestration the necessary send ports, receive port, and receive location will be created for receiving a file into the orchestration and outputting the correlation message and the response message.</span></span>  
  
## <a name="binding-and-starting-the-orchestration"></a><span data-ttu-id="ae520-212">Enlazar e iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="ae520-212">Binding and Starting the Orchestration</span></span>  
 <span data-ttu-id="ae520-213">Este procedimiento enlaza la orquestación al host y a los puertos de envío y ubicaciones de recepción correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ae520-213">This procedure binds the orchestration to the host and appropriate send ports and receive locations.</span></span>  
  
#### <a name="to-bind-and-start-the-orchestration"></a><span data-ttu-id="ae520-214">Procedimiento para enlazar e iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="ae520-214">To bind and start the orchestration</span></span>  
  
1.  <span data-ttu-id="ae520-215">En la consola de administración de BizTalk Server, expanda el **orquestaciones** carpeta.</span><span class="sxs-lookup"><span data-stu-id="ae520-215">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="ae520-216">En el panel de detalles, haga clic en el **MQSCorrelationSolicitResponse** orquestación y haga clic en **enlazar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-216">In the details pane, right-click the **MQSCorrelationSolicitResponse** orchestration and click **Bind**.</span></span>  
  
3.  <span data-ttu-id="ae520-217">Enlace los puertos de orquestación con los siguientes puertos de envío y ubicaciones de recepción:</span><span class="sxs-lookup"><span data-stu-id="ae520-217">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="ae520-218">**Puerto de orquestación**</span><span class="sxs-lookup"><span data-stu-id="ae520-218">**Orchestration Port**</span></span>|<span data-ttu-id="ae520-219">**Puerto de mensajería / ubicación de recepción**</span><span class="sxs-lookup"><span data-stu-id="ae520-219">**Messaging Port / Receive Location**</span></span>|  
    |----------------------------|--------------------------------------------|  
    |<span data-ttu-id="ae520-220">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="ae520-220">FileReceivePort</span></span>|<span data-ttu-id="ae520-221">MQSCorrelationSolicitResponse.Orchestration.FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="ae520-221">MQSCorrelationSolicitResponse.Orchestration.FileReceivePort</span></span>|  
    |<span data-ttu-id="ae520-222">MQSeriesResponseReceivePort</span><span class="sxs-lookup"><span data-stu-id="ae520-222">MQSeriesResponseReceivePort</span></span>|<span data-ttu-id="ae520-223">MQReply</span><span class="sxs-lookup"><span data-stu-id="ae520-223">MQReply</span></span>|  
    |<span data-ttu-id="ae520-224">SolicitResponsePort</span><span class="sxs-lookup"><span data-stu-id="ae520-224">SolicitResponsePort</span></span>|<span data-ttu-id="ae520-225">MQSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="ae520-225">MQSolicitResponse</span></span>|  
    |<span data-ttu-id="ae520-226">TempPort</span><span class="sxs-lookup"><span data-stu-id="ae520-226">TempPort</span></span>|<span data-ttu-id="ae520-227">MQSCorrelationSolicitResponse.Orchestration.TempPort</span><span class="sxs-lookup"><span data-stu-id="ae520-227">MQSCorrelationSolicitResponse.Orchestration.TempPort</span></span>|  
    |<span data-ttu-id="ae520-228">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="ae520-228">FileSendPort</span></span>|<span data-ttu-id="ae520-229">MQSCorrelationSolicitResponse.Orchestration.FileSendPort</span><span class="sxs-lookup"><span data-stu-id="ae520-229">MQSCorrelationSolicitResponse.Orchestration.FileSendPort</span></span>|  
  
4.  <span data-ttu-id="ae520-230">Haga clic en **Host**.</span><span class="sxs-lookup"><span data-stu-id="ae520-230">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="ae520-231">En el **Host** cuadro, seleccione **BizTalkServerApplication** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-231">In the **Host** box, select **BizTalkServerApplication** and click **OK**.</span></span>  
  
6.  <span data-ttu-id="ae520-232">En **puertos de envío**, haga clic en **MQSCorrelationSolicitResponse.Orchestration.TempPort**y, a continuación, seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-232">In **Send Ports**, right-click **MQSCorrelationSolicitResponse.Orchestration.TempPort**, and then select **Start**.</span></span>  
  
7.  <span data-ttu-id="ae520-233">En **puertos de envío**, haga clic en **MQSCorrelationSolicitResponse.Orchestration.FileSendPort**y, a continuación, seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-233">In **Send Ports**, right-click **MQSCorrelationSolicitResponse.Orchestration.FileSendPort**, and then select **Start**.</span></span>  
  
8.  <span data-ttu-id="ae520-234">En **ubicaciones de recepción**, haga clic en **MQSCorrelationSolicitResponse.Orchestration.FileReceivePort**y, a continuación, seleccione **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-234">In **Receive Locations**, right-click **MQSCorrelationSolicitResponse.Orchestration.FileReceivePort**, and then select **Enable**.</span></span>  
  
9. <span data-ttu-id="ae520-235">Haga clic en la orquestación y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ae520-235">Right-click the orchestration and click **Start**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae520-236">Además, iniciar la orquestación da de alta la orquestación de forma automática.</span><span class="sxs-lookup"><span data-stu-id="ae520-236">Starting the orchestration also automatically enlists the orchestration.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="ae520-237">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae520-237">Testing the Application</span></span>  
 <span data-ttu-id="ae520-238">Este procedimiento comprueba la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae520-238">This procedure tests the application.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="ae520-239">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae520-239">To test the application</span></span>  
  
1. <span data-ttu-id="ae520-240">Coloque un archivo en el **C:\Temp\Pickup2** carpeta.</span><span class="sxs-lookup"><span data-stu-id="ae520-240">Put a file in the **C:\Temp\Pickup2** folder.</span></span>  
  
2. <span data-ttu-id="ae520-241">Examine los archivos en el **C:\Temp\Dropit2** carpeta y el **C:\Temp\Moveit**carpeta.</span><span class="sxs-lookup"><span data-stu-id="ae520-241">Examine the files in the **C:\Temp\Dropit2** folder and the **C:\Temp\Moveit**folder.</span></span>  
  
   - <span data-ttu-id="ae520-242">El **C:\Temp\Dropit2** carpeta debe contener una copia del mensaje que se ha recogido originalmente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae520-242">The **C:\Temp\Dropit2** folder should contain a copy of the message that was originally picked up by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   - <span data-ttu-id="ae520-243">El **C:\Temp\Moveit**carpeta debe contener un documento de respuesta con el identificador de mensajes (MQMD_MsgId) y el identificador de correlación (MQMD_CorrelId).</span><span class="sxs-lookup"><span data-stu-id="ae520-243">The **C:\Temp\Moveit**folder should contain a response document with the message identifier (MQMD_MsgId) and the correlation identifier (MQMD_CorrelId).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ae520-244">Si deshabilita el **MQReply** ubicación de recepción, puede examinar el mensaje en WebSphere MQ Explorer y observar que se establecen los identificadores de mensaje y correlación.</span><span class="sxs-lookup"><span data-stu-id="ae520-244">If you disable the **MQReply** receive location, you can examine the message in WebSphere MQ Explorer and see that the message and correlation identifiers are set.</span></span> <span data-ttu-id="ae520-245">Para ello, inicie el **WebSphere MQ Explorer** y examine el mensaje colocado en el **REPLYTOQ** cola.</span><span class="sxs-lookup"><span data-stu-id="ae520-245">To do this, launch the **WebSphere MQ Explorer** and examine the message placed in the **REPLYTOQ** queue.</span></span> <span data-ttu-id="ae520-246">Los identificadores de mensaje y correlación aparecen en la **identificadores** pestaña de la **Messageproperties** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae520-246">The message and correlation identifiers are displayed on the **Identifiers** tab of the **Messageproperties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae520-247">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae520-247">See Also</span></span>  
 <span data-ttu-id="ae520-248">[Correlación de mensajes mediante la solicitud y respuesta](../core/correlating-messages-using-request-reply.md) </span><span class="sxs-lookup"><span data-stu-id="ae520-248">[Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md) </span></span>  
 [<span data-ttu-id="ae520-249">Ejemplos del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ae520-249">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)