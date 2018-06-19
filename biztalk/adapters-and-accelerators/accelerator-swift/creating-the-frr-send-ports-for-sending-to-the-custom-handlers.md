---
title: Creación de los puertos de envío FRR para enviar a los controladores personalizados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6326ae6e82e819d3cdf76ecc4d81e2a377ea65
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966546"
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="1f57c-102">Creación de los puertos de envío FRR para enviar a los controladores personalizados</span><span class="sxs-lookup"><span data-stu-id="1f57c-102">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>
<span data-ttu-id="1f57c-103">Para realizar la conciliación de respuesta de FIN, debe crear una serie de puertos de envío, cada uno de los cuales envía un mensaje (original mensaje o respuesta) de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a los controladores personalizados que procesan los mensajes correlacionados.</span><span class="sxs-lookup"><span data-stu-id="1f57c-103">To perform FIN Response Reconciliation, you need to create a series of send ports, each of which sends a message (original message or response) from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the custom handlers that process the correlated messages.</span></span>  
  
 <span data-ttu-id="1f57c-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="1f57c-104">**Summary**</span></span>  
  
 <span data-ttu-id="1f57c-105">Crear una serie de puertos de envío con las siguientes propiedades y los componentes, cada uno de ellos que se distinguen por el valor de BTS. Operación en el filtro:</span><span class="sxs-lookup"><span data-stu-id="1f57c-105">Create a series of send ports with the following properties and components, each one distinguished by the value of BTS.Operation in the filter:</span></span>  
  
|<span data-ttu-id="1f57c-106">Propiedad/componente</span><span class="sxs-lookup"><span data-stu-id="1f57c-106">Property/Component</span></span>|<span data-ttu-id="1f57c-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="1f57c-107">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="1f57c-108">Puerto de envío</span><span class="sxs-lookup"><span data-stu-id="1f57c-108">Send port</span></span>|<span data-ttu-id="1f57c-109">Puerto unidireccional estático</span><span class="sxs-lookup"><span data-stu-id="1f57c-109">Static one-way port</span></span>|  
|<span data-ttu-id="1f57c-110">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="1f57c-110">Transport type</span></span>|<span data-ttu-id="1f57c-111">FILE</span><span class="sxs-lookup"><span data-stu-id="1f57c-111">FILE</span></span>|  
|<span data-ttu-id="1f57c-112">Carpeta de destino (URI de dirección)</span><span class="sxs-lookup"><span data-stu-id="1f57c-112">Destination folder (Address URI)</span></span>|<span data-ttu-id="1f57c-113">La carpeta que desea enviar el mensaje</span><span class="sxs-lookup"><span data-stu-id="1f57c-113">The folder that you want to send the message to</span></span>|  
|<span data-ttu-id="1f57c-114">Nombre de archivo (dirección URI)</span><span class="sxs-lookup"><span data-stu-id="1f57c-114">File name (Address URI)</span></span>|<span data-ttu-id="1f57c-115">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="1f57c-115">%MessageID%.txt</span></span>|  
|<span data-ttu-id="1f57c-116">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="1f57c-116">Send pipeline</span></span>|[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="1f57c-117">. BizTalk.DefaultPipelines.</span><span class="sxs-lookup"><span data-stu-id="1f57c-117">.BizTalk.DefaultPipelines.</span></span> <span data-ttu-id="1f57c-118">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="1f57c-118">PassThruTransmit</span></span>|  
|<span data-ttu-id="1f57c-119">Filtros</span><span class="sxs-lookup"><span data-stu-id="1f57c-119">Filters</span></span>|<span data-ttu-id="1f57c-120">Como se muestra en las tablas siguientes</span><span class="sxs-lookup"><span data-stu-id="1f57c-120">As shown in the tables below</span></span>|  
  
 <span data-ttu-id="1f57c-121">Los puertos de envío para los mensajes se distinguen por el valor de BTS. Operación de filtro del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="1f57c-121">The send ports for the different messages are distinguished by the value of BTS.Operation in the send port's filter.</span></span>  
  
### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="1f57c-122">Para agregar puertos de envío FRR para enviar a los controladores personalizados</span><span class="sxs-lookup"><span data-stu-id="1f57c-122">To add FRR send ports for sending to the custom handlers</span></span>  
  
1.  <span data-ttu-id="1f57c-123">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto estático de una waySend**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-123">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  
  
2.  <span data-ttu-id="1f57c-124">En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba un nombre para el puerto de envío, por ejemplo, FRRCustomHandlersSendPort.</span><span class="sxs-lookup"><span data-stu-id="1f57c-124">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRCustomHandlersSendPort.</span></span>  
  
3.  <span data-ttu-id="1f57c-125">Para **tipo**, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-125">For **Type**, select **FILE**.</span></span>  
  
4.  <span data-ttu-id="1f57c-126">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-126">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="1f57c-127">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-127">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="1f57c-128">En el cuadro de diálogo Buscar carpeta, mover a la carpeta que desea enviar mensajes desde.</span><span class="sxs-lookup"><span data-stu-id="1f57c-128">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="1f57c-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-129">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f57c-130">Si esta carpeta no existe, puede crearlo mediante el **crear nueva carpeta** comando.</span><span class="sxs-lookup"><span data-stu-id="1f57c-130">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
7.  <span data-ttu-id="1f57c-131">En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-131">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f57c-132">Puede crear una carpeta diferente para cada tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1f57c-132">You can create a different folder for each type of message.</span></span>  
  
8.  <span data-ttu-id="1f57c-133">En el cuadro de diálogo Propiedades de puerto de envío para el controlador de envío, compruebe que **BizTalkServerApplication** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1f57c-133">In the Send Port Properties dialog box, for Send handler, verify that **BizTalkServerApplication** is selected.</span></span>  
  
9. <span data-ttu-id="1f57c-134">Para **canalización de envío**, seleccione **PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-134">For **Send Pipeline**, select **PassThruTransmit**.</span></span>  
  
10. <span data-ttu-id="1f57c-135">Haga clic en **filtros** en el panel izquierdo y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f57c-135">Click **Filters** in the left pane, and then do the following:</span></span>  
  
    |<span data-ttu-id="1f57c-136">Use</span><span class="sxs-lookup"><span data-stu-id="1f57c-136">Use this</span></span>|<span data-ttu-id="1f57c-137">Para</span><span class="sxs-lookup"><span data-stu-id="1f57c-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1f57c-138">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-138">**Property**</span></span>|<span data-ttu-id="1f57c-139">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-139">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="1f57c-140">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-140">**Operator**</span></span>|<span data-ttu-id="1f57c-141">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-141">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-142">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-142">**Value**</span></span>|<span data-ttu-id="1f57c-143">Tipo de **A4SWIFT_FrrService**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-143">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="1f57c-144">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1f57c-144">**Group**</span></span>|<span data-ttu-id="1f57c-145">**Y**</span><span class="sxs-lookup"><span data-stu-id="1f57c-145">**And**</span></span>|  
    |<span data-ttu-id="1f57c-146">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-146">**Property**</span></span>|<span data-ttu-id="1f57c-147">Seleccione **BTS. Operación**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-147">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="1f57c-148">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-148">**Operator**</span></span>|<span data-ttu-id="1f57c-149">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-149">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-150">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-150">**Value**</span></span>|<span data-ttu-id="1f57c-151">Escriba uno de los BTS. Valores de la operación de la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="1f57c-151">Type one of the BTS.Operation values from the table below.</span></span>|  
  
     <span data-ttu-id="1f57c-152">De BTS. Operación, escriba uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f57c-152">For BTS.Operation, enter one of the following values:</span></span>  
  
    |<span data-ttu-id="1f57c-153">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="1f57c-153">Message type</span></span>|<span data-ttu-id="1f57c-154">BTS. Valor de la operación</span><span class="sxs-lookup"><span data-stu-id="1f57c-154">BTS.Operation value</span></span>|  
    |------------------|-------------------------|  
    |<span data-ttu-id="1f57c-155">Todos los tipos de mensaje SWIFT FINÉS de categoría del 0 al 9</span><span class="sxs-lookup"><span data-stu-id="1f57c-155">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="1f57c-156">**A4SWIFT_FrrSendMTMsg**</span><span class="sxs-lookup"><span data-stu-id="1f57c-156">**A4SWIFT_FrrSendMTMsg**</span></span>|  
    |<span data-ttu-id="1f57c-157">MQ Series PAN/NAN (confirmación de nivel de transporte MQ Series/NAK)</span><span class="sxs-lookup"><span data-stu-id="1f57c-157">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="1f57c-158">**A4SWIFT_FrrSendTransport**</span><span class="sxs-lookup"><span data-stu-id="1f57c-158">**A4SWIFT_FrrSendTransport**</span></span>|  
    |<span data-ttu-id="1f57c-159">MT010 (advertencia de no entrega)</span><span class="sxs-lookup"><span data-stu-id="1f57c-159">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="1f57c-160">**A4SWIFT_FrrSend010NDW**</span><span class="sxs-lookup"><span data-stu-id="1f57c-160">**A4SWIFT_FrrSend010NDW**</span></span>|  
    |<span data-ttu-id="1f57c-161">MT011 (notificación de entrega)</span><span class="sxs-lookup"><span data-stu-id="1f57c-161">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="1f57c-162">**A4SWIFT_FrrSend011Delivered**</span><span class="sxs-lookup"><span data-stu-id="1f57c-162">**A4SWIFT_FrrSend011Delivered**</span></span>|  
    |<span data-ttu-id="1f57c-163">MT012 (notificación de remitente)</span><span class="sxs-lookup"><span data-stu-id="1f57c-163">MT012 (Sender Notification)</span></span>|<span data-ttu-id="1f57c-164">**A4SWIFT_FrrSend012SenderACK**</span><span class="sxs-lookup"><span data-stu-id="1f57c-164">**A4SWIFT_FrrSend012SenderACK**</span></span>|  
    |<span data-ttu-id="1f57c-165">MT015 (DIN o NAK diferida)</span><span class="sxs-lookup"><span data-stu-id="1f57c-165">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="1f57c-166">**A4SWIFT_FrrSend015DNK**</span><span class="sxs-lookup"><span data-stu-id="1f57c-166">**A4SWIFT_FrrSend015DNK**</span></span>|  
    |<span data-ttu-id="1f57c-167">MT019 (anular la notificación)</span><span class="sxs-lookup"><span data-stu-id="1f57c-167">MT019 (Abort Notification)</span></span>|<span data-ttu-id="1f57c-168">**A4SWIFT_FrrSend019Abort**</span><span class="sxs-lookup"><span data-stu-id="1f57c-168">**A4SWIFT_FrrSend019Abort**</span></span>|  
    |<span data-ttu-id="1f57c-169">MTS21_FIN_ACKNAK (confirmación de un mensaje FIN enviado por un LT (ACK)</span><span class="sxs-lookup"><span data-stu-id="1f57c-169">MTS21_FIN_ACKNAK (Acknowledgment of a FIN message sent by an LT (ACK)</span></span>|<span data-ttu-id="1f57c-170">**A4SWIFT_FrrSendS21ACK**</span><span class="sxs-lookup"><span data-stu-id="1f57c-170">**A4SWIFT_FrrSendS21ACK**</span></span>|  
    |<span data-ttu-id="1f57c-171">MTS21_FIN_ACKNAK (confirmación de un mensaje FIN enviado por un LT (NAK) de un negativo</span><span class="sxs-lookup"><span data-stu-id="1f57c-171">MTS21_FIN_ACKNAK (Negative acknowledgment of a FIN message sent by an LT (NAK)</span></span>|<span data-ttu-id="1f57c-172">**A4SWIFT_FrrSendS21NAK**</span><span class="sxs-lookup"><span data-stu-id="1f57c-172">**A4SWIFT_FrrSendS21NAK**</span></span>|  
  
11. <span data-ttu-id="1f57c-173">Para mensajes de FIN de SWIFT categoría 0 a 9 y que no se envían correctamente, haga lo siguiente el **filtros** panel:</span><span class="sxs-lookup"><span data-stu-id="1f57c-173">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, do the following in the **Filters** pane:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f57c-174">El **A4SWIFT_FRRFailedReason** propiedades en el siguiente filtro deben estar agrupados.</span><span class="sxs-lookup"><span data-stu-id="1f57c-174">The **A4SWIFT_FRRFailedReason** properties in the following filter should be grouped.</span></span>  
  
    |<span data-ttu-id="1f57c-175">Use</span><span class="sxs-lookup"><span data-stu-id="1f57c-175">Use this</span></span>|<span data-ttu-id="1f57c-176">Para</span><span class="sxs-lookup"><span data-stu-id="1f57c-176">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1f57c-177">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-177">**Property**</span></span>|<span data-ttu-id="1f57c-178">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-178">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="1f57c-179">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-179">**Operator**</span></span>|<span data-ttu-id="1f57c-180">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-180">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-181">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-181">**Value**</span></span>|<span data-ttu-id="1f57c-182">Tipo de **A4SWIFT_FrrService**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-182">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="1f57c-183">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1f57c-183">**Group**</span></span>|<span data-ttu-id="1f57c-184">**Y**</span><span class="sxs-lookup"><span data-stu-id="1f57c-184">**And**</span></span>|  
    |<span data-ttu-id="1f57c-185">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-185">**Property**</span></span>|<span data-ttu-id="1f57c-186">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-186">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.</span></span>|  
    |<span data-ttu-id="1f57c-187">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-187">**Operator**</span></span>|<span data-ttu-id="1f57c-188">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-188">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-189">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-189">**Value**</span></span>|<span data-ttu-id="1f57c-190">Tipo de **True**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-190">Type **True**.</span></span>|  
    |<span data-ttu-id="1f57c-191">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1f57c-191">**Group**</span></span>|<span data-ttu-id="1f57c-192">**Y**</span><span class="sxs-lookup"><span data-stu-id="1f57c-192">**And**</span></span>|  
    |<span data-ttu-id="1f57c-193">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-193">**Property**</span></span>|<span data-ttu-id="1f57c-194">Seleccione **BTS. Operación**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-194">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="1f57c-195">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-195">**Operator**</span></span>|<span data-ttu-id="1f57c-196">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-196">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-197">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-197">**Value**</span></span>|<span data-ttu-id="1f57c-198">Tipo de **A4SWIFT_FrrSendMTMsg**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-198">Type **A4SWIFT_FrrSendMTMsg**.</span></span>|  
    |<span data-ttu-id="1f57c-199">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1f57c-199">**Group**</span></span>|<span data-ttu-id="1f57c-200">**Y**</span><span class="sxs-lookup"><span data-stu-id="1f57c-200">**And**</span></span>|  
    |<span data-ttu-id="1f57c-201">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-201">**Property**</span></span>|<span data-ttu-id="1f57c-202">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-202">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="1f57c-203">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-203">**Operator**</span></span>|<span data-ttu-id="1f57c-204">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-204">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-205">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-205">**Value**</span></span>|<span data-ttu-id="1f57c-206">Tipo de  *\<NAKErrorCode\>*, por ejemplo, "Y01".</span><span class="sxs-lookup"><span data-stu-id="1f57c-206">Type *\<NAKErrorCode\>*, such as "Y01".</span></span>|  
    |<span data-ttu-id="1f57c-207">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1f57c-207">**Group**</span></span>|<span data-ttu-id="1f57c-208">**Or**</span><span class="sxs-lookup"><span data-stu-id="1f57c-208">**Or**</span></span>|  
    |<span data-ttu-id="1f57c-209">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-209">**Property**</span></span>|<span data-ttu-id="1f57c-210">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-210">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="1f57c-211">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-211">**Operator**</span></span>|<span data-ttu-id="1f57c-212">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-212">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-213">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-213">**Value**</span></span>|<span data-ttu-id="1f57c-214">Tipo de **TimedOut**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-214">Type **TimedOut**.</span></span>|  
    |<span data-ttu-id="1f57c-215">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1f57c-215">**Group**</span></span>|<span data-ttu-id="1f57c-216">**Or**</span><span class="sxs-lookup"><span data-stu-id="1f57c-216">**Or**</span></span>|  
    |<span data-ttu-id="1f57c-217">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-217">**Property**</span></span>|<span data-ttu-id="1f57c-218">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-218">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="1f57c-219">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-219">**Operator**</span></span>|<span data-ttu-id="1f57c-220">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-220">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-221">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-221">**Value**</span></span>|<span data-ttu-id="1f57c-222">Tipo de **TransportError**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-222">Type **TransportError**.</span></span>|  
    |<span data-ttu-id="1f57c-223">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1f57c-223">**Group**</span></span>|<span data-ttu-id="1f57c-224">**Or**</span><span class="sxs-lookup"><span data-stu-id="1f57c-224">**Or**</span></span>|  
    |<span data-ttu-id="1f57c-225">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-225">**Property**</span></span>|<span data-ttu-id="1f57c-226">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-226">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="1f57c-227">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-227">**Operator**</span></span>|<span data-ttu-id="1f57c-228">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-228">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-229">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-229">**Value**</span></span>|<span data-ttu-id="1f57c-230">Tipo de **DelayedNAK**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-230">Type **DelayedNAK**.</span></span>|  
    |<span data-ttu-id="1f57c-231">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="1f57c-231">**Group**</span></span>|<span data-ttu-id="1f57c-232">**Or**</span><span class="sxs-lookup"><span data-stu-id="1f57c-232">**Or**</span></span>|  
    |<span data-ttu-id="1f57c-233">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1f57c-233">**Property**</span></span>|<span data-ttu-id="1f57c-234">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-234">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="1f57c-235">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1f57c-235">**Operator**</span></span>|<span data-ttu-id="1f57c-236">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="1f57c-236">Select **==**.</span></span>|  
    |<span data-ttu-id="1f57c-237">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f57c-237">**Value**</span></span>|<span data-ttu-id="1f57c-238">Tipo de **AbortMessage**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-238">Type **AbortMessage**.</span></span>|  
  
12. <span data-ttu-id="1f57c-239">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-239">Click **Apply**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="1f57c-240">Haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="1f57c-240">Right-click the send port, and then click **Start**.</span></span>  
  
14. <span data-ttu-id="1f57c-241">Repita los pasos del 2 al 13 para crear un puerto de envío para cada tipo de mensaje requerido.</span><span class="sxs-lookup"><span data-stu-id="1f57c-241">Repeat steps 2 through 13 to create a send port for each message type required.</span></span>