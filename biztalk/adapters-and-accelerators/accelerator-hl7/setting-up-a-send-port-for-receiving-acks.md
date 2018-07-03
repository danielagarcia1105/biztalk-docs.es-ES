---
title: Configurar un puerto de envío para recibir confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f70be6d66d0ba8aa3385760bfc17b4b19f50351a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984749"
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a><span data-ttu-id="c0508-102">Configurar un puerto de envío para recibir confirmaciones</span><span class="sxs-lookup"><span data-stu-id="c0508-102">Setting Up a Send Port for Receiving ACKs</span></span>
<span data-ttu-id="c0508-103">Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) puede recibir confirmaciones (ACK) en un puerto de envío unidireccional.</span><span class="sxs-lookup"><span data-stu-id="c0508-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) can receive acknowledgments (ACK) on a one-way send port.</span></span> <span data-ttu-id="c0508-104">Al configurar un puerto de envío unidireccional para recibir confirmaciones en la misma conexión, debe asociar ese envío Puerto unidireccional con el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="c0508-104">When you set up a new one-way send port for receiving ACKs on the same connection, you must associate that send port with a one-way receive port.</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="c0508-105"> programa de instalación crea un unidireccional puerto de recepción (llamado **TwoWayAckReceivePort**) y la ubicación de recepción (llamado **TwoWayAckReceiveLocation**).</span><span class="sxs-lookup"><span data-stu-id="c0508-105"> setup creates a one-way receive port (called **TwoWayAckReceivePort**) and receive location (called **TwoWayAckReceiveLocation**).</span></span> <span data-ttu-id="c0508-106">La ubicación de recepción utiliza el tipo de transporte de protocolo de nivel inferior mínimo (MLLP), tiene un identificador URI de "127.0.0.1:65535" y utiliza el **BTAHL72XReceivePipeline**.</span><span class="sxs-lookup"><span data-stu-id="c0508-106">The receive location uses the Minimal Lower Layer Protocol (MLLP) transport type, has a URI of "127.0.0.1:65535", and uses the **BTAHL72XReceivePipeline**.</span></span> <span data-ttu-id="c0508-107">Se trata de la configuración necesaria para la recepción y procesamiento de confirmación recibida un mensaje enviado por el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] enviar adaptador, en modo bidireccional.</span><span class="sxs-lookup"><span data-stu-id="c0508-107">These are the settings required for receiving and processing an ACK received against a message sent out by the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] send adapter, in two-way mode.</span></span> <span data-ttu-id="c0508-108">Esta ubicación de recepción no deberían eliminarse o usar para otros fines.</span><span class="sxs-lookup"><span data-stu-id="c0508-108">This receive location should not be deleted or used for any other purposes.</span></span> <span data-ttu-id="c0508-109">Nunca se envían datos a esta ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="c0508-109">Never send data to this receive location.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="c0508-110"> permite que esta ubicación de recepción de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c0508-110"> enables this receive location by default.</span></span>  
  
 <span data-ttu-id="c0508-111">**TwoWayAckReceiveLocation**, que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Asistente para configuración crea, utiliza el **BizTalkServerApplication** como el controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="c0508-111">**TwoWayAckReceiveLocation**, which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Setup Wizard creates, uses the **BizTalkServerApplication** as the receive handler.</span></span> <span data-ttu-id="c0508-112">Sin embargo, si decide crear un nuevo host y usarlo como el controlador de recepción de MLLP, a continuación, debe hacer lo siguiente para crear un nuevo **TwoWayAckReceiveLocation**:</span><span class="sxs-lookup"><span data-stu-id="c0508-112">However, if you choose to create a new host and use it as the receive handler for MLLP, then you must do the following to create a new **TwoWayAckReceiveLocation**:</span></span>  
  
1.  <span data-ttu-id="c0508-113">Crear un sentido puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="c0508-113">Create a one-way receive port.</span></span>  
  
2.  <span data-ttu-id="c0508-114">Crear un sentido ubicación de recepción de MLLP.</span><span class="sxs-lookup"><span data-stu-id="c0508-114">Create a one-way MLLP receive location.</span></span>  
  
3.  <span data-ttu-id="c0508-115">Especifique los valores adecuados para las propiedades de transporte MLLP.</span><span class="sxs-lookup"><span data-stu-id="c0508-115">Specify the appropriate values for the MLLP transport properties.</span></span>  
  
4.  <span data-ttu-id="c0508-116">Especifique el que controlador de recepción adecuado.</span><span class="sxs-lookup"><span data-stu-id="c0508-116">Specify the appropriate receive handler.</span></span>  
  
5.  <span data-ttu-id="c0508-117">Habilitar la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="c0508-117">Enable the receive location.</span></span>  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a><span data-ttu-id="c0508-118">Para crear un puerto de envío habilitado para recibir una confirmación en el mismo socket</span><span class="sxs-lookup"><span data-stu-id="c0508-118">To create a send port enabled to receive an ACK on the same socket</span></span>  
  
1.  <span data-ttu-id="c0508-119">Abra la consola de administración de BizTalk y, a continuación, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **BizTalk Aplicación 1**.</span><span class="sxs-lookup"><span data-stu-id="c0508-119">Open the BizTalk Administration Console, and then expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="c0508-120">Haga clic en **puertos de envío**, elija Nuevo y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="c0508-120">Right-click **Send Ports**, point to New, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="c0508-121">En el **nombre** , escriba el nombre del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c0508-121">In the **Name** box, type the name of the send port.</span></span>  
  
3.  <span data-ttu-id="c0508-122">En el **transporte** sección, para **tipo**, seleccione **MLLP**.</span><span class="sxs-lookup"><span data-stu-id="c0508-122">In the **Transport** section, for **Type**, select **MLLP**.</span></span>  
  
4.  <span data-ttu-id="c0508-123">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="c0508-123">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="c0508-124">En el cuadro de diálogo Propiedades de transporte de MLLP, escriba un nombre de la conexión y un host (por ejemplo, **localhost**).</span><span class="sxs-lookup"><span data-stu-id="c0508-124">In the MLLP Transport Properties dialog box, type a connection name and host (for instance, **localhost**).</span></span>  
  
6.  <span data-ttu-id="c0508-125">Para **de petición respuesta habilitado**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c0508-125">For **Solicit Response Enabled**, select **Yes**.</span></span> <span data-ttu-id="c0508-126">Deje **enviar recibir ubicación (URI) para la confirmación** en blanco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c0508-126">Leave **Submit Receive Location (URI) for ACK** blank, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0508-127">Si se deja **ubicación de recepción envíe** en blanco, BTAHL7 entra en el URI para el valor predeterminado **TwoWayAckReceiveLocation**.</span><span class="sxs-lookup"><span data-stu-id="c0508-127">When you leave **Submit Receive Location** blank, BTAHL7 enters the URI for the default **TwoWayAckReceiveLocation**.</span></span> <span data-ttu-id="c0508-128">Puede comprobar que una vez al hacer clic **Aceptar** en el paso 6, al hacer clic en **configuración** nuevo.</span><span class="sxs-lookup"><span data-stu-id="c0508-128">You can verify that after clicking **OK** in step 6, by clicking **Configuration** again.</span></span> <span data-ttu-id="c0508-129">El URI para **TwoWayAckReceiveLocation** (127.0.0.1:65535) se escribirán en **enviar recibir ubicación (URI) para la confirmación**.</span><span class="sxs-lookup"><span data-stu-id="c0508-129">The URI for **TwoWayAckReceiveLocation** (127.0.0.1:65535) will be entered in **Submit Receive Location (URI) for ACK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0508-130">Debe crear un puerto de envío para suscribirse a ha recibido la confirmación o la confirmación se verán en un estado suspendido, porque no se encontraron suscripciones.</span><span class="sxs-lookup"><span data-stu-id="c0508-130">You must create a send port to subscribe to the ACK received, or the ACK will be seen in a suspended state, because no subscriptions were found.</span></span> <span data-ttu-id="c0508-131">Para suscribirse a las Confirmaciones recibidas por el puerto de envío, use los filtros, por ejemplo, **BTS. MessageType == \< *MessageType* \>**  y **BTS. ReceivePortName == \< *puertoRecepción*\>**.</span><span class="sxs-lookup"><span data-stu-id="c0508-131">To subscribe to the ACK received by the send port, use filters, for example, **BTS.MessageType == \<*MessageType*\>** and **BTS.ReceivePortName == \<*ReceivePort*\>**.</span></span> <span data-ttu-id="c0508-132">Para confirmaciones estáticas, es el tipo de mensaje **StaticAck**.</span><span class="sxs-lookup"><span data-stu-id="c0508-132">For static ACKs, the message type is **StaticAck**.</span></span>  
  
7.  <span data-ttu-id="c0508-133">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c0508-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0508-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0508-134">See Also</span></span>  
 <span data-ttu-id="c0508-135">[Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="c0508-135">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="c0508-136">[Tipos de esquema de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="c0508-136">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="c0508-137">[Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="c0508-137">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="c0508-138">Condiciones de error de confirmación</span><span class="sxs-lookup"><span data-stu-id="c0508-138">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)