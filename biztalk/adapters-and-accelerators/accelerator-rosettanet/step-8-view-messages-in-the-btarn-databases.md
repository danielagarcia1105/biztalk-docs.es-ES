---
title: 'Paso 8: Ver los mensajes en las bases de datos BTARN | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, viewing
- loopback tutorial, viewing messages
- databases, viewing messages
ms.assetid: c549670c-4428-483c-906c-eff163ddef9a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2324cca59a9104d8f40b5b6b69eca76af1004384
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a><span data-ttu-id="fa286-102">Paso 8: Ver los mensajes en las bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="fa286-102">Step 8: View Messages in the BTARN Databases</span></span>
<span data-ttu-id="fa286-103">En este paso, utilice el analizador de consultas de SQL para ver los mensajes de línea de negocio (LOB) que se almacenan en la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] base de datos para comprobar que el escenario de bucle invertido funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa286-103">In this step, you use SQL Query Analyzer to view line-of-business (LOB) messages stored in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] database to verify that your loop-back scenario is working correctly.</span></span>  
  
 <span data-ttu-id="fa286-104">Después de la aplicación LOB utilidad genera un mensaje LOB y lo envía a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], ocurre lo siguiente para el iniciador (principal) y el Respondedor (asociado):</span><span class="sxs-lookup"><span data-stu-id="fa286-104">After the LOB Application utility generates an LOB message and submits it to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the following events occur for the initiator (home) and the responder (partner):</span></span>  
  
 <span data-ttu-id="fa286-105">Flujo de trabajo de iniciador</span><span class="sxs-lookup"><span data-stu-id="fa286-105">Initiator Workflow</span></span>  
  
-   <span data-ttu-id="fa286-106">SubmitRNIF envía el mensaje LOB a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="fa286-106">SubmitRNIF submits the LOB message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
-   <span data-ttu-id="fa286-107">El adaptador de SQL de recepción ubicación recoge el mensaje y lo entrega a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fa286-107">The SQL adapter receive location picks up the message and delivers it to the MessageBox database.</span></span> <span data-ttu-id="fa286-108">El adaptador de SQL recoge un mensaje en un tiempo de ejecución el `GetMessagesFromLOB` procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="fa286-108">The SQL adapter picks up one message at a time running the `GetMessagesFromLOB` stored procedure.</span></span>  
  
-   <span data-ttu-id="fa286-109">El iniciador privado toma el mensaje de la base de datos de cuadro de mensajes y, a continuación, colocarla de nuevo a la base de datos de cuadro de mensajes con propiedades de contexto promocionadas adicional.</span><span class="sxs-lookup"><span data-stu-id="fa286-109">The private initiator picks the message from the MessageBox database and then drops it again to the MessageBox database with additional promoted context properties.</span></span>  
  
-   <span data-ttu-id="fa286-110">El iniciador público toma el mensaje de la base de datos de cuadro de mensajes basándose en el filtro de suscripción.</span><span class="sxs-lookup"><span data-stu-id="fa286-110">The public initiator picks the message from the MessageBox database based on the subscription filter.</span></span>  
  
-   <span data-ttu-id="fa286-111">HTTP puerto de envío recoge el mensaje con la canalización de RNIFSend según las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="fa286-111">The HTTP send port picks the message with the RNIFSend pipeline based on the subscriptions.</span></span> <span data-ttu-id="fa286-112">Guarda el mensaje en la tabla MessageStorageOut de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sin repudio, en la base de datos Archive y, a continuación, envía el mensaje a través a la página RNIFSend.aspx.</span><span class="sxs-lookup"><span data-stu-id="fa286-112">It saves the message in the MessageStorageOut table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database for non-repudiation, and then sends the message over to the RNIFSend.aspx page.</span></span>  
  
-   <span data-ttu-id="fa286-113">La página RNIFSend.aspx recibe el mensaje codificado con MIME con variables de cadena de consulta que incluyen el destino final del mensaje (URL de organización del socio comercial).</span><span class="sxs-lookup"><span data-stu-id="fa286-113">The RNIFSend.aspx page receives the MIME-encoded message with query string variables that include the final destination of the message (partner organization URL).</span></span>  
  
 <span data-ttu-id="fa286-114">Flujo de trabajo de servicio de respuesta</span><span class="sxs-lookup"><span data-stu-id="fa286-114">Responder Workflow</span></span>  
  
-   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="fa286-115">envía el mensaje RNIF a la página de trabajo RNIFReceive.aspx donde se quita el contenedor de descodificación MIME.</span><span class="sxs-lookup"><span data-stu-id="fa286-115"> sends the RNIF message to the RNIFReceive.aspx page where the MIME-decoded wrapper is removed.</span></span> <span data-ttu-id="fa286-116">El mensaje se identifica como sincrónico o asincrónico y, a continuación, se reenvían a ubicación (RNIF_Sync_Receive o RNIF_Async_Receive) de recepción del modo sincrónico o asincrónico.</span><span class="sxs-lookup"><span data-stu-id="fa286-116">The message is identified as either synchronous or asynchronous, and then forwarded to either the synchronous or asynchronous receive location (RNIF_Sync_Receive or RNIF_Async_Receive).</span></span>  
  
-   <span data-ttu-id="fa286-117">La recepción de HTTP ubicación primera guarda el formato del mensaje en la tabla MessageStorageIn para el no rechazo de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="fa286-117">The HTTP receive location first saves the wire format of the message in the MessageStorageIn table for non-repudiation of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database.</span></span> <span data-ttu-id="fa286-118">Ubicación de recepción de HTTP, a continuación, se descodifica, descifra (para RNIF 2.0), valida en su firma, desensambla las partes del mensaje XML, se autoriza en función de la firma y, a continuación, lo coloca en la base de datos de cuadro de mensajes con las propiedades promocionadas correctas</span><span class="sxs-lookup"><span data-stu-id="fa286-118">The HTTP receive location then decodes, decrypts (for RNIF 2.0), validates on its signature, disassembles the XML message parts, authorizes based on the signature, and then drops it in the MessageBox database with the correct promoted properties</span></span>  
  
-   <span data-ttu-id="fa286-119">El servicio de respuesta pública toma las partes del mensaje según la suscripción y, a continuación, se valida y procesa el mensaje según el estándar RNIF correcto.</span><span class="sxs-lookup"><span data-stu-id="fa286-119">The public responder picks the message parts based on subscription, and then validates and processes the message based on the correct RNIF standard.</span></span> <span data-ttu-id="fa286-120">El elemento de contenido de servicio coloca el mensaje en la base de datos de cuadro de mensajes con las propiedades de contexto correcto.</span><span class="sxs-lookup"><span data-stu-id="fa286-120">The service content part drops the message into the MessageBox database with the correct context properties.</span></span>  
  
-   <span data-ttu-id="fa286-121">La instrucción SQL puerto de envío recoge el mensaje basándose en el filtro de suscripción.</span><span class="sxs-lookup"><span data-stu-id="fa286-121">The SQL send port picks the message based on the subscription filter.</span></span> <span data-ttu-id="fa286-122">A continuación, guarda el mensaje en la tabla MessagesToLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="fa286-122">It then saves the message in the MessagesToLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa286-123">En el lado de servicio de respuesta, el servicio de respuesta pública es responsable de generar el acuse de recibo o la señal de excepción al iniciador.</span><span class="sxs-lookup"><span data-stu-id="fa286-123">On the responder side, the Public Responder is responsible for generating the acknowledgement receipt or the exception signal back to the initiator.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="fa286-124">no guarda el mensaje de señal en la tabla MessagesFromLOB.</span><span class="sxs-lookup"><span data-stu-id="fa286-124"> does not save the signal message in the MessagesFromLOB table.</span></span> <span data-ttu-id="fa286-125">Esto es porque la aplicación de LOB no genera el mensaje de señal.</span><span class="sxs-lookup"><span data-stu-id="fa286-125">This is because the LOB application does not generate the signal message.</span></span> <span data-ttu-id="fa286-126">El mensaje de acción proseguirá con el servicio de respuesta privado, y [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] lo guarda en la tabla MessagesToLOB.</span><span class="sxs-lookup"><span data-stu-id="fa286-126">The Action message will continue through the Private Responder, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves it to the MessagesToLOB table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa286-127">PIP de doble acción, el LOB en el lado de servicio de respuesta es responsable para generar un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fa286-127">For double-action PIPs, the LOB on the responder side is responsible for generating a response message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="fa286-128">coloca en la tabla MessagesFromLOB pasen por el mismo proceso que el proceso de iniciador.</span><span class="sxs-lookup"><span data-stu-id="fa286-128"> drops it to the MessagesFromLOB table to go through the same process as the initiator-side process.</span></span> <span data-ttu-id="fa286-129">En este caso, el proceso de iniciador público en el lado del iniciador nuevo envía una señal de confirmación de recepción o de una excepción para el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fa286-129">In this case, the Public Initiator Process on the initiator side sends back an acknowledgement receipt or exception signal for the response message.</span></span>  
  
### <a name="to-view-messages-in-the-btarn-databases"></a><span data-ttu-id="fa286-130">Para ver los mensajes en las bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="fa286-130">To view messages in the BTARN databases</span></span>  
  
1.  <span data-ttu-id="fa286-131">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="fa286-131">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="fa286-132">En conectar al servidor, cuadro de diálogo, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="fa286-132">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fa286-133">En el panel Explorador de objetos, compruebe que se ha iniciado el Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fa286-133">In the Object Explorer pane, verify that the SQL Server Agent is started.</span></span> <span data-ttu-id="fa286-134">Si no es así, haga clic en **Agente SQL Server**y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fa286-134">If not, right-click **SQL Server Agent**, and click **Start**.</span></span>  
  
3.  <span data-ttu-id="fa286-135">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="fa286-135">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="fa286-136">En la ventana de consulta en blanco, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa286-136">In the Blank Query window, type the following:</span></span>  
  
    ```  
    use BTARNArchive  
    SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
    SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
    use BTARNData  
    SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
    SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
    SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
    ```  
  
5.  <span data-ttu-id="fa286-137">En Microsoft SQL Server Management Studio, haga clic en **Execute**.</span><span class="sxs-lookup"><span data-stu-id="fa286-137">In the Microsoft SQL Server Management Studio, click **Execute**.</span></span>  
  
 <span data-ttu-id="fa286-138">Verá un mensaje de acción en la tabla MessagesFromLOB y, si ejecuta la consulta de nuevo al cabo de unos minutos (tiempo puede variar según la configuración del sistema), verá dos mensajes generados en la tabla MessagesToLOB con valores de MessageCategory de AsyncAckSignal (25) y AsyncAction (10).</span><span class="sxs-lookup"><span data-stu-id="fa286-138">You will see an action message in the MessagesFromLOB table, and if you run the query again in several minutes (time may vary depending on your system configuration), you will see two messages generated in the MessagesToLOB table with MessageCategory values of AsyncAckSignal (25) and AsyncAction (10).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa286-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa286-139">See Also</span></span>  
 <span data-ttu-id="fa286-140">[Bucle invertido](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span><span class="sxs-lookup"><span data-stu-id="fa286-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span></span>  
 [<span data-ttu-id="fa286-141">Tutorial de bucle invertido</span><span class="sxs-lookup"><span data-stu-id="fa286-141">Loopback Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)