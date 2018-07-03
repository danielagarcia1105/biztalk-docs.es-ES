---
title: 'Parte 1: Escenario de lote de entrada fragmentado | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5cf6f38daca7b1773798e4bc8ed2e40ad143bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970509"
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a><span data-ttu-id="e785b-102">Parte 1: Escenario de lote de entrada fragmentado</span><span class="sxs-lookup"><span data-stu-id="e785b-102">Part 1: Fragmented Inbound Batch Scenario</span></span>
<span data-ttu-id="e785b-103">En esta parte del tutorial, recibir un lote con codificación HL7, fragmento de en mensajes individuales y enviar los mensajes individuales a un destino.</span><span class="sxs-lookup"><span data-stu-id="e785b-103">In this part of the tutorial, you receive an HL7-encoded batch, fragment it into individual messages, and send the individual messages to a destination.</span></span> <span data-ttu-id="e785b-104">En la siguiente ilustración muestra el flujo de este proceso.</span><span class="sxs-lookup"><span data-stu-id="e785b-104">The following figure shows the flow of this process.</span></span>  
  
 <span data-ttu-id="e785b-105">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")</span><span class="sxs-lookup"><span data-stu-id="e785b-105">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")</span></span>  
  
 <span data-ttu-id="e785b-106">Este escenario incluye el flujo de trabajo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e785b-106">This scenario includes the following workflow:</span></span>  
  
1. <span data-ttu-id="e785b-107">El flujo de trabajo se inicia cuando una aplicación de línea de negocio envía un lote de mensajes de Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] motor de integración mediante el protocolo del protocolo de nivel inferior mínimo (MLLP).</span><span class="sxs-lookup"><span data-stu-id="e785b-107">The workflow begins when a line-of-business application sends a message batch to the Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Integration Engine using the Minimal Lower Layer Protocol (MLLP) protocol.</span></span> <span data-ttu-id="e785b-108">El lote contiene dos versiones de un ADT ^ A03 mensaje.</span><span class="sxs-lookup"><span data-stu-id="e785b-108">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="e785b-109">La aplicación de origen pertenece a la entidad Tutorial_BatchSource.</span><span class="sxs-lookup"><span data-stu-id="e785b-109">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2. <span data-ttu-id="e785b-110">El motor de la interfaz se recibe el lote en un MLLP puerto de recepción y valida el lote de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e785b-110">The Interface Engine receives the batch on an MLLP receive port, and validates the message batch.</span></span> <span data-ttu-id="e785b-111">(El nivel de validación depende de configuración seleccionada para la entidad de origen en el Explorador de configuración de BTAHL7).</span><span class="sxs-lookup"><span data-stu-id="e785b-111">(The level of validation depends on settings selected for the source party in BTAHL7 Configuration Explorer.)</span></span>  
  
3. <span data-ttu-id="e785b-112">Basándose en una configuración en el Explorador de configuración de BTAHL7 que permite la fragmentación de lote, el motor de la interfaz analiza el lote en dos ADT individuales ^ A03 mensajes.</span><span class="sxs-lookup"><span data-stu-id="e785b-112">Based on a setting in BTAHL7 Configuration Explorer that enables batch fragmentation, the Interface Engine parses the batch into two individual ADT^A03 messages.</span></span> <span data-ttu-id="e785b-113">Valida los mensajes individuales, nuevamente basados en la configuración seleccionada para la entidad de origen en el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="e785b-113">It validates the individual messages, again based on settings selected for the source party in BTAHL7 Configuration Explorer.</span></span>  
  
4. <span data-ttu-id="e785b-114">El motor de la interfaz genera una confirmación para cada mensaje, según la configuración de la definición de confirmación en el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="e785b-114">The Interface Engine generates an acknowledgment for each message, based on the acknowledgment definition settings in BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="e785b-115">En este tutorial, seleccionará el modo de confirmación Original, por lo que el motor de la interfaz genera una confirmación de aplicación acepte única para cada mensaje después de validar el encabezado del mensaje y el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e785b-115">In this tutorial, you will select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for each message after validating both the message header and body.</span></span> <span data-ttu-id="e785b-116">El motor de la confirmación en función del esquema ACK_024_GLO_DEF basa, escribirá "AA" en el campo MSA2 de la confirmación, entra en la entidad de destino en MSH3 y entra en la entidad de origen en MSH5.</span><span class="sxs-lookup"><span data-stu-id="e785b-116">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5. <span data-ttu-id="e785b-117">El motor de la interfaz coloca contenedores MLLP en torno a cada confirmación, y las rutas de las confirmaciones en el origen de terceros a través de un adaptador de envío MLLP configuración para procesar confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="e785b-117">The Interface Engine places MLLP wrappers around each acknowledgment, and routes the acknowledgments to the source party through an MLLP send adapter set up to process acknowledgments.</span></span>  
  
6. <span data-ttu-id="e785b-118">El motor de interfaz incluye contenedores MLLP en torno a cada mensaje y las rutas configurada para procesar los mensajes de confirmación de que no sean de puerto de envío de cada mensaje de forma individual para un MLLP.</span><span class="sxs-lookup"><span data-stu-id="e785b-118">The Interface Engine places MLLP wrappers around each message, and routes each message individually to an MLLP send port set up to process non-acknowledgment messages.</span></span>  
  
7. <span data-ttu-id="e785b-119">BTAHL7 envía cada mensaje a través de otro puerto de envío MLLP al destino especificado en el campo MSH5.</span><span class="sxs-lookup"><span data-stu-id="e785b-119">BTAHL7 sends each message through another MLLP send port to the destination specified in its MSH5 field.</span></span>  
  
8. <span data-ttu-id="e785b-120">La entidad de destino que se envía a BTAHL7 una confirmación para cada mensaje que recibió de aceptación de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e785b-120">The destination party sends to BTAHL7 an application-accept acknowledgment for each message that it received.</span></span>  
  
9. <span data-ttu-id="e785b-121">El motor de la interfaz se recibe cada confirmación.</span><span class="sxs-lookup"><span data-stu-id="e785b-121">The Interface Engine receives each acknowledgment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e785b-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e785b-122">In This Section</span></span>  
  
-   [<span data-ttu-id="e785b-123">Paso 1: Agregar esquemas de encabezado y confirmación</span><span class="sxs-lookup"><span data-stu-id="e785b-123">Step 1: Add Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="e785b-124">Paso 2: Agregar los esquemas comunes para v2.3.1</span><span class="sxs-lookup"><span data-stu-id="e785b-124">Step 2: Add Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="e785b-125">Paso 3: Agregar un esquema de desencadenador de eventos (mensaje)</span><span class="sxs-lookup"><span data-stu-id="e785b-125">Step 3: Add a Trigger Event (Message) Schema</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [<span data-ttu-id="e785b-126">Paso 4: Crear el puerto de recepción para aceptar el mensaje de lote</span><span class="sxs-lookup"><span data-stu-id="e785b-126">Step 4: Create a Receive Port for Accepting the Batch Message</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [<span data-ttu-id="e785b-127">Paso 5: Crear un puerto de envío para entregar mensajes</span><span class="sxs-lookup"><span data-stu-id="e785b-127">Step 5: Create a Send Port to Deliver Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [<span data-ttu-id="e785b-128">Paso 6: Crear un puerto de envío para entregar confirmaciones</span><span class="sxs-lookup"><span data-stu-id="e785b-128">Step 6: Create a Send Port to Deliver Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [<span data-ttu-id="e785b-129">Paso 7: Crear y configurar una entidad de origen</span><span class="sxs-lookup"><span data-stu-id="e785b-129">Step 7: Create and Configure a Source Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [<span data-ttu-id="e785b-130">Paso 8: Reiniciar BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e785b-130">Step 8: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="e785b-131">Parte 9: Comprobar el escenario de lote de entrada fragmentado</span><span class="sxs-lookup"><span data-stu-id="e785b-131">Step 9: Verify the Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)