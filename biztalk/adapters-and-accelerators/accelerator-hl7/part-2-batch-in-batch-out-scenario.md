---
title: 'Parte 2: En lotes escenario | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593f1e57b12eb30f47db65bfacd34a988f701f07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975421"
---
# <a name="part-2-batch-inbatch-out-scenario"></a><span data-ttu-id="628b9-102">Parte 2: Proceso por lotes en / escenario de lote</span><span class="sxs-lookup"><span data-stu-id="628b9-102">Part 2: Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="628b9-103">En esta parte del tutorial, se recibe un archivo de lotes codificados en HL7, pasarlo a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sin fragmentación y envíe el archivo por lotes intacto al destino.</span><span class="sxs-lookup"><span data-stu-id="628b9-103">In this part of the tutorial, you receive an HL7-encoded batch file, pass it through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without fragmentation, and send the intact batch file to the destination.</span></span> <span data-ttu-id="628b9-104">En la siguiente ilustración muestra el flujo de este proceso y la subsección siguiente describe el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="628b9-104">The following figure shows the flow of this process, and the subsection below describes the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="628b9-105">Antes de iniciar esta parte del tutorial, desactive las herramientas de MllpReceive y MllpSend que usó en la parte 1, al cerrar los símbolos.</span><span class="sxs-lookup"><span data-stu-id="628b9-105">Before starting this part of the tutorial, turn off the MllpReceive and MllpSend tools that you used in Part 1, by closing the command prompts.</span></span>  
  
 <span data-ttu-id="628b9-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")</span><span class="sxs-lookup"><span data-stu-id="628b9-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")</span></span>  
  
 <span data-ttu-id="628b9-107">**Cómo fluyen los mensajes del lote en / escenario de lote**</span><span class="sxs-lookup"><span data-stu-id="628b9-107">**How messages flow in the Batch In/Batch Out scenario**</span></span>  
  
 <span data-ttu-id="628b9-108">Este escenario incluye el flujo de trabajo siguiente:</span><span class="sxs-lookup"><span data-stu-id="628b9-108">This scenario includes the following workflow:</span></span>  
  
1. <span data-ttu-id="628b9-109">El flujo de trabajo se inicia cuando una aplicación de línea de negocio envía un lote de mensajes para el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) mediante el protocolo de archivo de motor de integración.</span><span class="sxs-lookup"><span data-stu-id="628b9-109">The workflow begins when a line-of-business application sends a message batch to the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Integration Engine using the FILE protocol.</span></span> <span data-ttu-id="628b9-110">El lote contiene dos versiones de un ADT ^ A03 mensaje.</span><span class="sxs-lookup"><span data-stu-id="628b9-110">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="628b9-111">La aplicación de origen pertenece a la entidad Tutorial_BatchSource.</span><span class="sxs-lookup"><span data-stu-id="628b9-111">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2. <span data-ttu-id="628b9-112">El motor de integración recibe el lote en un archivo de puerto de recepción y valida el lote de mensajes.</span><span class="sxs-lookup"><span data-stu-id="628b9-112">The Integration Engine receives the batch on a FILE receive port, and validates the message batch.</span></span> <span data-ttu-id="628b9-113">(El nivel de validación depende de la configuración seleccionada para la entidad de origen en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.)</span><span class="sxs-lookup"><span data-stu-id="628b9-113">(The level of validation depends on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.)</span></span>  
  
3. <span data-ttu-id="628b9-114">En función de una configuración en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración que deshabilita la fragmentación de lote para la entidad, el motor de la interfaz no se analiza el lote en mensajes individuales, pero deja el lote como un lote.</span><span class="sxs-lookup"><span data-stu-id="628b9-114">Based on a setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer that disables batch fragmentation for the party, the Interface Engine does not parse the batch into individual messages, but leaves the batch as a batch.</span></span> <span data-ttu-id="628b9-115">Valida los mensajes individuales, nuevamente basados en la configuración seleccionada para la entidad de origen en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="628b9-115">It validates the individual messages, again based on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
4. <span data-ttu-id="628b9-116">El motor de la interfaz genera una confirmación para el mensaje por lotes, según la configuración de la definición de confirmación en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Editor de configuración para la entidad.</span><span class="sxs-lookup"><span data-stu-id="628b9-116">The Interface Engine generates an acknowledgment for the batch message, based on the acknowledgment definition settings in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Editor for the party.</span></span> <span data-ttu-id="628b9-117">En este caso, selecciona el modo de confirmación Original, por lo que el motor de la interfaz genera una confirmación de aceptación de la aplicación solo para el lote de mensajes después de validar el encabezado del mensaje y el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="628b9-117">In this case, you select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for the message batch after validating both the message header and body.</span></span> <span data-ttu-id="628b9-118">El motor de la confirmación en función del esquema ACK_024_GLO_DEF basa, escribirá "AA" en el campo MSA2 de la confirmación, entra en la entidad de destino en MSH3 y entra en la entidad de origen en MSH5.</span><span class="sxs-lookup"><span data-stu-id="628b9-118">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5. <span data-ttu-id="628b9-119">Adaptador configurado para procesar las confirmaciones de envío de las rutas de motor de la interfaz del lote de confirmación al origen de terceros a través de un archivo.</span><span class="sxs-lookup"><span data-stu-id="628b9-119">The Interface Engine routes the acknowledgment batch to the source party through a FILE send adapter set up to process acknowledgments.</span></span> <span data-ttu-id="628b9-120">En este caso, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] enruta el lote a la carpeta \Tutorial_BatchACKDrop.</span><span class="sxs-lookup"><span data-stu-id="628b9-120">In this case, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] routes the batch to the \Tutorial_BatchACKDrop folder.</span></span>  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="628b9-121"> envía que el lote de mensajes al destino especificado para la entidad de destino, en este caso el \Tutorial_BTAHL7Drop carpeta.</span><span class="sxs-lookup"><span data-stu-id="628b9-121"> sends the message batch to the destination specified for the destination party, in this case the folder \Tutorial_BTAHL7Drop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="628b9-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="628b9-122">In This Section</span></span>  
  
-   [<span data-ttu-id="628b9-123">Paso 1: Configurar la información de entidad para el lote de entrada o salida</span><span class="sxs-lookup"><span data-stu-id="628b9-123">Step 1: Configure Party Information for Batch In/Batch Out</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [<span data-ttu-id="628b9-124">Paso 2: Modificar o crear los puertos de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="628b9-124">Step 2: Modify or Create the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="628b9-125">Paso 3: Probar el escenario de lote de entrada o salida</span><span class="sxs-lookup"><span data-stu-id="628b9-125">Step 3: Test the Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)