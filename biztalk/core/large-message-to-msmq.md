---
title: "Mensajes de gran tamaño a MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1fb87b46-5656-42c0-be99-8ab66e51bb4d
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 008e6c2d775fc5d46977ca4672b6d3376349b3f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="large-message-to-msmq"></a><span data-ttu-id="1f3a7-102">Mensajes de gran tamaño a MSMQ</span><span class="sxs-lookup"><span data-stu-id="1f3a7-102">Large Message to MSMQ</span></span>
<span data-ttu-id="1f3a7-103">Los mensajes de gran tamaño al ejemplo MSMQ se muestra cómo enviar un documento .xml mayor de 4 megabytes (MB) de Message Queue Server (también conocido como MSMQ) para el adaptador de MSMQ de BizTalk mediante el uso de la **MQSendLargeMessage** API implementada por MQRTLarge.dll.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-103">The Large Message to MSMQ sample demonstrates how to send an .xml document larger than 4 megabytes (MB) from Message Queuing (also known as MSMQ) to the BizTalk MSMQ adapter by using the **MQSendLargeMessage** API implemented by MQRTLarge.dll.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1f3a7-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f3a7-104">What This Sample Does</span></span>  
 <span data-ttu-id="1f3a7-105">El ejemplo funciona como se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="1f3a7-105">The sample works as follows:</span></span>  
  
1.  <span data-ttu-id="1f3a7-106">Un usuario usa SendLargeMessage.exe para enviar un archivo .xml de gran tamaño a una cola de un equipo local.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-106">A user uses SendLargeMessage.exe to send a large .xml file to a queue on a local computer.</span></span>  
  
2.  <span data-ttu-id="1f3a7-107">BizTalk Server recibe el archivo .xml de gran tamaño de la cola y lo copia en un directorio local.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-107">BizTalk Server receives the large .xml file from the queue and copies it to a local directory.</span></span>  
  
 <span data-ttu-id="1f3a7-108">Muchas de las operaciones de Message Queue Server son asíncronas.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-108">Many operations in Message Queuing are asynchronous.</span></span> <span data-ttu-id="1f3a7-109">Es decir, muchas llamadas de API MSMQ (por ejemplo, **MQSendLargeMessage**) devuelto al llamador antes de que la operación solicitada se haya completado.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-109">That is, many MSMQ API calls (for example, **MQSendLargeMessage**) return to the caller before the requested operation has fully completed.</span></span>  
  
 <span data-ttu-id="1f3a7-110">MSMQ proporciona un mecanismo de envío de comentarios a la aplicación una vez completada la operación.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-110">MSMQ provides a mechanism to deliver feedback to the application after the operation has completed.</span></span> <span data-ttu-id="1f3a7-111">Este mecanismo implica el uso de una cola de administración.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-111">This mechanism involves the use of an "Admin Queue."</span></span> <span data-ttu-id="1f3a7-112">MSMQ devuelve los comentarios en forma de mensaje en la cola de administración.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-112">MSMQ returns feedback in the form of a message in the Admin Queue.</span></span> <span data-ttu-id="1f3a7-113">La cola de administración a la que MSMQ devolverá los comentarios se especifica cuando se efectúe la llamada original de la API MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-113">The Admin Queue to which MSMQ will return feedback is specified when the original MSMQ API call is made.</span></span> <span data-ttu-id="1f3a7-114">Así, por ejemplo, cuando envía un mensaje mediante la **MQSendLargeMessage** API, la aplicación puede especificar el nombre de una cola de administración mediante la **PROPID_M_ADMIN_QUEUE** message (propiedad) en el mensaje pasa en la llamada a **MQSendLargeMessage**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-114">So, for example, when sending a message using the **MQSendLargeMessage** API, the application can specify the name of an Admin Queue by using the **PROPID_M_ADMIN_QUEUE** message property on the message passed in the call to **MQSendLargeMessage**.</span></span> <span data-ttu-id="1f3a7-115">Aunque la aplicación puede obtener un código devuelto correctamente el **MQSendLargeMessage** llamada, si el mensaje de operación de envío posteriormente se produce un error, MSMQ escribirá un mensaje a tal efecto en la cola de administración especificada.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-115">Even though the application may get a successful return code on the **MQSendLargeMessage** call, if the message send operation subsequently fails, MSMQ writes a message to that effect to the specified Admin Queue.</span></span>  
  
 <span data-ttu-id="1f3a7-116">Si la aplicación no especifica ninguna cola de administración, un error de envío tendrá como consecuencia la pérdida del mensaje y la ausencia de captura del diagnóstico (el mensaje desaparece sin dejar rastro).</span><span class="sxs-lookup"><span data-stu-id="1f3a7-116">If the application does not specify an Admin Queue, a send failure results in the message being lost and no diagnostics captured — in effect, the message disappears without any evidence.</span></span> <span data-ttu-id="1f3a7-117">Un número de situaciones de error en MSMQ puede hacer que esto ocurra, por ejemplo, realizar un envío no transaccional a una cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-117">A number of error situations in MSMQ can cause this to happen, for example, doing a non-transactional send to a transactional queue.</span></span>  
  
 <span data-ttu-id="1f3a7-118">En el contexto de este ejemplo, es importante que el código especifique un tipo de transacción en la llamada a **MQSendLargeMessage** que es coherente con la compatibilidad de transacción especificada para la cola a la que se envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-118">In the context of this sample, it is important that the code specify a transaction type in the call to **MQSendLargeMessage** that is consistent with the transaction support specified for the queue to which the message is sent.</span></span> <span data-ttu-id="1f3a7-119">Si esto último no se lleva a cabo y no se especifica ninguna cola de administración (como en el caso de este ejemplo), MSMQ descarta el mensaje enviado sin dar ninguna indicación de ello (es decir, sin que se devuelva código de error alguno a la aplicación, sin que se escriba ningún diagnóstico en el registro de eventos, etc.).</span><span class="sxs-lookup"><span data-stu-id="1f3a7-119">If this is not done and if no Admin Queue is specified (as is the case in this sample), then MSMQ discards the sent message with no indication that it has done so (that is, no error code returned to the application, no diagnostics written to the event log, and so on).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1f3a7-120">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f3a7-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="1f3a7-121">\<Ejemplos de ruta de acceso\>\AdaptersUsage\MSMQLarge</span><span class="sxs-lookup"><span data-stu-id="1f3a7-121">\<Samples Path\>\AdaptersUsage\MSMQLarge</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f3a7-122">Si usa una versión de 64 bits de Windows y el servidor BizTalk Server, el ejemplo se instalará en el **C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\SDK\Samples\AdaptersUsage\MSMQLarge** carpeta.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-122">If using a 64-bit version of Windows and BizTalk Server, the sample will be installed in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge** folder.</span></span>  <span data-ttu-id="1f3a7-123">Tenga en cuenta este cambio para el resto de instrucciones de este documento mediante el **C:\Program Files** carpeta.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-123">Note this change for any other instructions in this document using the **C:\Program Files** folder.</span></span>  
  
 <span data-ttu-id="1f3a7-124">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-124">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="1f3a7-125">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="1f3a7-125">**File**</span></span>|<span data-ttu-id="1f3a7-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="1f3a7-126">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="1f3a7-127">**MQRTLarge.dll**</span><span class="sxs-lookup"><span data-stu-id="1f3a7-127">**MQRTLarge.dll**</span></span>|<span data-ttu-id="1f3a7-128">Proporciona un complemento para la versión nativa de Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-128">Provides an add-on for native message queuing.</span></span> <span data-ttu-id="1f3a7-129">Expone el **MQSendLargeMessage** y **MQReceiveLargeMessage** API.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-129">Exposes the **MQSendLargeMessage** and **MQReceiveLargeMessage** APIs.</span></span><br /><br /> <span data-ttu-id="1f3a7-130">Debe instalar a BizTalk Server en una versión de 64 bits de Windows para tener acceso a la versión de 64 bits de MQRTLarge.dll.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-130">You must install BizTalk Server on a 64-bit version of Windows in order to access the 64-bit version of MQRTLarge.dll.</span></span><br /><br /> <span data-ttu-id="1f3a7-131">Para una solución MSMQ sin BizTalk Server, la posible que MQRTLarge.dll funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-131">For an MSMQ solution without BizTalk Server, the MQRTLarge.dll may still function correctly.</span></span> <span data-ttu-id="1f3a7-132">Sin embargo, esto no es una configuración recomendada que admita Microsoft, y pueden producirse resultados inesperados si se usa fuera del entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-132">However, this is not a recommended configuration that Microsoft supports, and unexpected results may occur if used outside of the BizTalk Server environment.</span></span>|  
|||  
|<span data-ttu-id="1f3a7-133">**LargeMessages.sln**</span><span class="sxs-lookup"><span data-stu-id="1f3a7-133">**LargeMessages.sln**</span></span>|<span data-ttu-id="1f3a7-134">Proporciona una solución de Visual Studio para crear el ejecutable SendLargeMessage que se utiliza en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-134">Provides a Visual Studio solution to create the SendLargeMessage executable used in the sample.</span></span>|  
|<span data-ttu-id="1f3a7-135">**XMLCreator.sln**</span><span class="sxs-lookup"><span data-stu-id="1f3a7-135">**XMLCreator.sln**</span></span>|<span data-ttu-id="1f3a7-136">Proporciona una solución de Visual Studio para crear el ejecutable XMLCreator a fin de generar un archivo .xml de prueba para el ejemplo de SDK.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-136">Provides a Visual Studio solution to create the XMLCreator executable to generate a test .xml file for the SDK sample.</span></span>|  
  
## <a name="configure-biztalk-and-create-the-msmq-queue"></a><span data-ttu-id="1f3a7-137">Configuración de BizTalk y crear la cola MSMQ</span><span class="sxs-lookup"><span data-stu-id="1f3a7-137">Configure BizTalk and Create the MSMQ Queue</span></span>  
 <span data-ttu-id="1f3a7-138">Asegúrese de que Visual Studio, Microsoft Message Queue Server y BizTalk Server instalan.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-138">Ensure that Visual Studio, Microsoft Message Queuing, and BizTalk Server installed.</span></span>  
  
#### <a name="to-configure-biztalk-server"></a><span data-ttu-id="1f3a7-139">Para configurar BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1f3a7-139">To configure BizTalk Server</span></span>  
  
1.  <span data-ttu-id="1f3a7-140">En Visual Studio, abra el **C:\Program Files\Microsoft BizTalk Server \<versión\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln** archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-140">In Visual Studio, open the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln** solution file.</span></span>  <span data-ttu-id="1f3a7-141">Cree el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-141">Build the sample.</span></span>  
  
2.  <span data-ttu-id="1f3a7-142">Crear un **C:\Demo** directorio en el servidor BizTalk Server colocará los mensajes de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-142">Create a **C:\Demo** directory where BizTalk Server will place the messages from MSMQ.</span></span>  
  
3.  <span data-ttu-id="1f3a7-143">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-143">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="1f3a7-144">Cree un puerto de envío para el ejemplo para escribir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-144">Create a send port for the sample to write the message.</span></span>  
  
    -   <span data-ttu-id="1f3a7-145">Expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**, haga clic en **puertos de envío**, haga clic en **Nuevo**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-145">Expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, right-click **Send Ports**, click **New**, and then click **Static One-Way Send Port**.</span></span>  
  
5.  <span data-ttu-id="1f3a7-146">En el **propiedades de puerto de envío de unidireccional estático** diálogo cuadro, establezca el nombre del puerto **MySendPort**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-146">In the **Static One-Way Send Port Properties** dialog box, set the name of the port to **MySendPort**.</span></span>  
  
6.  <span data-ttu-id="1f3a7-147">Establece el tipo de transporte en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-147">Set the transport type to **File**.</span></span>  
  
7.  <span data-ttu-id="1f3a7-148">Haga clic en el **configurar** para abrir el **propiedades de transporte de archivo** formulario.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-148">Click the **Configure** button to open the **File Transport Properties** form.</span></span> <span data-ttu-id="1f3a7-149">Escriba **C:\Demo** en **carpeta de destino**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-149">Enter **C:\Demo** in **Destination Folder**.</span></span> <span data-ttu-id="1f3a7-150">Asegúrese de que la identidad de la instancia de host tiene acceso a la carpeta C:\Demo.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-150">Ensure that the host instance identity has access to the C:\Demo folder.</span></span>  
  
8.  <span data-ttu-id="1f3a7-151">Asegúrese de que **nombre de archivo** está establecido en **%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-151">Ensure that **File Name** is set to **%MessageID%.xml**.</span></span> <span data-ttu-id="1f3a7-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1f3a7-153">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-153">Click **Filters**.</span></span>  
  
    1.  <span data-ttu-id="1f3a7-154">Establecer **propiedad** a **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-154">Set **Property** to **BTS.ReceivePortName**.</span></span>  
  
    2.  <span data-ttu-id="1f3a7-155">Establecer **operador** a  **=** .</span><span class="sxs-lookup"><span data-stu-id="1f3a7-155">Set **Operator** to **=**.</span></span>  
  
    3.  <span data-ttu-id="1f3a7-156">Establecer **valor** a **MyReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-156">Set **Value** to **MyReceivePort**.</span></span>  
  
    4.  <span data-ttu-id="1f3a7-157">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-157">Click **OK**.</span></span>  
  
10. <span data-ttu-id="1f3a7-158">Cree un puerto de recepción para aceptar el mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-158">Create a receive port to accept the message from MSMQ.</span></span>  
  
    1.  <span data-ttu-id="1f3a7-159">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-159">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Receive Ports**.</span></span>  
  
    2.  <span data-ttu-id="1f3a7-160">Haga clic en **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-160">Click **New**, and then click **One-way Receive Port**.</span></span>  
  
11. <span data-ttu-id="1f3a7-161">En el **propiedades de puerto de recepción** diálogo cuadro, establezca el nombre del puerto **MyReceivePort**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-161">In the **Receive Port Properties** dialog box, set the name of the port to **MyReceivePort**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="1f3a7-162">Tras crear un puerto de recepción para el ejemplo, es preciso crear una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-162">After creating a receive port for the sample, you must create a receive location.</span></span>  
  
    1.  <span data-ttu-id="1f3a7-163">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-163">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Receive Locations**.</span></span>  
  
    2.  <span data-ttu-id="1f3a7-164">Haga clic en **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-164">Click **New**, and then click **One-way Receive Location**.</span></span>  
  
    3.  <span data-ttu-id="1f3a7-165">Establecer el nombre de la ubicación de recepción **MSMQReceiveLocation**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-165">Set the name of the receive location to **MSMQReceiveLocation**.</span></span>  
  
    4.  <span data-ttu-id="1f3a7-166">En el **seleccionar un puerto de recepción** cuadro de diálogo, seleccione **MyReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-166">In the **Select a Receive Port** dialog box, select **MyReceivePort**.</span></span>  
  
    5.  <span data-ttu-id="1f3a7-167">En el **propiedades de la ubicación de recepción** cuadro de diálogo, establezca **tipo de transporte** a **MSMQ**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-167">In the **Receive Location Properties** dialog box, set **Transport Type** to **MSMQ**.</span></span>  
  
    6.  <span data-ttu-id="1f3a7-168">En el **dirección (URI)** sección, haga clic en **configurar** para abrir el **propiedades de transporte de MSMQ** formulario.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-168">In the **Address (URI)** section, click **Configure** to open the **MSMQ Transport Properties** form.</span></span> <span data-ttu-id="1f3a7-169">Establecer **cola** a **localhost\private$ \test**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-169">Set **Queue** to **localhost\private$\test**.</span></span>  
  
    7.  <span data-ttu-id="1f3a7-170">Establecer **transaccional** a `True`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-170">Set **Transactional** to `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="1f3a7-171">Es necesario hacer que los puertos y las ubicaciones de recepción se encuentren disponibles para su uso a través de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f3a7-171">You must make the ports and receive locations available for use through the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
    1.  <span data-ttu-id="1f3a7-172">Haga clic en **MySendPort**y, a continuación, haga clic en **dar de alta**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-172">Right-click **MySendPort**, and then click **Enlist**.</span></span>  
  
    2.  <span data-ttu-id="1f3a7-173">Haga clic en **MySendPort**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-173">Right-click **MySendPort**, and then click **Start**.</span></span>  
  
    3.  <span data-ttu-id="1f3a7-174">Haga clic en **MSMQReceiveLocation**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-174">Right-click **MSMQReceiveLocation**, and then click **Enable**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows-server"></a><span data-ttu-id="1f3a7-175">Para crear la cola MSMQ en Windows Server</span><span class="sxs-lookup"><span data-stu-id="1f3a7-175">To create the MSMQ queue in Windows Server</span></span>
  
1.  <span data-ttu-id="1f3a7-176">Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-176">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="1f3a7-177">Expanda el **características** nodo.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-177">Expand the **Features** node.</span></span>  
  
3.  <span data-ttu-id="1f3a7-178">Expanda el **Message Queue Server** nodo.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-178">Expand the **Message Queuing** node.</span></span>  
  
4.  <span data-ttu-id="1f3a7-179">Haga clic en el **colas privadas** nodo, haga clic en **New**y, a continuación, haga clic en **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-179">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
5.  <span data-ttu-id="1f3a7-180">En **nombre de la cola**, escriba **probar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-180">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="1f3a7-181">Asegúrese de que el **transaccional** casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-181">Ensure that the **Transactional** check box is selected.</span></span>  
  
6.  <span data-ttu-id="1f3a7-182">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-182">Click **OK**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows"></a><span data-ttu-id="1f3a7-183">Para crear la cola MSMQ en Windows</span><span class="sxs-lookup"><span data-stu-id="1f3a7-183">To create the MSMQ queue in Windows</span></span> 
  
1.  <span data-ttu-id="1f3a7-184">Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-184">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="1f3a7-185">Expanda **servicios y aplicaciones**y, a continuación, expanda el **Message Queue Server** nodo.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-185">Expand **Services and Applications**, and then expand the **Message Queuing** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f3a7-186">Si **Message Queue Server** no está instalado en el equipo, vaya a **el Panel de Control > Programas > programas y características**y, a continuación, seleccione **o desactivar las características de Windows Active**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-186">If **Message Queuing** is not installed in the computer, go to **Control Panel > Programs > Programs and Features**, and then select **Turn Windows features on or off**.</span></span> <span data-ttu-id="1f3a7-187">Compruebe todas las características de **Microsoft Message Queue (MSMQ) Server**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-187">Check all the features under **Microsoft Message Queue (MSMQ) Server**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f3a7-188">Haga clic en el **colas privadas** nodo, haga clic en **New**y, a continuación, haga clic en **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-188">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
4.  <span data-ttu-id="1f3a7-189">En **nombre de la cola**, escriba **probar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-189">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="1f3a7-190">Asegúrese de que el **transaccional** casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-190">Ensure that the **Transactional** check box is selected.</span></span>  
  
5.  <span data-ttu-id="1f3a7-191">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-191">Click **OK**.</span></span>  
  
## <a name="creating-a-test-file-and-running-the-sample"></a><span data-ttu-id="1f3a7-192">Creación de un archivo de prueba y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f3a7-192">Creating a Test File and Running the Sample</span></span>  
  
#### <a name="to-create-a-large-test-file"></a><span data-ttu-id="1f3a7-193">Para crear un archivo de prueba de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="1f3a7-193">To create a large test file</span></span>  
  
1.  <span data-ttu-id="1f3a7-194">En Visual Studio, abra la solución **C:\Program Files\Microsoft BizTalk Server \<versión\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-194">In Visual Studio, open the solution **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**.</span></span>  
  
2.  <span data-ttu-id="1f3a7-195">Cree y ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-195">Build and run the project.</span></span>  
  
3.  <span data-ttu-id="1f3a7-196">En **cuerpo XML**, tipo **se trata de un mensaje de prueba**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-196">Under **XML Body**, type **This is a test message**.</span></span>  
  
4.  <span data-ttu-id="1f3a7-197">En **número de veces para copiar el cuerpo XML**, tipo `250000`.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-197">Under **# of times to copy XML body**, type `250000`.</span></span>  
  
5.  <span data-ttu-id="1f3a7-198">En **ubicación del archivo XML**, tipo `C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-198">Under **XML File Location**, type `C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`.</span></span>  
  
6.  <span data-ttu-id="1f3a7-199">Haga clic en **crear XML**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-199">Click **Create XML**, and then click **OK**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="1f3a7-200">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f3a7-200">To run the sample</span></span>  
  
1.  <span data-ttu-id="1f3a7-201">Abra un símbolo del sistema y cambie al directorio **C:\Program Files\Microsoft BizTalk Server \<versión\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-201">Open a command prompt and change directory to **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**.</span></span>  
  
2.  <span data-ttu-id="1f3a7-202">En el símbolo del sistema, ejecute **SendLargeMessage.exe**.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-202">At the command prompt, run **SendLargeMessage.exe**.</span></span> <span data-ttu-id="1f3a7-203">El ejecutable SendLargeMessage acepta dos variables: la primera es la ubicación de la cola MSMQ y la segunda es la ubicación del archivo .xml que se va a enviar:</span><span class="sxs-lookup"><span data-stu-id="1f3a7-203">The SendLargeMessage executable accepts two variables — the first is the location of the MSMQ queue, and the second is the location of the .xml file to send:</span></span>  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  <span data-ttu-id="1f3a7-204">Compruebe que se creó un archivo del mismo tamaño en el equipo de servidor BizTalk Server en el **C:\Demo** directory.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-204">Verify that a file of the same size was created on the BizTalk Server computer in the **C:\Demo** directory.</span></span> <span data-ttu-id="1f3a7-205">Éste es el directorio identificado en el puerto de envío MySendPort.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-205">This is the directory you identified in the MySendPort send port.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="1f3a7-206">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f3a7-206">Comments</span></span>  
 <span data-ttu-id="1f3a7-207">SendLargeMessage.exe hace referencia a la **LargeMessages** API, que a su vez hace referencia a la BizTalk extensión Message Queue Server grandes mensaje (MQRTLarge.dll) API.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-207">SendLargeMessage.exe references the **LargeMessages** API, which in turn references the BizTalk Message Queuing Large Message Extension (MQRTLarge.dll) API.</span></span> <span data-ttu-id="1f3a7-208">La API de extensión de mensajes de gran tamaño de Message Queue Server es un complemento para la versión nativa de Message Queue Server con el que se habilita el procesamiento de mensajes con un tamaño superior al límite de 4 MB de la versión nativa de Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-208">The Message Queuing Large Message Extension API is an add-on for native message queuing that enables the processing of messages larger than the 4 MB limit of native message queuing.</span></span>  
  
 <span data-ttu-id="1f3a7-209">Este ejemplo se utiliza la **MQSendLargeMessage** API y expone la API de .NET Framework mediante el uso de la **LargeMessages** API.</span><span class="sxs-lookup"><span data-stu-id="1f3a7-209">This sample uses the **MQSendLargeMessage** API and exposes the API to the .NET Framework by using the **LargeMessages** API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f3a7-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f3a7-210">See Also</span></span>  
 <span data-ttu-id="1f3a7-211">[Extensión de mensajes de BizTalk para Message Queue grandes](../core/biztalk-message-queuing-large-message-extension.md) </span><span class="sxs-lookup"><span data-stu-id="1f3a7-211">[BizTalk Message Queuing Large Message Extension](../core/biztalk-message-queuing-large-message-extension.md) </span></span>  
 [<span data-ttu-id="1f3a7-212">Ejemplos de adaptadores: uso</span><span class="sxs-lookup"><span data-stu-id="1f3a7-212">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)