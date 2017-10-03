---
title: "Paso 1: Configurar y habilitar el BatchControlPort el puerto de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be248a05-e740-497a-b112-8ba3a57b020b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d50289924062268db078844f2b3d2eaaccda23a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a><span data-ttu-id="2f00e-102">Paso 1: Configurar y habilitar el BatchControlPort el puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="2f00e-102">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="2f00e-103">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) el programa de instalación crea un puerto de recepción, el puerto el control de proceso por lotes, para controlar los mensajes que la orquestación del lote que se usa para iniciar, lotes de detención y el tiempo.</span><span class="sxs-lookup"><span data-stu-id="2f00e-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) setup creates a receive port, the batch control port, to handle the messages that the batch orchestration uses to start, stop, and time batches.</span></span> <span data-ttu-id="2f00e-104">Estos mensajes incluyen la activación de lotes, terminación de lotes y mensajes de temporizador de lote.</span><span class="sxs-lookup"><span data-stu-id="2f00e-104">These messages include the batch activation, batch termination, and batch timer messages.</span></span> <span data-ttu-id="2f00e-105">En este paso, puede configura la canalización de recepción para el puerto de control de lote y habilitar el puerto.</span><span class="sxs-lookup"><span data-stu-id="2f00e-105">In this step, you configure the receive pipeline for the batch control port, and enable the port.</span></span>  
  
### <a name="to-configure-and-enable-batchcontrolport"></a><span data-ttu-id="2f00e-106">Para configurar y habilitar BatchControlPort</span><span class="sxs-lookup"><span data-stu-id="2f00e-106">To configure and enable BatchControlPort</span></span>  
  
1.  <span data-ttu-id="2f00e-107">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2f00e-107">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2f00e-108">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1**.</span><span class="sxs-lookup"><span data-stu-id="2f00e-108">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="2f00e-109">Haga clic en **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="2f00e-109">Click **Receive Locations**.</span></span>  
  
3.  <span data-ttu-id="2f00e-110">Haga clic en **BatchControlLocation**y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="2f00e-110">Right-click **BatchControlLocation**, and then click **Disable**.</span></span>  
  
4.  <span data-ttu-id="2f00e-111">Haga clic en **BatchControlLocation**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2f00e-111">Right-click **BatchControlLocation**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="2f00e-112">En el cuadro de diálogo Propiedades de la ubicación de recepción, para **canalización de recepción**, seleccione **BTAHL72XPipelines.BTAHL72XReceivePipeline**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2f00e-112">In the Receive Location Properties dialog box, for **Receive Pipeline**, select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.Click **OK**.</span></span>  
  
6.  <span data-ttu-id="2f00e-113">En la consola de administración de BizTalk, haga clic en **BatchControlLocation**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="2f00e-113">In the BizTalk Administration Console, right-click **BatchControlLocation**, and then click **Enable**.</span></span>  
  
 <span data-ttu-id="2f00e-114">Continúe con [paso 2: habilitar la orquestación del lote](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="2f00e-114">Proceed to [Step 2: Enable the Batch Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).</span></span>