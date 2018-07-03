---
title: 'Paso 4: Configurar la entidad de origen para el escenario de creación de lote | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b06b6545-4c2e-4a56-9feb-bd3f9574d4d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbb4e172c88c179ea53f1e48d1e08dcb63458607
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999829"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a><span data-ttu-id="d8a17-102">Paso 4: Configurar la entidad de origen para el escenario de creación de lote</span><span class="sxs-lookup"><span data-stu-id="d8a17-102">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>
<span data-ttu-id="d8a17-103">En este paso, configure la entidad de origen para el escenario de lote de crear.</span><span class="sxs-lookup"><span data-stu-id="d8a17-103">In this step, you configure the source party for the Create-Batch scenario.</span></span> <span data-ttu-id="d8a17-104">También selecciona las confirmaciones que el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) procesará por lotes los, tal como se define para esta entidad.</span><span class="sxs-lookup"><span data-stu-id="d8a17-104">You also select the acknowledgments that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) will batch, as defined for this party.</span></span> <span data-ttu-id="d8a17-105">Establecer la programación para el lote de confirmación que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] creará el lote después de que el número de mensajes llega a 2.</span><span class="sxs-lookup"><span data-stu-id="d8a17-105">You set the scheduling for the acknowledgment batch such that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will create the batch after the message count reaches 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8a17-106">En este escenario, se usa la misma entidad de origen que creó en [paso 7: crear y configurar una entidad de origen](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md) parte 1 de este tutorial (el fragmentado de entrada por lotes escenario).</span><span class="sxs-lookup"><span data-stu-id="d8a17-106">In this scenario, you use the same source party that you created in [Step 7: Create and Configure a Source Party](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md) of Part 1 of this tutorial (the Fragmented Inbound Batch Scenario).</span></span>  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a><span data-ttu-id="d8a17-107">Para configurar la entidad de origen para el escenario de creación de lote</span><span class="sxs-lookup"><span data-stu-id="d8a17-107">To configure the source party for the Create-Batch scenario</span></span>  
  
1. <span data-ttu-id="d8a17-108">En el Explorador de configuración de BTAHL7, en el **partes** , haga clic en el árbol de consola **Tutorial_BatchSource**.</span><span class="sxs-lookup"><span data-stu-id="d8a17-108">In BTAHL7 Configuration Explorer, on the **Parties** tab in the console tree, click **Tutorial_BatchSource**.</span></span>  
  
2. <span data-ttu-id="d8a17-109">Haga clic en el **confirmación** ficha en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="d8a17-109">Click the **Acknowledgment** tab in the Details pane.</span></span> <span data-ttu-id="d8a17-110">Compruebe que la **tipo de confirmación** es **OriginalMode**.</span><span class="sxs-lookup"><span data-stu-id="d8a17-110">Verify that the **Acknowledgment type** is **OriginalMode**.</span></span>  
  
3. <span data-ttu-id="d8a17-111">Haga clic en el **definición de lote** ficha. En **confirmaciones de mensajes disponibles**, haga clic en **BTAHL7Schemas.ADT_A03_231_GLO_DEF**, haga clic en la migración a la flecha derecha (**>>**) para agregar este esquema a  **Selecciona las confirmaciones de mensajes**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="d8a17-111">Click the **Batch Definition** tab. Under **Available Message Acks**, click **BTAHL7Schemas.ADT_A03_231_GLO_DEF**, click the Move to the right arrow (**>>**) to add this schema to **Selected Message Acks**, and then click **Save**.</span></span>  
  
4. <span data-ttu-id="d8a17-112">Haga clic en el **programación por lotes** ficha. En el **Repita el proceso por lotes después** sección, seleccione **mensajes**y, a continuación, escriba **2** en el **mensajes** cuadro.</span><span class="sxs-lookup"><span data-stu-id="d8a17-112">Click the **Batch Schedule** tab. In the **Repeat Batch After** section, select **Messages**, and then type **2** in the **Messages** box.</span></span>  
  
5. <span data-ttu-id="d8a17-113">Haga clic en **iniciar programación**.</span><span class="sxs-lookup"><span data-stu-id="d8a17-113">Click **Start Schedule**.</span></span>  
  
   <span data-ttu-id="d8a17-114">Continúe con [paso 5: crear el puerto de envío para el lote de mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md).</span><span class="sxs-lookup"><span data-stu-id="d8a17-114">Proceed to [Step 5: Create the Send Port for the Message Batch](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md).</span></span>