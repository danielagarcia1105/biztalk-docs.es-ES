---
title: 'Paso 8: Ver los mensajes en las bases de datos BTARN | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- loopback tutorial, viewing messages
- databases, viewing messages
ms.assetid: c549670c-4428-483c-906c-eff163ddef9a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56563473e5865e9b94edefd76e9f230f8cd37f67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998451"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a><span data-ttu-id="19e7e-102">Paso 8: Ver los mensajes en las bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="19e7e-102">Step 8: View Messages in the BTARN Databases</span></span>
<span data-ttu-id="19e7e-103">En este paso, utilice SQL Query Analyzer para ver los mensajes de la línea de negocio (LOB) almacenados en el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] base de datos para comprobar que su escenario de bucle invertido funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="19e7e-103">In this step, you use SQL Query Analyzer to view line-of-business (LOB) messages stored in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] database to verify that your loop-back scenario is working correctly.</span></span>  
  
 <span data-ttu-id="19e7e-104">Después de la aplicación LOB utilidad genera un mensaje LOB y lo envía a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], ocurre lo siguiente para el iniciador (inicio) y el Respondedor (asociado):</span><span class="sxs-lookup"><span data-stu-id="19e7e-104">After the LOB Application utility generates an LOB message and submits it to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the following events occur for the initiator (home) and the responder (partner):</span></span>  
  
 <span data-ttu-id="19e7e-105">Flujo de trabajo de iniciador</span><span class="sxs-lookup"><span data-stu-id="19e7e-105">Initiator Workflow</span></span>  
  
- <span data-ttu-id="19e7e-106">SubmitRNIF envía el mensaje LOB a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="19e7e-106">SubmitRNIF submits the LOB message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
- <span data-ttu-id="19e7e-107">El adaptador de SQL de recepción ubicación recoge el mensaje y lo entrega a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="19e7e-107">The SQL adapter receive location picks up the message and delivers it to the MessageBox database.</span></span> <span data-ttu-id="19e7e-108">El adaptador de SQL recoge un mensaje en un tiempo de ejecución el `GetMessagesFromLOB` procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="19e7e-108">The SQL adapter picks up one message at a time running the `GetMessagesFromLOB` stored procedure.</span></span>  
  
- <span data-ttu-id="19e7e-109">El iniciador privado toma el mensaje de la base de datos de cuadro de mensajes y lo coloca nuevamente a la base de datos de cuadro de mensajes con propiedades de contexto promocionadas adicionales.</span><span class="sxs-lookup"><span data-stu-id="19e7e-109">The private initiator picks the message from the MessageBox database and then drops it again to the MessageBox database with additional promoted context properties.</span></span>  
  
- <span data-ttu-id="19e7e-110">El iniciador público toma el mensaje de la base de datos de cuadro de mensajes en función del filtro de suscripción.</span><span class="sxs-lookup"><span data-stu-id="19e7e-110">The public initiator picks the message from the MessageBox database based on the subscription filter.</span></span>  
  
- <span data-ttu-id="19e7e-111">El HTTP del puerto de envío recoge el mensaje con la canalización RNIFSend basándose en las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="19e7e-111">The HTTP send port picks the message with the RNIFSend pipeline based on the subscriptions.</span></span> <span data-ttu-id="19e7e-112">Guarda el mensaje en la tabla MessageStorageOut de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] archivar la base de datos para el no rechazo y, a continuación, envía el mensaje a través de la página RNIFSend.aspx.</span><span class="sxs-lookup"><span data-stu-id="19e7e-112">It saves the message in the MessageStorageOut table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database for non-repudiation, and then sends the message over to the RNIFSend.aspx page.</span></span>  
  
- <span data-ttu-id="19e7e-113">La página RNIFSend.aspx recibe el mensaje codificado con MIME con variables de cadena de consulta que incluyen el destino final del mensaje (URL de organización de asociado).</span><span class="sxs-lookup"><span data-stu-id="19e7e-113">The RNIFSend.aspx page receives the MIME-encoded message with query string variables that include the final destination of the message (partner organization URL).</span></span>  
  
  <span data-ttu-id="19e7e-114">Flujo de trabajo de servicio de respuesta</span><span class="sxs-lookup"><span data-stu-id="19e7e-114">Responder Workflow</span></span>  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="19e7e-115"> envía el mensaje RNIF a la página de trabajo RNIFReceive.aspx donde se quita el contenedor de descodificación MIME.</span><span class="sxs-lookup"><span data-stu-id="19e7e-115"> sends the RNIF message to the RNIFReceive.aspx page where the MIME-decoded wrapper is removed.</span></span> <span data-ttu-id="19e7e-116">El mensaje se identifica como sincrónico o asincrónico y luego se reenvían a la sincrónica o asincrónica de recepción ubicación (RNIF_Sync_Receive o RNIF_Async_Receive).</span><span class="sxs-lookup"><span data-stu-id="19e7e-116">The message is identified as either synchronous or asynchronous, and then forwarded to either the synchronous or asynchronous receive location (RNIF_Sync_Receive or RNIF_Async_Receive).</span></span>  
  
- <span data-ttu-id="19e7e-117">La recepción HTTP de ubicación primero guarda el formato del mensaje en la tabla MessageStorageIn de rechazo de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archivar base de datos.</span><span class="sxs-lookup"><span data-stu-id="19e7e-117">The HTTP receive location first saves the wire format of the message in the MessageStorageIn table for non-repudiation of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database.</span></span> <span data-ttu-id="19e7e-118">Ubicación de recepción de HTTP, a continuación, se descodifica, descifra (para RNIF 2.0), valida en su firma, separa las partes del mensaje XML, autoriza en función de la firma y, a continuación, lo coloca en la base de datos de cuadro de mensajes con las propiedades promocionadas correctas</span><span class="sxs-lookup"><span data-stu-id="19e7e-118">The HTTP receive location then decodes, decrypts (for RNIF 2.0), validates on its signature, disassembles the XML message parts, authorizes based on the signature, and then drops it in the MessageBox database with the correct promoted properties</span></span>  
  
- <span data-ttu-id="19e7e-119">El servicio de respuesta pública toma las partes del mensaje en función de suscripción y, a continuación, se valida y procesa el mensaje según el estándar RNIF correcto.</span><span class="sxs-lookup"><span data-stu-id="19e7e-119">The public responder picks the message parts based on subscription, and then validates and processes the message based on the correct RNIF standard.</span></span> <span data-ttu-id="19e7e-120">El elemento de contenido de servicio coloca el mensaje en la base de datos de cuadro de mensajes con las propiedades de contexto correcta.</span><span class="sxs-lookup"><span data-stu-id="19e7e-120">The service content part drops the message into the MessageBox database with the correct context properties.</span></span>  
  
- <span data-ttu-id="19e7e-121">El código SQL puerto de envío recoge el mensaje en función del filtro de suscripción.</span><span class="sxs-lookup"><span data-stu-id="19e7e-121">The SQL send port picks the message based on the subscription filter.</span></span> <span data-ttu-id="19e7e-122">A continuación, guarda el mensaje en la tabla MessagesToLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="19e7e-122">It then saves the message in the MessagesToLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19e7e-123">En el lado de servicio de respuesta, el servicio de respuesta pública es responsable de generar la confirmación de recepción o de la señal de excepción al iniciador.</span><span class="sxs-lookup"><span data-stu-id="19e7e-123">On the responder side, the Public Responder is responsible for generating the acknowledgement receipt or the exception signal back to the initiator.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="19e7e-124"> no guarda el mensaje de señal en la tabla MessagesFromLOB.</span><span class="sxs-lookup"><span data-stu-id="19e7e-124"> does not save the signal message in the MessagesFromLOB table.</span></span> <span data-ttu-id="19e7e-125">Esto es porque la aplicación de LOB no genera el mensaje de señal.</span><span class="sxs-lookup"><span data-stu-id="19e7e-125">This is because the LOB application does not generate the signal message.</span></span> <span data-ttu-id="19e7e-126">El mensaje de acción continuará hasta el Respondedor privado, y [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] lo guarda en la tabla MessagesToLOB.</span><span class="sxs-lookup"><span data-stu-id="19e7e-126">The Action message will continue through the Private Responder, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves it to the MessagesToLOB table.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="19e7e-127">Para PIP de doble acción, la línea de negocio en el lado de servicio de respuesta es responsable de generar un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="19e7e-127">For double-action PIPs, the LOB on the responder side is responsible for generating a response message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="19e7e-128"> lo coloca en la tabla MessagesFromLOB pasen por el mismo proceso que el proceso del lado del iniciador.</span><span class="sxs-lookup"><span data-stu-id="19e7e-128"> drops it to the MessagesFromLOB table to go through the same process as the initiator-side process.</span></span> <span data-ttu-id="19e7e-129">En este caso, el proceso público del iniciador en el lado del iniciador volver envía una señal de confirmación de recepción o de excepción para el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="19e7e-129">In this case, the Public Initiator Process on the initiator side sends back an acknowledgement receipt or exception signal for the response message.</span></span>  
  
### <a name="to-view-messages-in-the-btarn-databases"></a><span data-ttu-id="19e7e-130">Para ver los mensajes en las bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="19e7e-130">To view messages in the BTARN databases</span></span>  
  
1. <span data-ttu-id="19e7e-131">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft SQL Server \<versión\>** y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="19e7e-131">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server \<version\>**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="19e7e-132">En conectar al cuadro de diálogo de servidor, haga clic en **Connect**.</span><span class="sxs-lookup"><span data-stu-id="19e7e-132">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="19e7e-133">En el panel Explorador de objetos, compruebe que se ha iniciado el Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="19e7e-133">In the Object Explorer pane, verify that the SQL Server Agent is started.</span></span> <span data-ttu-id="19e7e-134">Si no, haga clic en **del Agente SQL Server**y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="19e7e-134">If not, right-click **SQL Server Agent**, and click **Start**.</span></span>  
  
3. <span data-ttu-id="19e7e-135">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="19e7e-135">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4. <span data-ttu-id="19e7e-136">En la ventana de consulta en blanco, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="19e7e-136">In the Blank Query window, type the following:</span></span>  
  
   ```  
   use BTARNArchive  
   SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
   SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
   use BTARNData  
   SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
   ```  
  
5. <span data-ttu-id="19e7e-137">En Microsoft SQL Server Management Studio, haga clic en **Execute**.</span><span class="sxs-lookup"><span data-stu-id="19e7e-137">In the Microsoft SQL Server Management Studio, click **Execute**.</span></span>  
  
   <span data-ttu-id="19e7e-138">Verá un mensaje de acción en la tabla MessagesFromLOB y, si ejecuta la consulta a intentarlo en unos minutos (tiempo puede variar según la configuración del sistema), verá dos mensajes generados en la tabla MessagesToLOB con valores de MessageCategory de AsyncAckSignal (25) y AsyncAction (10).</span><span class="sxs-lookup"><span data-stu-id="19e7e-138">You will see an action message in the MessagesFromLOB table, and if you run the query again in several minutes (time may vary depending on your system configuration), you will see two messages generated in the MessagesToLOB table with MessageCategory values of AsyncAckSignal (25) and AsyncAction (10).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e7e-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="19e7e-139">See Also</span></span>  
 <span data-ttu-id="19e7e-140">[Bucle invertido](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span><span class="sxs-lookup"><span data-stu-id="19e7e-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span></span>  
 [<span data-ttu-id="19e7e-141">Tutorial de bucles invertidos</span><span class="sxs-lookup"><span data-stu-id="19e7e-141">Loopback Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
