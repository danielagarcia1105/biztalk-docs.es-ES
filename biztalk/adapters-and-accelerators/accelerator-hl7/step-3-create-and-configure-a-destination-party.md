---
title: 'Paso 3: Crear y configurar una entidad de destino | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8746f115-9f69-4593-9943-9ccda45cd900
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34fb3ef45123817f747ab9aa956e961c5bb9a1c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-and-configure-a-destination-party"></a><span data-ttu-id="94f17-102">Paso 3: Crear y configurar una entidad de destino</span><span class="sxs-lookup"><span data-stu-id="94f17-102">Step 3: Create and Configure a Destination Party</span></span>
<span data-ttu-id="94f17-103">En este paso, crear y configurar una entidad de destino para el escenario de lote de crear.</span><span class="sxs-lookup"><span data-stu-id="94f17-103">In this step, you create and configure a destination party for the Create-Batch scenario.</span></span> <span data-ttu-id="94f17-104">También selecciona los mensajes que [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] lotes y el lote programa, tal como se define para esa entidad.</span><span class="sxs-lookup"><span data-stu-id="94f17-104">You also select the messages that [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] batches and the batch schedules, as defined for that party.</span></span> <span data-ttu-id="94f17-105">Puede programar la hora de envío de lote como una hora después de copiar los archivos en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="94f17-105">You schedule the batch send time as one hour after copying the files into the folder.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="94f17-106">los lotes de cualquier mensaje recibido posteriormente con una frecuencia de una hora.</span><span class="sxs-lookup"><span data-stu-id="94f17-106"> batches any messages received thereafter with a frequency of one hour.</span></span>  
  
### <a name="to-create-and-configure-a-destination-party"></a><span data-ttu-id="94f17-107">Para crear y configurar una entidad de destino</span><span class="sxs-lookup"><span data-stu-id="94f17-107">To create and configure a destination party</span></span>  
  
1.  <span data-ttu-id="94f17-108">En la consola de administración de BizTalk Server, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="94f17-108">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="94f17-109">En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **Tutorial_BatchDest**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94f17-109">In the Party Properties dialog box, in the **Name** box, type **Tutorial_BatchDest**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="94f17-110">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="94f17-110">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
4.  <span data-ttu-id="94f17-111">En el Explorador de configuración de BTAHL7, en la **partes** en el árbol de consola, haga clic en **Tutorial_BatchDest**.</span><span class="sxs-lookup"><span data-stu-id="94f17-111">In BTAHL7 Configuration Explorer, on the **Parties** tab in the console tree, click **Tutorial_BatchDest**.</span></span>  
  
5.  <span data-ttu-id="94f17-112">Haga clic en el **confirmación** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="94f17-112">Click the **Acknowledgment** tab in the Details pane.</span></span> <span data-ttu-id="94f17-113">Compruebe que la **tipo de confirmación** es **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="94f17-113">Verify that the **Acknowledgment type** is **None**.</span></span>  
  
6.  <span data-ttu-id="94f17-114">Haga clic en el **definición por lotes** ficha. En el **mensajes disponibles** panel, seleccione **BTAHL7Schemas.ADT_A03_231_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="94f17-114">Click the **Batch Definition** tab. In the **Available Messages** pane, select **BTAHL7Schemas.ADT_A03_231_GLO_DEF**.</span></span> <span data-ttu-id="94f17-115">Haga clic en el movimiento a la flecha derecha (**>>**) para agregar este esquema a **mensajes seleccionados**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="94f17-115">Click the Move to the right arrow (**>>**) to add this schema to **Selected Messages**, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="94f17-116">Haga clic en el **programación por lotes** ficha. En el **repita lote después de** sección, compruebe que **horas** está seleccionada y, a continuación, escriba **1** en el **horas** cuadro.</span><span class="sxs-lookup"><span data-stu-id="94f17-116">Click the **Batch Schedule** tab. In the **Repeat Batch After** section, verify that **Hours** is selected, and then type **1** in the **Hours** box.</span></span> <span data-ttu-id="94f17-117">En el **horas antes del primer lote** , escriba **1**y, a continuación, haga clic en **programación iniciar**.</span><span class="sxs-lookup"><span data-stu-id="94f17-117">In the **Hours before first batch** box, type **1**, and then click **Start Schedule**.</span></span>  
  
 <span data-ttu-id="94f17-118">Continúe con [paso 4: configurar la entidad de origen para el escenario de lote crear](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="94f17-118">Proceed to [Step 4: Configure the Source Party for the Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md).</span></span>