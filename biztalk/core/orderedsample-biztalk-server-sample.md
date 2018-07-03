---
title: OrderedSample (ejemplo de BizTalk Server) | Microsoft Docs
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
- MQSeries adapters, examples
ms.assetid: 7e59ff43-d425-40cd-9725-af13084f83d9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96a8cd43f80e9bf6ef7b5a2628f276aa7ef6829c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013101"
---
# <a name="orderedsample-biztalk-server-sample"></a><span data-ttu-id="5765f-102">OrderedSample (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="5765f-102">OrderedSample (BizTalk Server Sample)</span></span>
<span data-ttu-id="5765f-103">El ejemplo OrderedSample muestra cómo usar una orquestación para recibir y enviar un serie ordenada de mensajes en un modo de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="5765f-103">The OrderedSample sample demonstrates how to use an orchestration to receive and send an ordered series of messages in a round-trip fashion.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="5765f-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="5765f-104">What This Sample Does</span></span>  
 <span data-ttu-id="5765f-105">El ejemplo asume que existen mensajes en la cola MQSeries desde la que recibe mensajes.</span><span class="sxs-lookup"><span data-stu-id="5765f-105">The sample assumes there are messages in the MQSeries queue from which it receives messages.</span></span> <span data-ttu-id="5765f-106">Cuando el adaptador lee los mensajes de la cola MQSeries, lo hace en orden y los envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5765f-106">When the adapter reads the messages from MQSeries queue, it reads them in-order and submits them to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5765f-107">El puerto de recepción en la orquestación, **mqreceive**, tiene su **entrega ordenada** propiedad establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="5765f-107">The receive port in the orchestration, **mqreceive**, has its **Ordered Delivery** property set to **True**.</span></span>  
  
 <span data-ttu-id="5765f-108">En cuanto al envío, la orquestación envía un mensaje y, a continuación, espera por la notificación de entrega antes de enviar el siguiente mensaje.</span><span class="sxs-lookup"><span data-stu-id="5765f-108">For the send side, the orchestration sends a message and then waits for a delivery notification before sending the next message.</span></span> <span data-ttu-id="5765f-109">El puerto de envío **mqsend** tiene su **notificación de entrega** propiedad establecida en **transmitida**.</span><span class="sxs-lookup"><span data-stu-id="5765f-109">The send port, **mqsend** has its **Delivery Notification** property set to **Transmitted**.</span></span> <span data-ttu-id="5765f-110">Para que el ejemplo siga siendo sencillo, la orquestación usa un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="5765f-110">To keep the example simple, the orchestration uses an infinite loop.</span></span>  
  
 <span data-ttu-id="5765f-111">La orquestación puede recibir lotes de mensajes, así como un único mensaje.</span><span class="sxs-lookup"><span data-stu-id="5765f-111">The orchestration can receive batches of messages and single messages.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5765f-112">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="5765f-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="5765f-113">*\<Ejemplos de la ruta de acceso\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample</span><span class="sxs-lookup"><span data-stu-id="5765f-113">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample</span></span>  
  
 <span data-ttu-id="5765f-114">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="5765f-114">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5765f-115">Archivo</span><span class="sxs-lookup"><span data-stu-id="5765f-115">File</span></span>|<span data-ttu-id="5765f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="5765f-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5765f-117">OrderedReceiveSend.btproj,</span><span class="sxs-lookup"><span data-stu-id="5765f-117">OrderedReceiveSend.btproj,</span></span><br /><br /> <span data-ttu-id="5765f-118">OrderedReceiveSend.sln</span><span class="sxs-lookup"><span data-stu-id="5765f-118">OrderedReceiveSend.sln</span></span>|<span data-ttu-id="5765f-119">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5765f-119">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="5765f-120">OrderedReceiveSendOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="5765f-120">OrderedReceiveSendOrchestration.odx</span></span>|<span data-ttu-id="5765f-121">La orquestación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5765f-121">The orchestration of the application.</span></span>|  
|<span data-ttu-id="5765f-122">OrderedSample.snk</span><span class="sxs-lookup"><span data-stu-id="5765f-122">OrderedSample.snk</span></span>|<span data-ttu-id="5765f-123">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="5765f-123">The strong naming key file.</span></span>|  
|<span data-ttu-id="5765f-124">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="5765f-124">**Setup.bat**</span></span>|<span data-ttu-id="5765f-125">Crea e inicializa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5765f-125">Builds and initializes this sample.</span></span>|  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="5765f-126">Generar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5765f-126">Building and Running the Sample</span></span>  
  
#### <a name="to-build-and-deploy-the-sample"></a><span data-ttu-id="5765f-127">Para generar e implementar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5765f-127">To build and deploy the sample</span></span>  
  
1. <span data-ttu-id="5765f-128">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="5765f-128">In a command window, navigate to the following folder:</span></span>  
  
    `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2. <span data-ttu-id="5765f-129">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5765f-129">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   1.  <span data-ttu-id="5765f-130">Crea una clave de nombre seguro para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5765f-130">Creates a strong name key for the project.</span></span>  
  
   2.  <span data-ttu-id="5765f-131">Compila e implementa el proyecto de orquestación.</span><span class="sxs-lookup"><span data-stu-id="5765f-131">Compiles and deploys the orchestration project.</span></span>  
  
   <span data-ttu-id="5765f-132">Si dispone de los permisos necesarios para la instalación de MQSeries Server para Windows, puede crear la cola MQSeries mediante los cuadros de diálogo del adaptador y puede omitir el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="5765f-132">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="5765f-133">Si no dispone de este acceso, puede crear la cola con IBM WebSphere MQ Explorer.</span><span class="sxs-lookup"><span data-stu-id="5765f-133">If you do not have such access, you can create the queue using the IBM WebSphere MQ Explorer.</span></span> <span data-ttu-id="5765f-134">Para crear las colas con WebSphere MQ Explorer, realice los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="5765f-134">To create the queues through the WebSphere MQ Explorer, complete the following steps.</span></span>  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="5765f-135">Crear las colas MQSeries con WebSphere MQ Explorer</span><span class="sxs-lookup"><span data-stu-id="5765f-135">Creating the MQSeries Queues Through the WebSphere MQ Explorer</span></span>  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="5765f-136">Para crear las colas MQSeries con WebSphere MQ Explorer</span><span class="sxs-lookup"><span data-stu-id="5765f-136">To create the MQSeries queues through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="5765f-137">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.</span><span class="sxs-lookup"><span data-stu-id="5765f-137">Click **Start**, point to **All Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="5765f-138">Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el **Administrador de cola predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="5765f-138">Double-click **Queue Managers**, and then double-click the **default queue manager**.</span></span> <span data-ttu-id="5765f-139">Normalmente, el administrador de cola predeterminado se denomina QM_<nombre_equipo>, donde nombre_equipo es el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="5765f-139">The default queue manager is typically named QM_<machine_name> where machine_name is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="5765f-140">Haga clic en **colas**, apunte a **New**y, a continuación, haga clic en **cola Local**.</span><span class="sxs-lookup"><span data-stu-id="5765f-140">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="5765f-141">En **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **"queue1"** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-141">In **Create Local Queue** dialog box, in **Queue Name**, type **"queue1"**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="5765f-142">Haga clic en **colas**, haga clic en **New**y, a continuación, haga clic en **cola Local**.</span><span class="sxs-lookup"><span data-stu-id="5765f-142">Right-click **Queues**, click **New**, and then click **Local Queue**.</span></span>  
  
6.  <span data-ttu-id="5765f-143">En el **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **"queue2"** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-143">In the **Create Local Queue** dialog box, in **Queue Name**, type **"queue2"**, and then click **OK**.</span></span>  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="5765f-144">Crear la ubicación de recepción y la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="5765f-144">Creating the Receive Location and the MQSeries Queue</span></span>  
 <span data-ttu-id="5765f-145">Este procedimiento crea el puerto de envío y la ubicación de recepción para enviar el mensaje y recibir el mensaje de correlación de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="5765f-145">This procedure creates the send port and receive location to send the message to and receive the correlation message from MQSeries.</span></span> <span data-ttu-id="5765f-146">La cola MQSeries también se creará al crear la ubicación de recepción si no se ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5765f-146">The MQSeries queue will also be created when you create the receive location if not already created.</span></span>  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="5765f-147">Para crear la ubicación de recepción y la cola de MQSeries</span><span class="sxs-lookup"><span data-stu-id="5765f-147">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="5765f-148">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5765f-148">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="5765f-149">Expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación necesaria.</span><span class="sxs-lookup"><span data-stu-id="5765f-149">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="5765f-150">Haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="5765f-150">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="5765f-151">En el **propiedades del puerto de recepción unidireccional** cuadro de diálogo, en el **nombre** cuadro, escriba **OrderedSampleReceive** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-151">In the **One-way Receive Port Properties** dialog box type, in the **Name** box type **OrderedSampleReceive** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="5765f-152">En el panel izquierdo, haga clic en **ubicaciones de recepción** pestaña y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="5765f-152">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="5765f-153">En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** cuadro, escriba "**OrderedSampleReceiveLocation**".</span><span class="sxs-lookup"><span data-stu-id="5765f-153">In the **Receive Location Properties** dialog box, in the **Name** box type "**OrderedSampleReceiveLocation**".</span></span>  
  
7.  <span data-ttu-id="5765f-154">En el **tipo de transporte** cuadro, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="5765f-154">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="5765f-155">En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="5765f-155">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="5765f-156">En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="5765f-156">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="5765f-157">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-157">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="5765f-158">En el **propiedades de transporte MQSeries** cuadro de diálogo el **intervalo de sondeo** , escriba **"10"**.</span><span class="sxs-lookup"><span data-stu-id="5765f-158">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type **"10"**.</span></span>  
  
12. <span data-ttu-id="5765f-159">En el **definición de la cola** cuadro, haga clic en el **puntos suspensivos (...)**  botón.</span><span class="sxs-lookup"><span data-stu-id="5765f-159">In the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
13. <span data-ttu-id="5765f-160">En el **definición de la cola** cuadro de diálogo el **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="5765f-160">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="5765f-161">En el **Administrador de cola** cuadro, seleccione el **Administrador de cola predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="5765f-161">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
15. <span data-ttu-id="5765f-162">En el **cola** , escriba " **queue1**" y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-162">In the **Queue** box, type " **queue1**", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="5765f-163">En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** o **realiza** hasta que haya salido de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5765f-163">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="5765f-164">Crear el puerto de envío y la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="5765f-164">Creating the Send Port and MQSeries Queue</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="5765f-165">Para crear el puerto de envío y la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="5765f-165">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="5765f-166">Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="5765f-166">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="5765f-167">En el **propiedades del puerto estático** cuadro de diálogo, en el **nombre** , escriba "**OrderedSampleSend**".</span><span class="sxs-lookup"><span data-stu-id="5765f-167">In the **Static Port Properties** dialog box type, in the **Name** box, type "**OrderedSampleSend**".</span></span>  
  
3.  <span data-ttu-id="5765f-168">En el **tipo de transporte** cuadro, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="5765f-168">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="5765f-169">En el **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="5765f-169">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="5765f-170">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-170">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="5765f-171">En el **propiedades de transporte MQSeries** cuadro de diálogo el **definición de la cola** cuadro, haga clic en el **puntos suspensivos (...)**  botón.</span><span class="sxs-lookup"><span data-stu-id="5765f-171">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
7.  <span data-ttu-id="5765f-172">En el **definición de la cola** cuadro de diálogo el **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="5765f-172">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
8.  <span data-ttu-id="5765f-173">En el **Administrador de cola** cuadro, seleccione el **Administrador de cola predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="5765f-173">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
9. <span data-ttu-id="5765f-174">En el **cola** , escriba " **queue2**" y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-174">In the **Queue** box, type " **queue2**", and then click **Export**.</span></span>  
  
10. <span data-ttu-id="5765f-175">En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** o **realiza** hasta que haya salido de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5765f-175">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="5765f-176">Para habilitar la ubicación de recepción e iniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="5765f-176">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="5765f-177">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="5765f-177">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="5765f-178">En el panel de detalles, haga clic en el **MQIn** ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-178">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="5765f-179">En el panel de detalles, haga clic en el **MQOut** puerto de envío y haga clic en **iniciar.**</span><span class="sxs-lookup"><span data-stu-id="5765f-179">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
#### <a name="to-bind-and-start-the-orchestration"></a><span data-ttu-id="5765f-180">Para enlazar e iniciar la Orquestación</span><span class="sxs-lookup"><span data-stu-id="5765f-180">To bind and start the Orchestration</span></span>  
  
1.  <span data-ttu-id="5765f-181">En la consola de administración de BizTalk Server, expanda el **orquestaciones** carpeta.</span><span class="sxs-lookup"><span data-stu-id="5765f-181">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="5765f-182">Haga doble clic en el **OrderedSampleOrchestration** orquestación y, a continuación, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="5765f-182">Double-click the **OrderedSampleOrchestration** orchestration, and then click  **Bindings**.</span></span>  
  
3.  <span data-ttu-id="5765f-183">Enlace los puertos de orquestación con los siguientes puertos de envío y ubicaciones de recepción:</span><span class="sxs-lookup"><span data-stu-id="5765f-183">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="5765f-184">Puerto de orquestación</span><span class="sxs-lookup"><span data-stu-id="5765f-184">Orchestration Port</span></span>|<span data-ttu-id="5765f-185">Puerto de mensajería/ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="5765f-185">Messaging Port / Receive Location</span></span>|  
    |------------------------|----------------------------------------|  
    |<span data-ttu-id="5765f-186">mqreceive</span><span class="sxs-lookup"><span data-stu-id="5765f-186">mqreceive</span></span>|<span data-ttu-id="5765f-187">OrderedSampleReceive</span><span class="sxs-lookup"><span data-stu-id="5765f-187">OrderedSampleReceive</span></span>|  
    |<span data-ttu-id="5765f-188">mqsend</span><span class="sxs-lookup"><span data-stu-id="5765f-188">mqsend</span></span>|<span data-ttu-id="5765f-189">OrderedSampleSend</span><span class="sxs-lookup"><span data-stu-id="5765f-189">OrderedSampleSend</span></span>|  
  
4.  <span data-ttu-id="5765f-190">Haga clic en **Host**.</span><span class="sxs-lookup"><span data-stu-id="5765f-190">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="5765f-191">En el **Host** cuadro, seleccione **BizTalkServerApplication**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-191">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="5765f-192">Haga clic en el **orquestación** y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="5765f-192">Right click the **Orchestration** and click **Start**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="5765f-193">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5765f-193">To run the sample</span></span>  
  
1.  <span data-ttu-id="5765f-194">Iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="5765f-194">Start the orchestration.</span></span>  
  
2.  <span data-ttu-id="5765f-195">Colocar los mensajes en la cola MQSeries desde la que ha configurado la ubicación de recepción para realizar la lectura.</span><span class="sxs-lookup"><span data-stu-id="5765f-195">Put messages into the MQSeries queue from which you have configured the receive location to read.</span></span>  
  
3.  <span data-ttu-id="5765f-196">Ver los mensajes en la cola de envío de WebSphere MQ Explorer en la que ha configurado el puerto de envío para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="5765f-196">View the messages in WebSphere MQ Explorer in the send queue to which you have configured the send port to send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5765f-197">Vea también</span><span class="sxs-lookup"><span data-stu-id="5765f-197">See Also</span></span>  
 [<span data-ttu-id="5765f-198">Ejemplos del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="5765f-198">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)