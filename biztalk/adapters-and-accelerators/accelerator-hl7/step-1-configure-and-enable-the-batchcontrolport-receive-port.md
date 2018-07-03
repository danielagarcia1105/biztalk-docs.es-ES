---
title: 'Paso 1: Configurar y puerto de recepción de habilitar la BatchControlPort | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be248a05-e740-497a-b112-8ba3a57b020b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fb11e0638a66fa7d22332d1cbca103a14490528
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988253"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a><span data-ttu-id="da2a8-102">Paso 1: Configurar y habilitar el BatchControlPort puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="da2a8-102">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>
<span data-ttu-id="da2a8-103">Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) programa de instalación crea un puerto de recepción, el control del lote de puerto, para controlar los mensajes que la orquestación del lote que se usa para iniciar, tiempo y detenga los lotes.</span><span class="sxs-lookup"><span data-stu-id="da2a8-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) setup creates a receive port, the batch control port, to handle the messages that the batch orchestration uses to start, stop, and time batches.</span></span> <span data-ttu-id="da2a8-104">Estos mensajes incluyen la activación de lotes, terminación de lotes y mensajes de temporizador de batch.</span><span class="sxs-lookup"><span data-stu-id="da2a8-104">These messages include the batch activation, batch termination, and batch timer messages.</span></span> <span data-ttu-id="da2a8-105">En este paso, configurará la canalización de recepción para el puerto de control de proceso por lotes y habilitar el puerto.</span><span class="sxs-lookup"><span data-stu-id="da2a8-105">In this step, you configure the receive pipeline for the batch control port, and enable the port.</span></span>  
  
### <a name="to-configure-and-enable-batchcontrolport"></a><span data-ttu-id="da2a8-106">Para configurar y habilitar BatchControlPort</span><span class="sxs-lookup"><span data-stu-id="da2a8-106">To configure and enable BatchControlPort</span></span>  
  
1. <span data-ttu-id="da2a8-107">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="da2a8-107">Start **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="da2a8-108">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1**.</span><span class="sxs-lookup"><span data-stu-id="da2a8-108">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="da2a8-109">Haga clic en **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="da2a8-109">Click **Receive Locations**.</span></span>  
  
3. <span data-ttu-id="da2a8-110">Haga clic en **BatchControlLocation**y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="da2a8-110">Right-click **BatchControlLocation**, and then click **Disable**.</span></span>  
  
4. <span data-ttu-id="da2a8-111">Haga clic en **BatchControlLocation**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="da2a8-111">Right-click **BatchControlLocation**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="da2a8-112">En el cuadro de diálogo Propiedades de ubicación de recepción para **canalización de recepción**, seleccione **BTAHL72XPipelines.BTAHL72XReceivePipeline**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da2a8-112">In the Receive Location Properties dialog box, for **Receive Pipeline**, select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.Click **OK**.</span></span>  
  
6. <span data-ttu-id="da2a8-113">En la consola de administración de BizTalk, haga clic en **BatchControlLocation**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="da2a8-113">In the BizTalk Administration Console, right-click **BatchControlLocation**, and then click **Enable**.</span></span>  
  
   <span data-ttu-id="da2a8-114">Continúe con [paso 2: habilitar la orquestación del lote](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="da2a8-114">Proceed to [Step 2: Enable the Batch Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).</span></span>