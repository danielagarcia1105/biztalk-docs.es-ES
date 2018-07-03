---
title: 'Paso 1: Configurar la información de entidad para fuera de proceso por lotes en Batch | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eafe692cf86ccf3c6fbe0713c1e621a99a601d5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974925"
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a><span data-ttu-id="3f16f-102">Paso 1: Configurar la información de entidad para el lote o salida</span><span class="sxs-lookup"><span data-stu-id="3f16f-102">Step 1: Configure Party Information for Batch In/Batch Out</span></span>
<span data-ttu-id="3f16f-103">En este paso, desactivar la fragmentación del procesamiento por lotes para la entidad, lo que permite el lote en / escenario de lote.</span><span class="sxs-lookup"><span data-stu-id="3f16f-103">In this step, you turn off fragmentation of batching for the party, enabling the Batch In/Batch Out scenario.</span></span> <span data-ttu-id="3f16f-104">A continuación, reinicie [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para habilitar el cambio de configuración surta efecto.</span><span class="sxs-lookup"><span data-stu-id="3f16f-104">You then restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to enable the configuration change to take effect.</span></span>  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a><span data-ttu-id="3f16f-105">Para desactivar la fragmentación del procesamiento por lotes para la entidad</span><span class="sxs-lookup"><span data-stu-id="3f16f-105">To turn off fragmentation of batching for the party</span></span>  
  
1. <span data-ttu-id="3f16f-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en **Explorador de configuración de BTAHL7**.</span><span class="sxs-lookup"><span data-stu-id="3f16f-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
2. <span data-ttu-id="3f16f-107">En el Explorador de configuración de BTAHL7, en el **partes** , haga clic en el panel izquierdo **Tutorial_BatchSource**.</span><span class="sxs-lookup"><span data-stu-id="3f16f-107">In BTAHL7 Configuration Explorer, on the **Parties** tab in the left-hand pane, click **Tutorial_BatchSource**.</span></span>  
  
3. <span data-ttu-id="3f16f-108">Haga clic en el **definición de lote** ficha.</span><span class="sxs-lookup"><span data-stu-id="3f16f-108">Click the **Batch Definition** tab.</span></span>  
  
4. <span data-ttu-id="3f16f-109">Seleccione **No** para **requerida fragmentación**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f16f-109">Select **No** for **Fragmentation required**, and then click **Save**.</span></span>  
  
5. <span data-ttu-id="3f16f-110">Asegúrese de que en **soporte técnico de intercambio recuperable requiere** lista desplegable **False** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f16f-110">Make sure that in **Recoverable Interchange Support Required** dropdown list **False** is selected.</span></span>  
  
   <span data-ttu-id="3f16f-111">Continúe con [paso 2: modificar o crear el envío y recepción](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).</span><span class="sxs-lookup"><span data-stu-id="3f16f-111">Proceed to [Step 2: Modify or Create the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).</span></span>