---
title: "Paso 1: Configurar la información de entidad para el lote en procesos por lotes el | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 982b17fe3826a0e5c5ee2a42030ba020b755ab70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a><span data-ttu-id="a6361-102">Paso 1: Configurar la información de entidad para el lote en / lote Out</span><span class="sxs-lookup"><span data-stu-id="a6361-102">Step 1: Configure Party Information for Batch In/Batch Out</span></span>
<span data-ttu-id="a6361-103">En este paso, desactivar la fragmentación del procesamiento por lotes para la entidad, lo que permite el lote en / escenario de lote.</span><span class="sxs-lookup"><span data-stu-id="a6361-103">In this step, you turn off fragmentation of batching for the party, enabling the Batch In/Batch Out scenario.</span></span> <span data-ttu-id="a6361-104">A continuación, reinicie [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para habilitar el cambio de configuración surta efecto.</span><span class="sxs-lookup"><span data-stu-id="a6361-104">You then restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to enable the configuration change to take effect.</span></span>  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a><span data-ttu-id="a6361-105">Para desactivar la fragmentación del procesamiento por lotes para la entidad</span><span class="sxs-lookup"><span data-stu-id="a6361-105">To turn off fragmentation of batching for the party</span></span>  
  
1.  <span data-ttu-id="a6361-106">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="a6361-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
2.  <span data-ttu-id="a6361-107">En el Explorador de configuración de BTAHL7, en la **partes** en el panel izquierdo, haga clic en **Tutorial_BatchSource**.</span><span class="sxs-lookup"><span data-stu-id="a6361-107">In BTAHL7 Configuration Explorer, on the **Parties** tab in the left-hand pane, click **Tutorial_BatchSource**.</span></span>  
  
3.  <span data-ttu-id="a6361-108">Haga clic en el **definición por lotes** ficha.</span><span class="sxs-lookup"><span data-stu-id="a6361-108">Click the **Batch Definition** tab.</span></span>  
  
4.  <span data-ttu-id="a6361-109">Seleccione **No** para **requerida fragmentación**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="a6361-109">Select **No** for **Fragmentation required**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="a6361-110">Asegúrese de que en **soporte técnico de intercambio recuperable requiere** lista desplegable **False** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a6361-110">Make sure that in **Recoverable Interchange Support Required** dropdown list **False** is selected.</span></span>  
  
 <span data-ttu-id="a6361-111">Continúe con [paso 2: modificar o crear el envío y puertos de recepción](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).</span><span class="sxs-lookup"><span data-stu-id="a6361-111">Proceed to [Step 2: Modify or Create the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).</span></span>