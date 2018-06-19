---
title: 'Parte 1: Escenario de fragmentados por lotes entrantes | Documentos de Microsoft'
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
ms.openlocfilehash: d8891bd09c803c77e1878b304f5db5b71a26ab9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206220"
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a><span data-ttu-id="cf544-102">Parte 1: Escenario de fragmentados por lotes entrantes</span><span class="sxs-lookup"><span data-stu-id="cf544-102">Part 1: Fragmented Inbound Batch Scenario</span></span>
<span data-ttu-id="cf544-103">En esta parte del tutorial, recibir un lote con codificación HL7, fragmentar en mensajes individuales y enviar los mensajes individuales a un destino.</span><span class="sxs-lookup"><span data-stu-id="cf544-103">In this part of the tutorial, you receive an HL7-encoded batch, fragment it into individual messages, and send the individual messages to a destination.</span></span> <span data-ttu-id="cf544-104">En la siguiente ilustración muestra el flujo de este proceso.</span><span class="sxs-lookup"><span data-stu-id="cf544-104">The following figure shows the flow of this process.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 <span data-ttu-id="cf544-105">Este escenario incluye el siguiente flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="cf544-105">This scenario includes the following workflow:</span></span>  
  
1.  <span data-ttu-id="cf544-106">El flujo de trabajo comienza a contar cuando una aplicación de línea de negocio envía un lote de mensajes a la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] motor de integración mediante el protocolo de capa de protocolo inferior mínimo (MLLP).</span><span class="sxs-lookup"><span data-stu-id="cf544-106">The workflow begins when a line-of-business application sends a message batch to the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Integration Engine using the Minimal Lower Layer Protocol (MLLP) protocol.</span></span> <span data-ttu-id="cf544-107">El lote contiene dos versiones de un ADT ^ A03 mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf544-107">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="cf544-108">La aplicación de origen pertenece a la entidad Tutorial_BatchSource.</span><span class="sxs-lookup"><span data-stu-id="cf544-108">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2.  <span data-ttu-id="cf544-109">El motor de la interfaz recibe el lote en un MLLP puerto de recepción y valida el lote de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf544-109">The Interface Engine receives the batch on an MLLP receive port, and validates the message batch.</span></span> <span data-ttu-id="cf544-110">(El nivel de validación depende de configuración seleccionada para la entidad de origen en el Explorador de configuración de BTAHL7).</span><span class="sxs-lookup"><span data-stu-id="cf544-110">(The level of validation depends on settings selected for the source party in BTAHL7 Configuration Explorer.)</span></span>  
  
3.  <span data-ttu-id="cf544-111">En función de una configuración en el Explorador de configuración de BTAHL7 que permite la fragmentación de lote, el motor de interfaz analiza el lote en dos ADT individuales ^ A03 mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf544-111">Based on a setting in BTAHL7 Configuration Explorer that enables batch fragmentation, the Interface Engine parses the batch into two individual ADT^A03 messages.</span></span> <span data-ttu-id="cf544-112">Valida los mensajes individuales, nuevo en función de la configuración seleccionada para la entidad de origen en el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="cf544-112">It validates the individual messages, again based on settings selected for the source party in BTAHL7 Configuration Explorer.</span></span>  
  
4.  <span data-ttu-id="cf544-113">El motor de interfaz genera una confirmación para cada mensaje, en función de la configuración de la definición de confirmación en el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="cf544-113">The Interface Engine generates an acknowledgment for each message, based on the acknowledgment definition settings in BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="cf544-114">En este tutorial, seleccionará el modo de confirmación Original, por lo que el motor de interfaz genera una confirmación de aplicación acepte única para cada mensaje después de validar el encabezado del mensaje y el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="cf544-114">In this tutorial, you will select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for each message after validating both the message header and body.</span></span> <span data-ttu-id="cf544-115">El motor compila la confirmación basándose en el esquema ACK_024_GLO_DEF, introduce "AA" en el campo MSA2 de la confirmación, entra en la entidad de destino en MSH3 y entra en la entidad de origen en MSH5.</span><span class="sxs-lookup"><span data-stu-id="cf544-115">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5.  <span data-ttu-id="cf544-116">El motor de interfaz coloca contenedores MLLP alrededor de cada confirmación, y las rutas de las confirmaciones al origen de terceros a través de un adaptador de envío MLLP configurado para procesar confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="cf544-116">The Interface Engine places MLLP wrappers around each acknowledgment, and routes the acknowledgments to the source party through an MLLP send adapter set up to process acknowledgments.</span></span>  
  
6.  <span data-ttu-id="cf544-117">El motor de interfaz incluye contenedores MLLP alrededor de cada mensaje y rutas configurado para procesar mensajes de confirmación no de puerto de envío de cada mensaje de forma individual para un MLLP.</span><span class="sxs-lookup"><span data-stu-id="cf544-117">The Interface Engine places MLLP wrappers around each message, and routes each message individually to an MLLP send port set up to process non-acknowledgment messages.</span></span>  
  
7.  <span data-ttu-id="cf544-118">BTAHL7 envía cada mensaje a través de otro puerto de envío MLLP en el destino especificado en el campo MSH5.</span><span class="sxs-lookup"><span data-stu-id="cf544-118">BTAHL7 sends each message through another MLLP send port to the destination specified in its MSH5 field.</span></span>  
  
8.  <span data-ttu-id="cf544-119">La entidad de destino que se envía a BTAHL7 una confirmación para cada mensaje que recibió de aceptación de aplicación.</span><span class="sxs-lookup"><span data-stu-id="cf544-119">The destination party sends to BTAHL7 an application-accept acknowledgment for each message that it received.</span></span>  
  
9. <span data-ttu-id="cf544-120">El motor de la interfaz recibe cada confirmación.</span><span class="sxs-lookup"><span data-stu-id="cf544-120">The Interface Engine receives each acknowledgment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf544-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cf544-121">In This Section</span></span>  
  
-   [<span data-ttu-id="cf544-122">Paso 1: Agregar encabezado y esquemas de confirmación</span><span class="sxs-lookup"><span data-stu-id="cf544-122">Step 1: Add Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="cf544-123">Paso 2: Agregar los esquemas comunes para v2.3.1</span><span class="sxs-lookup"><span data-stu-id="cf544-123">Step 2: Add Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="cf544-124">Paso 3: Agregar un esquema de desencadenador de eventos (mensaje)</span><span class="sxs-lookup"><span data-stu-id="cf544-124">Step 3: Add a Trigger Event (Message) Schema</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [<span data-ttu-id="cf544-125">Paso 4: Crear un puerto de recepción para aceptar el mensaje de lote</span><span class="sxs-lookup"><span data-stu-id="cf544-125">Step 4: Create a Receive Port for Accepting the Batch Message</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [<span data-ttu-id="cf544-126">Paso 5: Crear un puerto de envío para la entrega de mensajes</span><span class="sxs-lookup"><span data-stu-id="cf544-126">Step 5: Create a Send Port to Deliver Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [<span data-ttu-id="cf544-127">Paso 6: Crear un puerto de envío para entregar confirmaciones</span><span class="sxs-lookup"><span data-stu-id="cf544-127">Step 6: Create a Send Port to Deliver Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [<span data-ttu-id="cf544-128">Paso 7: Crear y configurar una entidad de origen</span><span class="sxs-lookup"><span data-stu-id="cf544-128">Step 7: Create and Configure a Source Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [<span data-ttu-id="cf544-129">Paso 8: Reinicie el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="cf544-129">Step 8: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="cf544-130">Paso 9: Compruebe el escenario fragmentados por lotes entrantes</span><span class="sxs-lookup"><span data-stu-id="cf544-130">Step 9: Verify the Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)