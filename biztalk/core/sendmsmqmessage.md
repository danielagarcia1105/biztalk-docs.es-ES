---
title: SendMSMQMessage | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, examples
- examples, MSMQ adapters
ms.assetid: 398bc396-0c66-4d55-886a-0d9bdab6476f
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c6a0f6b9e35b68fccd38d62fe7e1ae86f4f6ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024498"
---
# <a name="sendmsmqmessage"></a><span data-ttu-id="d483c-102">SendMSMQMessage</span><span class="sxs-lookup"><span data-stu-id="d483c-102">SendMSMQMessage</span></span>
<span data-ttu-id="d483c-103">En el ejemplo SendMSMQMessage se muestra cómo enviar un mensaje a un puerto de MSMQ desde una aplicación basada en .NET.</span><span class="sxs-lookup"><span data-stu-id="d483c-103">The SendMSMQMessage sample demonstrates how to send a message to an MSMQ port from a .NET-based application.</span></span> <span data-ttu-id="d483c-104">También proporciona instrucciones sobre cómo configurar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usar ubicación de recepción de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d483c-104">It also provides instructions about how to configure Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use an MSMQ receive location.</span></span>  

 <span data-ttu-id="d483c-105">Debe tener en cuenta que muchas operaciones en MSMQ son asíncronas.</span><span class="sxs-lookup"><span data-stu-id="d483c-105">You should be aware that many operations in Message Queuing are asynchronous.</span></span> <span data-ttu-id="d483c-106">Es decir, muchas llamadas de API MSMQ (por ejemplo, **System.Messaging.MessageQueue.Send**) devuelto al llamador antes de que ha completado la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="d483c-106">That is, many MSMQ API calls (for example, **System.Messaging.MessageQueue.Send**) return to the caller before the requested operation has fully completed.</span></span> <span data-ttu-id="d483c-107">MSMQ proporciona un mecanismo de envío de comentarios a la aplicación una vez completada la operación.</span><span class="sxs-lookup"><span data-stu-id="d483c-107">MSMQ provides a mechanism to deliver feedback to the application after the operation has completed.</span></span> <span data-ttu-id="d483c-108">Este mecanismo implica el uso de una cola de administración.</span><span class="sxs-lookup"><span data-stu-id="d483c-108">This mechanism involves the use of an "Admin Queue."</span></span> <span data-ttu-id="d483c-109">MSMQ devuelve los comentarios en forma de mensaje en la cola de administración.</span><span class="sxs-lookup"><span data-stu-id="d483c-109">MSMQ returns feedback in the form of a message in the Admin Queue.</span></span> <span data-ttu-id="d483c-110">La cola de administración a la que MSMQ devolverá los comentarios se especifica cuando se efectúe la llamada original de la API MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d483c-110">The Admin Queue to which MSMQ will return feedback is specified when the original MSMQ API call is made.</span></span> <span data-ttu-id="d483c-111">Así, por ejemplo, se envía un mensaje mediante la **System.Messaging.MessageQueue.Send** API, la aplicación puede especificar el nombre de una cola de administración mediante el uso de la **PROPID_M_ADMIN_QUEUE** message (propiedad) en el mensaje pasado en la llamada a **System.Messaging.MessageQueue.Send**.</span><span class="sxs-lookup"><span data-stu-id="d483c-111">So, for example, when sending a message using the **System.Messaging.MessageQueue.Send** API, the application can specify the name of an Admin Queue by using the **PROPID_M_ADMIN_QUEUE** message property on the message passed in the call to **System.Messaging.MessageQueue.Send**.</span></span> <span data-ttu-id="d483c-112">Aunque es posible la aplicación obtenga código devuelto correctamente el **System.Messaging.MessageQueue.Send** llamada, si el mensaje de operación de envío posteriormente se produce un error, MSMQ escribirá un mensaje a tal efecto en la cola de administración especificado.</span><span class="sxs-lookup"><span data-stu-id="d483c-112">Even though the application may get a successful return code on the **System.Messaging.MessageQueue.Send** call, if the message send operation subsequently fails, MSMQ writes a message to that effect to the specified Admin Queue.</span></span> <span data-ttu-id="d483c-113">Si la aplicación no especifica ninguna cola de administración, el error de envío da como resultado la pérdida del mensaje y no capturado del diagnóstico, de hecho, el mensaje desaparece sin dejar rastro.</span><span class="sxs-lookup"><span data-stu-id="d483c-113">If the application does not specify an Admin Queue, the send failure results in the message being lost and no diagnostics captured — in effect, the message disappears without any evidence.</span></span> <span data-ttu-id="d483c-114">Hay varias situaciones de error en MSMQ que pueden hacer que esto ocurra; por ejemplo, la realización de un envío no transaccional a una cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="d483c-114">There are a number of error situations in MSMQ that can cause this to happen, for example, doing a non-transactional send to a transactional queue.</span></span>  

 <span data-ttu-id="d483c-115">En el contexto de este ejemplo, es importante que el código especifique un tipo de transacción en la llamada a **System.Messaging.MessageQueue.Send** que es coherente con la compatibilidad con transacciones especificada para la cola a la que el mensaje es envía.</span><span class="sxs-lookup"><span data-stu-id="d483c-115">In the context of this sample, it is important that the code specify a transaction type in the call to **System.Messaging.MessageQueue.Send** that is consistent with the transaction support specified for the queue to which the message is sent.</span></span> <span data-ttu-id="d483c-116">Si esto último no se lleva a cabo y no se especifica ninguna cola de administración (como en el caso de este ejemplo), MSMQ descarta el mensaje enviado sin dar ninguna indicación de ello (es decir, sin que se devuelva código de error alguno a la aplicación, sin que se escriba ningún diagnóstico en el registro de eventos, etc.).</span><span class="sxs-lookup"><span data-stu-id="d483c-116">If this is not done and if no Admin Queue is specified (as is the case in this sample), then MSMQ discards the sent message with no indication that it has done so (that is, no error code returned to the application, no diagnostics written to the event log, and so on).</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="d483c-117">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="d483c-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="d483c-118">\<Ejemplos de la ruta de acceso\>\AdaptersUsage\SendMSMQMessage\\</span><span class="sxs-lookup"><span data-stu-id="d483c-118">\<Samples Path\>\AdaptersUsage\SendMSMQMessage\\</span></span>  

 <span data-ttu-id="d483c-119">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="d483c-119">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                 <span data-ttu-id="d483c-120">Archivos</span><span class="sxs-lookup"><span data-stu-id="d483c-120">Files</span></span>                                 |                                                                      <span data-ttu-id="d483c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d483c-121">Description</span></span>                                                                       |
|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d483c-122">App.ico, AssemblyInfo.cs, SendMSMQMessage.csproj, SendMSMQMessage.sln</span><span class="sxs-lookup"><span data-stu-id="d483c-122">App.ico, AssemblyInfo.cs, SendMSMQMessage.csproj, SendMSMQMessage.sln</span></span> |                           <span data-ttu-id="d483c-123">Proporciona archivos de proyecto y de solución, así como los archivos relacionados para la aplicación gráfica simple para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d483c-123">Provide project, solution, and related files for the simple graphical application for this sample.</span></span>                           |
|                         <span data-ttu-id="d483c-124">Form1.cs, Form1.resx</span><span class="sxs-lookup"><span data-stu-id="d483c-124">Form1.cs, Form1.resx</span></span>                          | <span data-ttu-id="d483c-125">Proporciona archivos de origen y formulario de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] .NET formulario para la aplicación gráfica simple para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d483c-125">Provide Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET source and form files for the simple graphical application for this sample.</span></span> |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="d483c-126">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="d483c-126">How to Use This Sample</span></span>  
 <span data-ttu-id="d483c-127">Puede usar el código de la aplicación gráfica simple incluido en este ejemplo como un ejemplo de cómo enviar mensajes a ubicaciones de recepción de MSMQ en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde aplicaciones compatibles con .NET, tal como Microsoft Office, desde páginas ASP.NET, etc.</span><span class="sxs-lookup"><span data-stu-id="d483c-127">You can use the code in the simple graphical application included with this sample as an example of how to send messages to MSMQ receive locations within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from .NET-enabled applications such as Microsoft Office, from ASP.NET pages, and so on.</span></span>  

## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="d483c-128">Crear e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d483c-128">Building and Initializing the Sample</span></span>  

#### <a name="to-build-the-sample-executable"></a><span data-ttu-id="d483c-129">Para generar el ejecutable de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d483c-129">To build the sample executable</span></span>  

1. <span data-ttu-id="d483c-130">Mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución SendMSMQMessage.sln.</span><span class="sxs-lookup"><span data-stu-id="d483c-130">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendMSMQMessage.sln.</span></span>  

2. <span data-ttu-id="d483c-131">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="d483c-131">On the **Build** menu, click **Build Solution**.</span></span>  

## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a><span data-ttu-id="d483c-132">Configuración de BizTalk Server y creación de la cola MSMQ</span><span class="sxs-lookup"><span data-stu-id="d483c-132">Configuring BizTalk Server and Creating the MSMQ Queue</span></span>  
 <span data-ttu-id="d483c-133">Use los procedimientos siguientes para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y crear la cola de MSMQ para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d483c-133">Use the following procedures to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and create the MSMQ queue for running the sample.</span></span>  

#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a><span data-ttu-id="d483c-134">Para crear la cola MSMQ en Windows Server 2008 R2 o Windows Server 2008 SP2</span><span class="sxs-lookup"><span data-stu-id="d483c-134">To create the MSMQ queue in Windows Server 2008 R2 or Windows Server 2008 SP2</span></span>  

1.  <span data-ttu-id="d483c-135">Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-135">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  

2.  <span data-ttu-id="d483c-136">Expanda el **características** nodo.</span><span class="sxs-lookup"><span data-stu-id="d483c-136">Expand the **Features** node.</span></span>  <span data-ttu-id="d483c-137">Si **Message Queue Server** no es está instalado, haga clic en **características** y seleccione **agregar características**.</span><span class="sxs-lookup"><span data-stu-id="d483c-137">If **Message Queuing** is not installed, right-click **Features** and select **Add Features**.</span></span>  <span data-ttu-id="d483c-138">Comprobar **Message Queue Server**, haga clic en **siguiente**y, a continuación, haga clic en **instalar** para instalar MSMQ en el sistema.</span><span class="sxs-lookup"><span data-stu-id="d483c-138">Check **Message Queuing**, click **Next**, and then click **Install** to install MSMQ on that system.</span></span>  

3.  <span data-ttu-id="d483c-139">Expanda el **Message Queue Server** nodo.</span><span class="sxs-lookup"><span data-stu-id="d483c-139">Expand the **Message Queuing** node.</span></span>  

4.  <span data-ttu-id="d483c-140">Haga clic en el **colas privadas** nodo, haga clic en **New**y, a continuación, haga clic en **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="d483c-140">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  

5.  <span data-ttu-id="d483c-141">En **nombre de la cola**, escriba `test`.</span><span class="sxs-lookup"><span data-stu-id="d483c-141">Under **Queue name**, enter `test`.</span></span> <span data-ttu-id="d483c-142">Asegúrese de que el **transaccional** casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="d483c-142">Ensure that the **Transactional** check box is selected.</span></span>  

6.  <span data-ttu-id="d483c-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-143">Click **OK**.</span></span>  

#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a><span data-ttu-id="d483c-144">Para crear la cola MSMQ en Windows 7 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="d483c-144">To create the MSMQ queue in Windows 7 or Windows Vista SP2</span></span>  

1.  <span data-ttu-id="d483c-145">Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-145">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  

2.  <span data-ttu-id="d483c-146">Expanda **servicios y aplicaciones**y, a continuación, expanda el **Message Queue Server** nodo.</span><span class="sxs-lookup"><span data-stu-id="d483c-146">Expand **Services and Applications**, and then expand the **Message Queuing** node.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="d483c-147">Si **Message Queue Server** no está instalado en el equipo, vaya a **Panel de Control > Programas > programas y características**y, a continuación, seleccione **o desactivar las características de Windows Active**.</span><span class="sxs-lookup"><span data-stu-id="d483c-147">If **Message Queuing** is not installed in the computer, go to **Control Panel > Programs > Programs and Features**, and then select **Turn Windows features on or off**.</span></span> <span data-ttu-id="d483c-148">Compruebe todas las características de **Microsoft Message Queue (MSMQ) Server**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-148">Check all the features under **Microsoft Message Queue (MSMQ) Server**, and then click **OK**.</span></span>  

3.  <span data-ttu-id="d483c-149">Haga clic en el **colas privadas** nodo, haga clic en **New**y, a continuación, haga clic en **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="d483c-149">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  

4.  <span data-ttu-id="d483c-150">En **nombre de la cola**, escriba **probar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-150">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="d483c-151">Asegúrese de que el **transaccional** casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="d483c-151">Ensure that the **Transactional** check box is selected.</span></span>  

5.  <span data-ttu-id="d483c-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-152">Click **OK**.</span></span>  

#### <a name="to-configure-biztalk-server"></a><span data-ttu-id="d483c-153">Para configurar BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d483c-153">To configure BizTalk Server</span></span>  

1. <span data-ttu-id="d483c-154">Seleccione una carpeta en la que recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="d483c-154">Select a folder in which to receive messages.</span></span> <span data-ttu-id="d483c-155">En los siguientes pasos se da por supuesto que ha seleccionado C:\Demo\Report, pero puede ajustar los pasos según sea necesario para otra carpeta.</span><span class="sxs-lookup"><span data-stu-id="d483c-155">The following steps assume that you have selected C:\Demo\Report, but you can adjust the steps as necessary for another folder.</span></span>  

2. <span data-ttu-id="d483c-156">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d483c-156">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

3. <span data-ttu-id="d483c-157">Cree una nueva aplicación denominada **MSMQSample**.</span><span class="sxs-lookup"><span data-stu-id="d483c-157">Create a new application named **MSMQSample**.</span></span>  

4. <span data-ttu-id="d483c-158">Haga clic en **puertos de recepción**, haga clic en **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="d483c-158">Right-click **Receive Ports**, click **New**, and then click **One-way Receive Port**.</span></span>  

5. <span data-ttu-id="d483c-159">En el **propiedades de puerto de recepción** cuadro de diálogo el **nombre** escriba **MyReceivePort**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-159">In the **Receive Port Properties** dialog box, in the **Name** box enter **MyReceivePort**, and then click **OK**.</span></span>  

6. <span data-ttu-id="d483c-160">Haga clic en **ubicaciones de recepción**, haga clic en **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="d483c-160">Right-click **Receive Locations**, click **New**, and then click **One-way Receive Location**.</span></span> <span data-ttu-id="d483c-161">En el **seleccionar un puerto de recepción** cuadro de diálogo, seleccione el puerto de recepción recién creado y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-161">In the **Select a Receive Port** dialog box, select the receive port you just created and click **OK**.</span></span>  

7. <span data-ttu-id="d483c-162">En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** , escriba un nombre para el puerto de recepción, tales como **MSMQReceiveLocation**.</span><span class="sxs-lookup"><span data-stu-id="d483c-162">In the **Receive Location Properties** dialog box, in the **Name** box, type a name for the receive port, such as **MSMQReceiveLocation**.</span></span>  

8. <span data-ttu-id="d483c-163">En el **propiedades de ubicación de recepción** cuadro de diálogo, el tipo de transporte, seleccione **MSMQ** .</span><span class="sxs-lookup"><span data-stu-id="d483c-163">In the **Receive Location Properties** dialog box, for the transport type, select **MSMQ** .</span></span>  

9. <span data-ttu-id="d483c-164">Haga clic en **configurar** para abrir el **propiedades de transporte de MSMQ** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d483c-164">Click **Configure** to open the **MSMQ Transport Properties** dialog box.</span></span> <span data-ttu-id="d483c-165">Establecer **cola** a `localhost\private$\test`, establezca **transaccional** a `True`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-165">Set **Queue** to `localhost\private$\test`, set **Transactional** to `True`, and then click **OK**.</span></span>  

10. <span data-ttu-id="d483c-166">Expanda la aplicación, seleccione **puertos de envío**, seleccione **New**, seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="d483c-166">Expand the application, select **Send Ports**, select **New**, select **Static One-way Send Port**.</span></span>  

11. <span data-ttu-id="d483c-167">En el **propiedades de puerto de envío** cuadro de diálogo el **nombre** , escriba un nombre para el puerto de envío como **MySendPort**.</span><span class="sxs-lookup"><span data-stu-id="d483c-167">In the **Send Port Properties** dialog box, in the **Name** box, type a name for the send port, such as **MySendPort**.</span></span>  

12. <span data-ttu-id="d483c-168">Establecer el **tipo de transporte** propiedad **archivo**.</span><span class="sxs-lookup"><span data-stu-id="d483c-168">Set the **Transport Type** property to **FILE**.</span></span>  

13. <span data-ttu-id="d483c-169">Haga clic en **configurar** para abrir el **propiedades de transporte File** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d483c-169">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>  

14. <span data-ttu-id="d483c-170">En el **propiedades de transporte de archivo** cuadro de diálogo, establezca el **carpeta de destino** propiedad **C:\Demo\Report**, mantenga la configuración predeterminada para las demás propiedades y, a continuación, Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-170">In the **FILE Transport Properties** dialog box, set the **Destination Folder** property to **C:\Demo\Report**, keep the default settings for the other properties, and then click **OK**.</span></span>  

15. <span data-ttu-id="d483c-171">Seleccione **filtros**y, a continuación, agregue una nueva fila estableciendo **propiedad** a **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="d483c-171">Select **Filters**, and then add a new row by setting **Property** to **BTS.ReceivePortName**.</span></span> <span data-ttu-id="d483c-172">Deje el **operador** columna establecida en **==**, establezca el **valor** columna **MyReceivePort**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-172">Leave the **Operator** column set to **==**, set the **Value** column to **MyReceivePort**, and then click **OK**.</span></span>  

16. <span data-ttu-id="d483c-173">Con el botón secundario el nuevo puerto de envío y, a continuación, haga clic en **Enlist**.</span><span class="sxs-lookup"><span data-stu-id="d483c-173">Right-click your new send port, and then click **Enlist**.</span></span>  

17. <span data-ttu-id="d483c-174">Con el botón secundario el nuevo puerto de envío nuevo y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-174">Right-click your new send port again, and then click **Start**.</span></span>  

18. <span data-ttu-id="d483c-175">Haga que la nueva ubicación de recepción y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="d483c-175">Right-click your new receive location, and then click **Enable**.</span></span>  

    <span data-ttu-id="d483c-176">Ahora, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] estará preparado para trabajar con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d483c-176">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is now ready to work with this sample.</span></span>  

## <a name="running-the-sample"></a><span data-ttu-id="d483c-177">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="d483c-177">Running the Sample</span></span>  
 <span data-ttu-id="d483c-178">Utilice el siguiente procedimiento para ejecutar el ejemplo SendMSMQMessage.</span><span class="sxs-lookup"><span data-stu-id="d483c-178">Use the following procedure to run the SendMSMQMessage sample.</span></span>  

#### <a name="to-run-the-sample"></a><span data-ttu-id="d483c-179">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d483c-179">To run the sample</span></span>  

1. <span data-ttu-id="d483c-180">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="d483c-180">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="d483c-181">\<Ejemplos de la ruta de acceso\>\AdaptersUsage\SendMSMQMessage\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="d483c-181">\<Samples Path\>\AdaptersUsage\SendMSMQMessage\bin\Debug</span></span>  

2. <span data-ttu-id="d483c-182">Ejecute el archivo SendMSMQMessage.exe, que inicia la aplicación gráfica que proporciona la interfaz de usuario de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d483c-182">Run the file SendMSMQMessage.exe, which starts the graphical application that provides the user interface for this sample.</span></span>  

3. <span data-ttu-id="d483c-183">En la aplicación gráfica, en la **el nombre del equipo de BizTalk** , escriba el nombre del equipo local.</span><span class="sxs-lookup"><span data-stu-id="d483c-183">In the graphical application, in the **BizTalk machine name** box, type the name of the local computer.</span></span>  

4. <span data-ttu-id="d483c-184">Pruebe el **enviar con ajuste** opción:</span><span class="sxs-lookup"><span data-stu-id="d483c-184">Try the **Send Wrapped** option:</span></span>  

   1. <span data-ttu-id="d483c-185">Si lo desea, cambie el texto en el **cuerpo del mensaje** cuadro.</span><span class="sxs-lookup"><span data-stu-id="d483c-185">Optionally change the text in the **Message body** box.</span></span>  

   2. <span data-ttu-id="d483c-186">Haga clic en **enviar ajustada**.</span><span class="sxs-lookup"><span data-stu-id="d483c-186">Click **Send wrapped**.</span></span>  

      <span data-ttu-id="d483c-187">Si la operación se realiza correctamente, verá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d483c-187">If the operation succeeds, you will see the following:</span></span>  

   - <span data-ttu-id="d483c-188">La palabra **éxito** aparece en color rojo en el cuadro justo encima de los botones.</span><span class="sxs-lookup"><span data-stu-id="d483c-188">The word **Success** appears in red font in the box immediately above the buttons.</span></span>  

   - <span data-ttu-id="d483c-189">Aparecerá un archivo en la carpeta de destino, C:\Demo\Reports.</span><span class="sxs-lookup"><span data-stu-id="d483c-189">A file appears in your destination folder, C:\Demo\Reports.</span></span> <span data-ttu-id="d483c-190">Este archivo contiene el texto de la **cuerpo del mensaje** cuadro ajustado en etiquetas simples de XML por la biblioteca de puesta en cola de mensajes. NET.</span><span class="sxs-lookup"><span data-stu-id="d483c-190">This file contains the text from the **Message body** box wrapped in simple XML tags by the .NET message queuing library.</span></span>  

     <span data-ttu-id="d483c-191">Si se produce un error en la operación, verá un mensaje de error en el cuadro justo encima de los botones.</span><span class="sxs-lookup"><span data-stu-id="d483c-191">If the operation fails, you will see an error message in the box immediately above the buttons.</span></span>  

5. <span data-ttu-id="d483c-192">Pruebe el **envío exacto** opción:</span><span class="sxs-lookup"><span data-stu-id="d483c-192">Try the **Send Exact** option:</span></span>  

   1. <span data-ttu-id="d483c-193">Si lo desea, cambie el texto en el **cuerpo del mensaje** cuadro.</span><span class="sxs-lookup"><span data-stu-id="d483c-193">Optionally change the text in the **Message body** box.</span></span>  

   2. <span data-ttu-id="d483c-194">Haga clic en **envío exacto**.</span><span class="sxs-lookup"><span data-stu-id="d483c-194">Click **Send exact**.</span></span>  

      <span data-ttu-id="d483c-195">Si la operación se realiza correctamente, verá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d483c-195">If the operation succeeds, you will see the following:</span></span>  

   - <span data-ttu-id="d483c-196">La palabra **éxito** aparece en color rojo en el cuadro justo encima de los botones.</span><span class="sxs-lookup"><span data-stu-id="d483c-196">The word **Success** appears in red font in the box immediately above the buttons.</span></span>  

   - <span data-ttu-id="d483c-197">Aparecerá un archivo en la carpeta de destino, C:\Demo\Reports.</span><span class="sxs-lookup"><span data-stu-id="d483c-197">A file appears in your destination folder, C:\Demo\Reports.</span></span> <span data-ttu-id="d483c-198">Este archivo contiene el texto de la **cuerpo del mensaje** cuadro exactamente como aparece en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d483c-198">This file contains the text from the **Message body** box exactly as it appears in the text box.</span></span>  

     <span data-ttu-id="d483c-199">Si se produce un error en la operación, verá un mensaje de error en el cuadro justo encima de los botones.</span><span class="sxs-lookup"><span data-stu-id="d483c-199">If the operation fails, you will see an error message in the box immediately above the buttons.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d483c-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="d483c-200">See Also</span></span>  
 [<span data-ttu-id="d483c-201">Ejemplos de adaptadores: uso</span><span class="sxs-lookup"><span data-stu-id="d483c-201">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)