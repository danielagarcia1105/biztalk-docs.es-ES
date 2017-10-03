---
title: MQSCorrelationSetOrchestration (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: fcda65d0-e3ec-4ead-978d-3904903b8762
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea8de4f60907e465f37502b5b0227e31ddcd92b5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqscorrelationsetorchestration-biztalk-server-sample"></a><span data-ttu-id="61a18-102">MQSCorrelationSetOrchestration (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="61a18-102">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="61a18-103">El ejemplo MQSCorrelationSetOrchestration muestra cómo usar el identificador de correlación MQSeries para correlacionar los mensajes enviados a una cola de MQSeries de vuelta a una orquestación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="61a18-103">The MQSCorrelationSetOrchestration sample demonstrates how to use the MQSeries correlation identifier for correlating messages sent to an MQSeries queue back to a running orchestration.</span></span> <span data-ttu-id="61a18-104">La orquestación establece el identificador de correlación de MQSeries y el mensaje valores de identificador mediante la **MQMD_CorrelId** y **MQMD_MsgID** propiedades.</span><span class="sxs-lookup"><span data-stu-id="61a18-104">The orchestration sets the MQSeries correlation identifier and message identifier values using the **MQMD_CorrelId** and **MQMD_MsgID** properties.</span></span> <span data-ttu-id="61a18-105">El administrador de cola de MQSeries copia el valor de MessageID en la propiedad CorrelationID del mensaje.</span><span class="sxs-lookup"><span data-stu-id="61a18-105">The MQSeries Queue Manager copies the MessageID value to the CorrelationID property of the message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61a18-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="61a18-106">Prerequisites</span></span>  
 <span data-ttu-id="61a18-107">En este ejemplo se presupone que ha instalado IBM WebSphere MQSeries en el mismo servidor en el que se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61a18-107">This sample assumes that you have installed IBM WebSphere MQSeries on the same server that you are running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="61a18-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="61a18-108">What This Sample Does</span></span>  
 <span data-ttu-id="61a18-109">En este ejemplo se muestra cómo establecer un identificador de mensaje y de correlación en un mensaje enviado a un servidor IBM WebSphere MQSeries Server.</span><span class="sxs-lookup"><span data-stu-id="61a18-109">This sample illustrates how to set a message identifier and correlation identifier in a message sent to an IBM WebSphere MQSeries Server.</span></span> <span data-ttu-id="61a18-110">Es un método que se puede utilizar para correlacionar un mensaje de vuelta a una instancia de orquestación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="61a18-110">This is one method that can be used to correlate a message back to a running orchestration instance.</span></span> <span data-ttu-id="61a18-111">Cuando el administrador de cola de MQSeries recibe el mensaje, copia el valor de MessageID en la propiedad CorrelationID del mensaje.</span><span class="sxs-lookup"><span data-stu-id="61a18-111">When the MQSeries Queue Manager receives the message it copies the MessageID value to the CorrelationID property of the message.</span></span> <span data-ttu-id="61a18-112">Este CorrelationID (**MQMD_CorrelId**), a continuación, se utiliza en la orquestación para asociar el mensaje de respuesta en MQSeries con la instancia que se usan para enviar mensajes a MQSeries.</span><span class="sxs-lookup"><span data-stu-id="61a18-112">This CorrelationID (**MQMD_CorrelId**) is then used in the orchestration to associate the response message on MQSeries with the instance used to send messages to MQSeries.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="61a18-113">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="61a18-113">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="61a18-114">En este ejemplo se muestra un escenario en el que un documento que una orquestación está procesando puede enviarse a una cola MQSeries (supuestamente para otro procesamiento) y devolverse a la orquestación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="61a18-114">This sample illustrates a scenario in which a document that is being processed by an orchestration can be sent to an MQSeries queue (presumably for additional processing) and returned back to the running orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="61a18-115">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="61a18-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="61a18-116">*\<Ejemplos de ruta de acceso >*\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration</span><span class="sxs-lookup"><span data-stu-id="61a18-116">*\<Samples Path>*\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration</span></span>  
  
 <span data-ttu-id="61a18-117">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="61a18-117">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="61a18-118">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="61a18-118">**File**</span></span>|<span data-ttu-id="61a18-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="61a18-119">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="61a18-120">**MQSCorrelationSetOrchestration.btproj,**</span><span class="sxs-lookup"><span data-stu-id="61a18-120">**MQSCorrelationSetOrchestration.btproj,**</span></span><br /><br /> <span data-ttu-id="61a18-121">**MQSCorrelationSetOrchestration.sln**</span><span class="sxs-lookup"><span data-stu-id="61a18-121">**MQSCorrelationSetOrchestration.sln**</span></span>|<span data-ttu-id="61a18-122">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61a18-122">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="61a18-123">**MQSCorrelationSetOrchestration.odx**</span><span class="sxs-lookup"><span data-stu-id="61a18-123">**MQSCorrelationSetOrchestration.odx**</span></span>|<span data-ttu-id="61a18-124">La orquestación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61a18-124">The orchestration of the application.</span></span>|  
|<span data-ttu-id="61a18-125">**MQSCorrelationSetOrchestration.snk**</span><span class="sxs-lookup"><span data-stu-id="61a18-125">**MQSCorrelationSetOrchestration.snk**</span></span>|<span data-ttu-id="61a18-126">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="61a18-126">The strong naming key file.</span></span>|  
|<span data-ttu-id="61a18-127">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="61a18-127">**Setup.bat**</span></span>|<span data-ttu-id="61a18-128">Crea e inicializa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="61a18-128">Builds and initializes this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="61a18-129">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="61a18-129">How to Use This Sample</span></span>  
 <span data-ttu-id="61a18-130">Incorpore la lógica utilizada en este ejemplo si necesita enviar un mensaje a MQSeries Server como uno de los pasos en el flujo de trabajo global.</span><span class="sxs-lookup"><span data-stu-id="61a18-130">Incorporate the logic employed in this sample if you need to send a message to MQSeries Server as one of the steps in overall workflow.</span></span>  
  
### <a name="to-create-the-mqseries-queue-through-the-websphere-mq-explorer"></a><span data-ttu-id="61a18-131">Para crear la cola MQSeries mediante WebSphere MQ Explorer</span><span class="sxs-lookup"><span data-stu-id="61a18-131">To create the MQSeries queue through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="61a18-132">Haga clic en **iniciar**, seleccione **programas**, seleccione **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.</span><span class="sxs-lookup"><span data-stu-id="61a18-132">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="61a18-133">Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="61a18-133">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="61a18-134">El Administrador de cola predeterminado se suele llamar **QM_ < nombre_equipo >** donde *nombre_equipo* es el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="61a18-134">The default queue manager is typically named **QM_<machine_name>** where *machine_name* is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="61a18-135">Haga clic en **colas**, seleccione **New**y, a continuación, haga clic en **cola Local**.</span><span class="sxs-lookup"><span data-stu-id="61a18-135">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="61a18-136">En **Create Local Queue** cuadro de diálogo **nombre de la cola**, escriba "MQCorrelation" y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-136">In **Create Local Queue** dialog box, in **Queue Name**, type "MQCorrelation", and then click **OK**.</span></span>  
  
### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="61a18-137">Para crear la ubicación de recepción y la cola de MQSeries</span><span class="sxs-lookup"><span data-stu-id="61a18-137">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="61a18-138">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="61a18-138">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="61a18-139">Expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación necesaria.</span><span class="sxs-lookup"><span data-stu-id="61a18-139">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="61a18-140">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="61a18-140">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="61a18-141">En el **propiedades del puerto de recepción unidireccional** cuadro de diálogo, en la **nombre** cuadro, escriba "MQIn" y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-141">In the **One-way Receive Port Properties** dialog box, in the **Name** box type "MQIn" and click **OK**.</span></span>  
  
5.  <span data-ttu-id="61a18-142">En el panel izquierdo, haga clic en **ubicaciones de recepción** ficha y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="61a18-142">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="61a18-143">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba "MQIn".</span><span class="sxs-lookup"><span data-stu-id="61a18-143">In the **Receive Location Properties** dialog box, in the **Name** box, type "MQIn".</span></span>  
  
7.  <span data-ttu-id="61a18-144">En el **tipo de transporte** cuadro, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="61a18-144">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="61a18-145">En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="61a18-145">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="61a18-146">En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="61a18-146">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="61a18-147">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-147">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="61a18-148">En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **intervalo de sondeo** , escriba "10".</span><span class="sxs-lookup"><span data-stu-id="61a18-148">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type "10".</span></span>  
  
12. <span data-ttu-id="61a18-149">En el **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="61a18-149">In the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
13. <span data-ttu-id="61a18-150">En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="61a18-150">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="61a18-151">En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="61a18-151">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
15. <span data-ttu-id="61a18-152">En el **cola** , escriba "MQCorrelation" y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-152">In the **Queue** box, type "MQCorrelation", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="61a18-153">En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en**Aceptar**o **realiza** hasta que haya salido de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="61a18-153">In the **Export** dialog box, click **Create Queue**, and then click**OK**or **Done** until you have exited all dialog boxes.</span></span>  
  
### <a name="to-create-the-send-port-to-mqseries"></a><span data-ttu-id="61a18-154">Para crear el puerto de envío en MQSeries</span><span class="sxs-lookup"><span data-stu-id="61a18-154">To create the send port to MQSeries</span></span>  
  
1.  <span data-ttu-id="61a18-155">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="61a18-155">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="61a18-156">En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , escriba "MQOut".</span><span class="sxs-lookup"><span data-stu-id="61a18-156">In the **Send Port Properties** dialog box, in the **Name** box, type "MQOut".</span></span>  
  
3.  <span data-ttu-id="61a18-157">En el **tipo de transporte** cuadro, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="61a18-157">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="61a18-158">En el **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="61a18-158">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="61a18-159">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-159">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="61a18-160">En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="61a18-160">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
7.  <span data-ttu-id="61a18-161">En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="61a18-161">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
8.  <span data-ttu-id="61a18-162">En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="61a18-162">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
9. <span data-ttu-id="61a18-163">En el **cola** , escriba "MQCorrelation" y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-163">In the **Queue** box, type "MQCorrelation", and then click **OK**.</span></span>  
  
10. <span data-ttu-id="61a18-164">Haga clic en **Aceptar** hasta que haya salido de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="61a18-164">Click **OK** until you have exited all dialog boxes.</span></span>  
  
### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="61a18-165">Para habilitar la ubicación de recepción e iniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="61a18-165">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="61a18-166">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="61a18-166">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="61a18-167">En el panel de detalles, haga clic en el **MQIn** ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-167">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="61a18-168">En el panel de detalles, haga clic en el **MQOut** puerto de envío y haga clic en **iniciar.**</span><span class="sxs-lookup"><span data-stu-id="61a18-168">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
### <a name="to-create-the-folders-used-by-the-application"></a><span data-ttu-id="61a18-169">Para crear las carpetas usadas por la aplicación</span><span class="sxs-lookup"><span data-stu-id="61a18-169">To create the folders used by the application</span></span>  
  
1.  <span data-ttu-id="61a18-170">En su **C:\\**  unidad, cree una carpeta denominada "temp" Si aún no existe.</span><span class="sxs-lookup"><span data-stu-id="61a18-170">On your **C:\\** drive, create a folder named "temp" if it does not already exist.</span></span>  
  
2.  <span data-ttu-id="61a18-171">En el **C:\temp** directorio, cree carpetas denominadas "Pickup" y "Dropit".</span><span class="sxs-lookup"><span data-stu-id="61a18-171">Under the **C:\temp** directory, create folders named "Pickup" and "Dropit".</span></span>  
  
### <a name="building-and-deploying-this-sample"></a><span data-ttu-id="61a18-172">Generar e implementar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="61a18-172">Building and deploying this sample</span></span>  
  
1.  <span data-ttu-id="61a18-173">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="61a18-173">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration`  
  
2.  <span data-ttu-id="61a18-174">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="61a18-174">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    1.  <span data-ttu-id="61a18-175">Crea una clave de nombre seguro para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="61a18-175">Creates a strong name key for the project.</span></span>  
  
    2.  <span data-ttu-id="61a18-176">Compila e implementa el proyecto de orquestación.</span><span class="sxs-lookup"><span data-stu-id="61a18-176">Compiles and deploys the orchestration project.</span></span>  
  
    3.  <span data-ttu-id="61a18-177">Crea un puerto de envío y un puerto de recepción con el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="61a18-177">Creates a send port and a receive port with the File adapter.</span></span>  
  
### <a name="bind-and-start-the-orchestration"></a><span data-ttu-id="61a18-178">Enlazar e iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="61a18-178">Bind and start the Orchestration</span></span>  
  
1.  <span data-ttu-id="61a18-179">En la consola de administración de BizTalk Server, expanda el **orquestaciones** carpeta.</span><span class="sxs-lookup"><span data-stu-id="61a18-179">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="61a18-180">En el panel de detalles, haga clic en el **MQSCorrelationSetOrchestration** orquestación y, a continuación, haga clic en **enlazar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-180">In the details pane, right-click the **MQSCorrelationSetOrchestration** orchestration, and then click **Bind**.</span></span>  
  
3.  <span data-ttu-id="61a18-181">Enlace los puertos de orquestación con los siguientes puertos de envío y ubicaciones de recepción:</span><span class="sxs-lookup"><span data-stu-id="61a18-181">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="61a18-182">**Puerto de orquestación**</span><span class="sxs-lookup"><span data-stu-id="61a18-182">**Orchestration Port**</span></span>|<span data-ttu-id="61a18-183">**Puerto de mensajería / ubicación de recepción**</span><span class="sxs-lookup"><span data-stu-id="61a18-183">**Messaging Port / Receive Location**</span></span>|  
    |----------------------------|--------------------------------------------|  
    |<span data-ttu-id="61a18-184">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="61a18-184">FileReceivePort</span></span>|<span data-ttu-id="61a18-185">MQSCorrelationSetOrchestration.FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="61a18-185">MQSCorrelationSetOrchestration.FileReceivePort</span></span>|  
    |<span data-ttu-id="61a18-186">MQSeriesResponseReceivePort</span><span class="sxs-lookup"><span data-stu-id="61a18-186">MQSeriesResponseReceivePort</span></span>|<span data-ttu-id="61a18-187">MQIn</span><span class="sxs-lookup"><span data-stu-id="61a18-187">MQIn</span></span>|  
    |<span data-ttu-id="61a18-188">MQSeriesRequestSendPort</span><span class="sxs-lookup"><span data-stu-id="61a18-188">MQSeriesRequestSendPort</span></span>|<span data-ttu-id="61a18-189">MQOut</span><span class="sxs-lookup"><span data-stu-id="61a18-189">MQOut</span></span>|  
    |<span data-ttu-id="61a18-190">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="61a18-190">FileSendPort</span></span>|<span data-ttu-id="61a18-191">MQSCorrelationSetOrchestration.FileSendPort</span><span class="sxs-lookup"><span data-stu-id="61a18-191">MQSCorrelationSetOrchestration.FileSendPort</span></span>|  
  
4.  <span data-ttu-id="61a18-192">Haga clic en **Host**.</span><span class="sxs-lookup"><span data-stu-id="61a18-192">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="61a18-193">En el **Host** cuadro, seleccione **BizTalkServerApplication**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-193">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="61a18-194">En **puertos de envío**, haga clic en **MQSCorrelationSetOrchestration.FileSendPort**y, a continuación, seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-194">In **Send Ports**, right-click **MQSCorrelationSetOrchestration.FileSendPort**, and then select **Start**.</span></span>  
  
7.  <span data-ttu-id="61a18-195">En **ubicaciones de recepción**, haga clic en **MQSCorrelationSetOrchestration.FileReceivePort** y, a continuación, seleccione **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-195">In **Receive Locations**, right-click **MQSCorrelationSetOrchestration.FileReceivePort** and then select **Enable**.</span></span>  
  
8.  <span data-ttu-id="61a18-196">Haga clic en la orquestación y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="61a18-196">Right-click the orchestration and click **Start**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61a18-197">Además, iniciar la orquestación da de alta la orquestación de forma automática.</span><span class="sxs-lookup"><span data-stu-id="61a18-197">Starting the orchestration also automatically enlists the orchestration.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="61a18-198">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="61a18-198">To test the application</span></span>  
  
1.  <span data-ttu-id="61a18-199">Coloque un archivo en el **C:\Temp\Pickup** carpeta.</span><span class="sxs-lookup"><span data-stu-id="61a18-199">Put a file into the **C:\Temp\Pickup** folder.</span></span>  
  
2.  <span data-ttu-id="61a18-200">Examine el archivo de la **C:\Temp\Dropit** carpeta.</span><span class="sxs-lookup"><span data-stu-id="61a18-200">Examine the file in the **C:\Temp\Dropit** folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61a18-201">Si deshabilita la **MQIn** ubicación de recepción, puede examinar el mensaje en WebSphere MQ Explorer y observar que se establecen los identificadores de mensaje y correlación.</span><span class="sxs-lookup"><span data-stu-id="61a18-201">If you disable the **MQIn** receive location, you can examine the message in WebSphere MQ Explorer and see that the message and correlation identifiers are set.</span></span> <span data-ttu-id="61a18-202">Para ello, inicie la **WebSphere MQ Explorer** y examine el mensaje colocado en el **MQCorrelation** cola.</span><span class="sxs-lookup"><span data-stu-id="61a18-202">To do this, launch the **WebSphere MQ Explorer** and examine the message placed in the **MQCorrelation** queue.</span></span> <span data-ttu-id="61a18-203">Los identificadores de mensaje y correlación aparecen en la **identificadores** pestaña de la **propiedades de mensaje** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="61a18-203">The message and correlation identifiers are displayed on the **Identifiers** tab of the **Message properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61a18-204">En una situación de producción, deseará asignar un identificador único a cada mensaje que se envía a la cola de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="61a18-204">In a production scenario, you will want to assign a unique ID for each message that is sent to the MQSeries queue.</span></span> <span data-ttu-id="61a18-205">Esto se puede hacer modificando la forma de expresión en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="61a18-205">This can be done by modifying the expression shape in the orchestration.</span></span> <span data-ttu-id="61a18-206">Cambie las líneas siguientes para establecer estas propiedades en un identificador único de 24 bytes:</span><span class="sxs-lookup"><span data-stu-id="61a18-206">Change the following lines to set these properties to a unique 24 byte ID:</span></span>  
    >   
    >  <span data-ttu-id="61a18-207">MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";</span><span class="sxs-lookup"><span data-stu-id="61a18-207">MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";</span></span>  
    >   
    >  <span data-ttu-id="61a18-208">MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";</span><span class="sxs-lookup"><span data-stu-id="61a18-208">MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";</span></span>  
    >   
    >  <span data-ttu-id="61a18-209">Si desea establecer un identificador de 24 bytes único para estas propiedades, vea la sección **para crear un identificador de 24 bytes único para los mensajes enviados a MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="61a18-209">If you want to set a unique 24 byte ID for these properties see the section **To create a unique 24 byte ID for messages sent to MQSeries**.</span></span>  
  
### <a name="to-create-a-unique-24-byte-id-for-messages-sent-to-mqseries"></a><span data-ttu-id="61a18-210">Para crear un identificador de 24 bytes único para mensajes enviados a MQSeries</span><span class="sxs-lookup"><span data-stu-id="61a18-210">To create a unique 24 byte ID for messages sent to MQSeries</span></span>  
  
1.  <span data-ttu-id="61a18-211">Cree un proyecto nuevo de biblioteca de clases C# en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61a18-211">Create a new C# class library project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="61a18-212">Pegue el código siguiente en el archivo .cs para la clase:</span><span class="sxs-lookup"><span data-stu-id="61a18-212">Paste the following code into the .cs file for the class:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Security.Cryptography;  
  
    namespace MQId  
    {[Serializable]  
        public class GetId  
        {  
            RNGCryptoServiceProvider randomCryptoString = new RNGCryptoServiceProvider();  
  
            public string getGuidstr()  
            {  
                byte[] newGuid = GetRandomData(24);  
                return ConvertToHex(newGuid);  
            }  
  
            private byte[] GetRandomData(int keySize)  
            {  
                byte[] randomData = new byte[keySize];  
                randomCryptoString.GetBytes(randomData);  
                return randomData;  
            }  
  
            private string ConvertToHex(byte[] key)  
            {  
                StringBuilder hexString = new StringBuilder();  
                for (int i = 0; i < key.Length; ++i)  
                {  
                    hexString.Append(String.Format("{0:X2}", key[i]));  
                }  
                return hexString.ToString();  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="61a18-213">Especifique un **espacio de nombres predeterminado** de **MQId** y **nombre de ensamblado** de **GetId** en las propiedades del proyecto **aplicación**  página.</span><span class="sxs-lookup"><span data-stu-id="61a18-213">Specify a **Default namespace** of **MQId** and an **Assembly name** of **GetId** on the project properties **Application** page.</span></span>  
  
4.  <span data-ttu-id="61a18-214">Especifique un archivo de clave de nombre seguro para firmar el ensamblado en las propiedades del proyecto **firma** página y, a continuación, compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="61a18-214">Specify a strong name key file to sign the assembly on the project properties **Signing** page and then build the project.</span></span>  
  
5.  <span data-ttu-id="61a18-215">Use la herramienta de caché global de ensamblados (gacutil.exe) para cargar el ensamblado compilado en la GAC (gacutil /i \< *nombre de archivo dll compilado*>).</span><span class="sxs-lookup"><span data-stu-id="61a18-215">Use the global assembly cache tool (gacutil.exe) to load the compiled assembly into the GAC (gacutil /i \<*name of compiled dll file*>).</span></span>  
  
6.  <span data-ttu-id="61a18-216">Agregue una referencia al ensamblado GetId en el proyecto de BizTalk para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="61a18-216">Add a reference to the GetId assembly in the BizTalk project for this sample.</span></span>  
  
7.  <span data-ttu-id="61a18-217">Agregue dos variables para la orquestación usada en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61a18-217">Add two variables to the orchestration used in this sample:</span></span>  
  
    |<span data-ttu-id="61a18-218">Nombre de variable (identificador)</span><span class="sxs-lookup"><span data-stu-id="61a18-218">Variable name (Identifier)</span></span>|<span data-ttu-id="61a18-219">Tipo</span><span class="sxs-lookup"><span data-stu-id="61a18-219">Type</span></span>|  
    |----------------------------------|----------|  
    |<span data-ttu-id="61a18-220">GetId</span><span class="sxs-lookup"><span data-stu-id="61a18-220">GetId</span></span>|<span data-ttu-id="61a18-221">MQId.GetId</span><span class="sxs-lookup"><span data-stu-id="61a18-221">MQId.GetId</span></span>|  
    |<span data-ttu-id="61a18-222">strGuid</span><span class="sxs-lookup"><span data-stu-id="61a18-222">strGuid</span></span>|<span data-ttu-id="61a18-223">System.String</span><span class="sxs-lookup"><span data-stu-id="61a18-223">System.String</span></span>|  
  
8.  <span data-ttu-id="61a18-224">Pegue el código siguiente en la forma de expresión usada en la orquestación de este ejemplo; este código debe invalidar el código existente:</span><span class="sxs-lookup"><span data-stu-id="61a18-224">Paste the following code into the expression shape used in the orchestration for this sample, this code should overwrite the existing code:</span></span>  
  
    ```  
    GetId = new MQId.GetId();  
    strGuid = GetId.getGuidstr();  
    MQSeriesRequestSendMessageModified = MQSeriesRequestSendMessage;  
    MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = strGuid;  
    MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = strGuid;  
    ```  
  
9. <span data-ttu-id="61a18-225">Detenga y quite la orquestación de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] si ya está implementada.</span><span class="sxs-lookup"><span data-stu-id="61a18-225">Stop and remove the orchestration in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console if it is already deployed.</span></span> <span data-ttu-id="61a18-226">A continuación, siga los pasos descritos en las secciones **generar e implementar este ejemplo**, **enlazar e iniciar la orquestación** y **para probar la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="61a18-226">Then follow the steps in the sections **Building and deploying this sample**, **Bind and start the Orchestration** and **To test the application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61a18-227">El uso de este método para crear un identificador de 24 bytes único para los mensajes enviados a MQSeries no garantiza al 100% identificadores únicos para todos los mensajes que se envían, pero la probabilidad de identificadores de mensaje duplicados es muy baja.</span><span class="sxs-lookup"><span data-stu-id="61a18-227">Use of this method to create a unique 24 byte ID for messages sent to MQSeries does not 100% guarantee unique IDs for all messages sent but the probability of duplicate message IDs is very low.</span></span> <span data-ttu-id="61a18-228">Si las necesidades empresariales requieren una garantía al 100% de que no se duplicará ningún identificador de mensaje, entonces será necesario implementar un código personalizado diferente para garantizar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="61a18-228">If business needs require a 100% guarantee that no message IDs are duplicated then you will need to employ different custom code to ensure this functionality.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="61a18-229">Clases o métodos usados en el ejemplo</span><span class="sxs-lookup"><span data-stu-id="61a18-229">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="61a18-230">En este ejemplo no se utilizan de manera explícita ninguna clase o método.</span><span class="sxs-lookup"><span data-stu-id="61a18-230">This sample does not make explicit use of any classes or methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a18-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="61a18-231">See Also</span></span>  
 <span data-ttu-id="61a18-232">[Correlacionar mensajes mediante la solicitud y respuesta](../core/correlating-messages-using-request-reply.md) </span><span class="sxs-lookup"><span data-stu-id="61a18-232">[Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md) </span></span>  
 [<span data-ttu-id="61a18-233">Ejemplos de adaptadores de MQSeries</span><span class="sxs-lookup"><span data-stu-id="61a18-233">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)