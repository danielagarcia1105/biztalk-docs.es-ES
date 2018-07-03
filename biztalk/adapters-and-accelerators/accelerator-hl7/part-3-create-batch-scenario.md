---
title: 'Parte 3: Escenario de creación de lote | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, creating
- creating, batching
ms.assetid: 02247186-5b21-4738-9110-f0ca0304f0fd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e487bfbe29ee2a34f2e50affa502d7f20592fe0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975957"
---
# <a name="part-3-create-batch-scenario"></a><span data-ttu-id="2ae9f-102">Parte 3: Escenario de creación de lote</span><span class="sxs-lookup"><span data-stu-id="2ae9f-102">Part 3: Create-Batch Scenario</span></span>
<span data-ttu-id="2ae9f-103">En esta parte del escenario, recibe dos mensajes entrantes, combinarlos en un mensaje por lotes y enviar el lote a un destino.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-103">In this part of the scenario, you receive two incoming messages, combine them into a batched message, and send the batch to a destination.</span></span> <span data-ttu-id="2ae9f-104">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) devuelve un lote de confirmación que contiene las dos confirmaciones que se generan para los mensajes desde el destino al origen.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-104">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) returns an acknowledgment batch containing the two acknowledgments generated for the messages from the destination to the source.</span></span> <span data-ttu-id="2ae9f-105">En la siguiente ilustración se muestra el flujo del proceso de esta parte del tutorial.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-105">The following figure shows the process flow of this part of the tutorial.</span></span>  
  
 <span data-ttu-id="2ae9f-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")</span><span class="sxs-lookup"><span data-stu-id="2ae9f-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")</span></span>  
  
 <span data-ttu-id="2ae9f-107">**Cómo fluyen los mensajes en el escenario de creación de lote**</span><span class="sxs-lookup"><span data-stu-id="2ae9f-107">**How messages flow in the Create-Batch scenario**</span></span>  
  
 <span data-ttu-id="2ae9f-108">Este escenario incluye el flujo de trabajo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ae9f-108">This scenario includes the following workflow:</span></span>  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="2ae9f-109"> intercepta todos los mensajes que cumplen la definición de lote en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-109"> traps all messages conforming to the batch definition in the MessageBox database.</span></span> <span data-ttu-id="2ae9f-110">Escriba esta definición en el **definición de lote** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-110">You enter this definition in the **Batch Definition** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="2ae9f-111">En este tutorial, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se interceptar y procesar por lotes todos los mensajes se envíen a Tutorial_BatchDest con un esquema de ADT ^ A03 y todas las confirmaciones para enviarse a Tutorial_BatchSource como resultado de ADT ^ A03 mensajes.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-111">In this tutorial, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will trap and batch all messages to be sent to Tutorial_BatchDest with a schema of ADT^A03, and all acknowledgments to be sent to Tutorial_BatchSource as a result of ADT^A03 messages.</span></span>  
  
- <span data-ttu-id="2ae9f-112">Cuando se produce la hora de envío por lotes programado, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía un mensaje de control de proceso por lotes que desencadena la transacción por lotes saliente.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-112">When the scheduled batch send time occurs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a batch control message that triggers the outbound batch transaction.</span></span> <span data-ttu-id="2ae9f-113">Defina la programación en el **programación por lotes** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-113">You define the schedule on the **Batch Schedule** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="2ae9f-114">También puede desencadenar el proceso haciendo clic en **enviar ahora** en la misma ficha.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-114">You can also trigger the process by clicking **Send Now** on the same tab.</span></span>  
  
- <span data-ttu-id="2ae9f-115">La orquestación del lote constituye el lote de mensajes fuera de los mensajes que se capturó en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-115">The batch orchestration forms the message batch out of the messages trapped in the MessageBox database.</span></span> <span data-ttu-id="2ae9f-116">La orquestación también ajusta el lote en un encabezado de archivo y finalizador y un encabezado de lote y el finalizador.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-116">The orchestration also wraps the batch in a file header and trailer, and a batch header and trailer.</span></span> <span data-ttu-id="2ae9f-117">Esta orquestación es nativo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orquestación agregada [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] programa de instalación para el conjunto de orquestaciones de BizTalk, por lo que aparece bajo el nodo orquestaciones en el Explorador de BizTalk o la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-117">This orchestration is a native [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orchestration added by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup to your set of BizTalk orchestrations, so it is listed under the Orchestrations node in BizTalk Explorer or the BizTalk Server Administration Console.</span></span>  
  
- <span data-ttu-id="2ae9f-118">Si se definen las confirmaciones para la entidad de origen (tal como están en este caso para Tutorial_BatchSource), BizTalk procesa por lotes las confirmaciones y los devuelve en un lote (en la carpeta \Tutorial_BatchACKDrop).</span><span class="sxs-lookup"><span data-stu-id="2ae9f-118">If acknowledgments are defined for the source party (as they are in this case for Tutorial_BatchSource), BizTalk batches the acknowledgments and returns them in a batch (to the \Tutorial_BatchACKDrop folder).</span></span> <span data-ttu-id="2ae9f-119">En este tutorial, las confirmaciones por lotes se envían tras un breve retraso.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-119">In this tutorial, the batched acknowledgments are sent after a short delay.</span></span>  
  
- <span data-ttu-id="2ae9f-120">La orquestación enruta el mensaje al puerto de envío (Tutorial_BatchDest), que envía el mensaje por lotes en el destino (en este caso, la carpeta \Tutorial_BatchMsgDrop en el disco duro).</span><span class="sxs-lookup"><span data-stu-id="2ae9f-120">The orchestration routes the message to the send port (Tutorial_BatchDest), which sends the batched message to the destination (in this case, the \Tutorial_BatchMsgDrop folder on your hard drive).</span></span> <span data-ttu-id="2ae9f-121">En este tutorial, se envían los mensajes por lotes después de una hora.</span><span class="sxs-lookup"><span data-stu-id="2ae9f-121">In this tutorial, the batched messages are sent after one hour.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ae9f-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ae9f-122">In This Section</span></span>  
  
-   [<span data-ttu-id="2ae9f-123">Paso 1: Configurar y habilitar el puerto de recepción BatchControlPort</span><span class="sxs-lookup"><span data-stu-id="2ae9f-123">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [<span data-ttu-id="2ae9f-124">Paso 2: Habilitar la orquestación del lote</span><span class="sxs-lookup"><span data-stu-id="2ae9f-124">Step 2: Enable the Batch Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [<span data-ttu-id="2ae9f-125">Paso 3: Crear y configurar una entidad de destino</span><span class="sxs-lookup"><span data-stu-id="2ae9f-125">Step 3: Create and Configure a Destination Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [<span data-ttu-id="2ae9f-126">Paso 4: Configurar la entidad de origen para el escenario de creación de lote</span><span class="sxs-lookup"><span data-stu-id="2ae9f-126">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [<span data-ttu-id="2ae9f-127">Paso 5: Crear el puerto de envío para el lote de mensajes</span><span class="sxs-lookup"><span data-stu-id="2ae9f-127">Step 5: Create the Send Port for the Message Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [<span data-ttu-id="2ae9f-128">Paso 6: Crear el puerto de envío para el lote de confirmaciones</span><span class="sxs-lookup"><span data-stu-id="2ae9f-128">Step 6: Create the Send Port for the Acknowledgment Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [<span data-ttu-id="2ae9f-129">Paso 7: Iniciar la orquestación y reiniciar BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2ae9f-129">Step 7: Start the Orchestration and Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="2ae9f-130">Paso 8: Probar el escenario de creación de lote</span><span class="sxs-lookup"><span data-stu-id="2ae9f-130">Step 8: Test the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)