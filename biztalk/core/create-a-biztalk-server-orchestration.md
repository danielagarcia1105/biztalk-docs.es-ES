---
title: "Crear una orquestación de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c637ae-f94f-40f8-8ce7-73a7b7df9f8f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6223ab8d8aa3c8d1c20559a88257dd0dccaa22e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="create-a-biztalk-server-orchestration"></a><span data-ttu-id="7986c-102">Crear una orquestación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7986c-102">Create a BizTalk Server orchestration</span></span>
> [!NOTE]
>  <span data-ttu-id="7986c-103">Este tutorial solo se aplica a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7986c-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="7986c-104">Cree una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que, al implementarla, reciba un mensaje de pedido de compra JSON, lo transforme en una factura XML y envíe una factura JSON.</span><span class="sxs-lookup"><span data-stu-id="7986c-104">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that, when deployed, receives a JSON purchase order message, transforms it to an XML invoice, and then sends out a JSON invoice.</span></span>  
  
## <a name="define-message-and-message-types"></a><span data-ttu-id="7986c-105">Definir el mensaje y los tipos de mensaje</span><span class="sxs-lookup"><span data-stu-id="7986c-105">Define message and message types</span></span>  
 <span data-ttu-id="7986c-106">Esta solución funciona con dos mensajes básicos: pedido de compra y factura.</span><span class="sxs-lookup"><span data-stu-id="7986c-106">This solution works with two basic messages – purchase order and invoice.</span></span> <span data-ttu-id="7986c-107">Ya hemos generado el esquema del pedido de compra a partir de un mensaje JSON usando el asistente para esquemas JSON.</span><span class="sxs-lookup"><span data-stu-id="7986c-107">We already generated the schema of the purchase order from a JSON message using the JSON schema wizard.</span></span> <span data-ttu-id="7986c-108">El ejemplo que se proporciona para este tutorial ya tiene el esquema para el mensaje de factura.</span><span class="sxs-lookup"><span data-stu-id="7986c-108">The sample provided for this tutorial already has the schema for the invoice message.</span></span> <span data-ttu-id="7986c-109">Estos esquemas se usan para crear los tipos de mensaje en la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7986c-109">We use these schemas to create the message types in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
1.  <span data-ttu-id="7986c-110">Agregue una orquestación al proyecto de BizTalk y abra la Vista orquestación.</span><span class="sxs-lookup"><span data-stu-id="7986c-110">Add an orchestration to the BizTalk project and open the Orchestration view.</span></span>  
  
2.  <span data-ttu-id="7986c-111">En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="7986c-111">In the Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="7986c-112">Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7986c-112">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="7986c-113">En el **propiedades** panel para la **Message_1**, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7986c-113">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="7986c-114">Use</span><span class="sxs-lookup"><span data-stu-id="7986c-114">Use this</span></span>|<span data-ttu-id="7986c-115">Para</span><span class="sxs-lookup"><span data-stu-id="7986c-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7986c-116">Identificador</span><span class="sxs-lookup"><span data-stu-id="7986c-116">Identifier</span></span>|<span data-ttu-id="7986c-117">Escriba `PurchaseOrder`</span><span class="sxs-lookup"><span data-stu-id="7986c-117">Type `PurchaseOrder`</span></span>|  
    |<span data-ttu-id="7986c-118">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="7986c-118">Message Type</span></span>|<span data-ttu-id="7986c-119">En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *BTSJSON. Pedido de compra*, donde *BTSJSON* es el nombre de su proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7986c-119">From the drop-down list, expand **Schemas**, and then select *BTSJSON.PO*, where *BTSJSON* is the name of your BizTalk project.</span></span>|  
  
5.  <span data-ttu-id="7986c-120">Repita el paso anterior para crear un nuevo tipo de mensaje para el mensaje de factura.</span><span class="sxs-lookup"><span data-stu-id="7986c-120">Repeat the previous step to create a new message type for the invoice message.</span></span> <span data-ttu-id="7986c-121">En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7986c-121">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="7986c-122">Use</span><span class="sxs-lookup"><span data-stu-id="7986c-122">Use this</span></span>|<span data-ttu-id="7986c-123">Para</span><span class="sxs-lookup"><span data-stu-id="7986c-123">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7986c-124">Identificador</span><span class="sxs-lookup"><span data-stu-id="7986c-124">Identifier</span></span>|<span data-ttu-id="7986c-125">Escriba `InvoiceMsg`</span><span class="sxs-lookup"><span data-stu-id="7986c-125">Type `InvoiceMsg`</span></span>|  
    |<span data-ttu-id="7986c-126">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="7986c-126">Message Type</span></span>|<span data-ttu-id="7986c-127">En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *BTSJSON. Factura*.</span><span class="sxs-lookup"><span data-stu-id="7986c-127">From the drop-down list, expand **Schemas**, and then select *BTSJSON.Invoice*.</span></span>|  
  
## <a name="set-up-the-orchestration"></a><span data-ttu-id="7986c-128">Configurar la orquestación</span><span class="sxs-lookup"><span data-stu-id="7986c-128">Set up the orchestration</span></span>  
 <span data-ttu-id="7986c-129">En este paso, va a agregar formas de mensaje y puertos para crear una orquestación.</span><span class="sxs-lookup"><span data-stu-id="7986c-129">In this step, you add message shapes and ports to create an orchestration.</span></span>  
  
### <a name="add-message-shapes"></a><span data-ttu-id="7986c-130">Agregar formas de mensaje</span><span class="sxs-lookup"><span data-stu-id="7986c-130">Add message shapes</span></span>  
 <span data-ttu-id="7986c-131">Abra el archivo de orquestación desde el Explorador de soluciones y agregue las siguientes formas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="7986c-131">Open the orchestration file from Solution Explorer, and add the following message shapes.</span></span>  
  
-   <span data-ttu-id="7986c-132">Agregar una forma recepción, dele el nombre **ReceivePO**y el tipo de mensaje **PurchaseOrder**.</span><span class="sxs-lookup"><span data-stu-id="7986c-132">Add a Receive shape, set its name to **ReceivePO**, and message type to **PurchaseOrder**.</span></span>  
  
-   <span data-ttu-id="7986c-133">Agregue una forma de envío, dele el nombre **SendInvoice**y el tipo de mensaje **InvoiceMsg**.</span><span class="sxs-lookup"><span data-stu-id="7986c-133">Add a Send shape, set its name to **SendInvoice**, and message type to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="7986c-134">Agregue una forma construir mensaje y establezca el **mensajes construidos** propiedad de la forma construir mensaje a **InvoiceMsg**.</span><span class="sxs-lookup"><span data-stu-id="7986c-134">Add a Construct Message shape and set the **Messages Constructed** property of the Construct Message shape to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="7986c-135">Agregue una forma Transformación a la forma Construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="7986c-135">Add a Transform shape within the Construct Message shape.</span></span> <span data-ttu-id="7986c-136">Haga doble clic en la forma transformación y, en la **configuración de transformación** cuadro de diálogo, seleccione la **mapa existente** opción y, a continuación, seleccione **BTSJSON. POToInvoice** mapa.</span><span class="sxs-lookup"><span data-stu-id="7986c-136">Double-click the Transform shape and in the **Transform Configuration** dialog box, select the **Existing Map** option, and then select **BTSJSON.POToInvoice** map.</span></span> <span data-ttu-id="7986c-137">Esta asignación se proporciona como parte del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7986c-137">This map is provided as part of the sample.</span></span> <span data-ttu-id="7986c-138">En el cuadro de diálogo, establezca **origen** a **PurchaseOrder** y establecer **destino** a **InvoiceMsg**.</span><span class="sxs-lookup"><span data-stu-id="7986c-138">In the dialog box, set **Source** to **PurchaseOrder** and set **Destination** to **InvoiceMsg**.</span></span> <span data-ttu-id="7986c-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7986c-139">Click **OK**.</span></span>  
  
### <a name="add-ports"></a><span data-ttu-id="7986c-140">Agregar puertos</span><span class="sxs-lookup"><span data-stu-id="7986c-140">Add ports</span></span>  
 <span data-ttu-id="7986c-141">Agregue dos puertos a la orquestación: uno para recibir mensajes y otro para enviarlos.</span><span class="sxs-lookup"><span data-stu-id="7986c-141">Add two ports to the orchestration – one for receiving messages and one for sending messages.</span></span> <span data-ttu-id="7986c-142">Use las siguientes propiedades para los puertos:</span><span class="sxs-lookup"><span data-stu-id="7986c-142">Use the following properties for the ports.</span></span>  
  
|<span data-ttu-id="7986c-143">Puerto</span><span class="sxs-lookup"><span data-stu-id="7986c-143">Port</span></span>|<span data-ttu-id="7986c-144">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7986c-144">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="7986c-145">MessageIn</span><span class="sxs-lookup"><span data-stu-id="7986c-145">MessageIn</span></span>|<span data-ttu-id="7986c-146">-Establecer **identificador** a *ReceiveJSONPO*</span><span class="sxs-lookup"><span data-stu-id="7986c-146">-   Set **Identifier** to *ReceiveJSONPO*</span></span><br /><span data-ttu-id="7986c-147">-Establecer **patrón de comunicación** a *unidireccional*</span><span class="sxs-lookup"><span data-stu-id="7986c-147">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="7986c-148">-Establecer **dirección de comunicación** a *de recepción*</span><span class="sxs-lookup"><span data-stu-id="7986c-148">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="7986c-149">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="7986c-149">ResponseOut</span></span>|<span data-ttu-id="7986c-150">-Establecer **identificador** a *SendJSONInvoice*</span><span class="sxs-lookup"><span data-stu-id="7986c-150">-   Set **Identifier** to *SendJSONInvoice*</span></span><br /><span data-ttu-id="7986c-151">-Establecer **patrón de comunicación** a *unidireccional*</span><span class="sxs-lookup"><span data-stu-id="7986c-151">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="7986c-152">-Establecer **dirección de comunicación** a *enviar*</span><span class="sxs-lookup"><span data-stu-id="7986c-152">-   Set **Communication Direction** to *Send*</span></span>|  
  
 <span data-ttu-id="7986c-153">Conecte los puertos y la forma del mensaje, como se muestra en la siguiente captura de pantalla, y guarde los cambios del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7986c-153">Connect the ports and message shape, as shown in the screenshot below, and save changes to the project.</span></span>  
  
 <span data-ttu-id="7986c-154">![Orquestación para procesar mensajes JSON](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span><span class="sxs-lookup"><span data-stu-id="7986c-154">![Orchestration to process JSON messages](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7986c-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="7986c-155">See Also</span></span>  
 [<span data-ttu-id="7986c-156">Procesamiento de mensajes JSON con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7986c-156">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)