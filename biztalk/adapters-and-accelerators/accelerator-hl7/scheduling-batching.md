---
title: Programar el procesamiento por lotes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790cf5cb853da211d5e8928f398ecc1a2b3fe0ba
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961538"
---
# <a name="scheduling-batching"></a><span data-ttu-id="1243f-102">Programar el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="1243f-102">Scheduling Batching</span></span>
<span data-ttu-id="1243f-103">Usa [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Explorador de configuración para activar, solicitar o finalizar un lote saliente.</span><span class="sxs-lookup"><span data-stu-id="1243f-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="1243f-104">Activar un lote saliente consta de dos pasos: configurar basado en tiempo o mensaje de recuento de criterios y, a continuación, iniciar la orquestación de procesamiento por lotes saliente.</span><span class="sxs-lookup"><span data-stu-id="1243f-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="1243f-105">La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **programación por lotes** ficha.</span><span class="sxs-lookup"><span data-stu-id="1243f-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Schedule** tab.</span></span>  
  
 <span data-ttu-id="1243f-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")</span><span class="sxs-lookup"><span data-stu-id="1243f-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")</span></span>  
  
 <span data-ttu-id="1243f-107">Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración y la programación de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="1243f-107">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and schedule batching.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="1243f-108">Para abrir el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="1243f-108">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="1243f-109">Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="1243f-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-schedule-message-batching"></a><span data-ttu-id="1243f-110">Para programar el procesamiento por lotes de mensajes</span><span class="sxs-lookup"><span data-stu-id="1243f-110">To schedule message batching</span></span>  
  
1.  <span data-ttu-id="1243f-111">Abra el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="1243f-111">Open BTAHL7 Configuration Explorer.</span></span>  
  
2.  <span data-ttu-id="1243f-112">En el Explorador de configuración de BTAHL7, en la **Explorador de configuración de BTAHL7** cuadro de diálogo la **partes** ficha, seleccione la entidad que desea configurar, y, a continuación, en la **programación por lotes** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1243f-112">In BTAHL7 Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Schedule** tab, do the following:</span></span>  
  
    |<span data-ttu-id="1243f-113">Use</span><span class="sxs-lookup"><span data-stu-id="1243f-113">Use this</span></span>|<span data-ttu-id="1243f-114">Para</span><span class="sxs-lookup"><span data-stu-id="1243f-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1243f-115">**Horas antes de que en primer lugar por lotes**</span><span class="sxs-lookup"><span data-stu-id="1243f-115">**Hours before first batch**</span></span>|<span data-ttu-id="1243f-116">Escriba el número de horas antes de que el primer lote consiste en iniciar.</span><span class="sxs-lookup"><span data-stu-id="1243f-116">Type the number of hours before the first batch is to start.</span></span>|  
    |<span data-ttu-id="1243f-117">**Repita el proceso por lotes después de**</span><span class="sxs-lookup"><span data-stu-id="1243f-117">**Repeat Batch After**</span></span>|<span data-ttu-id="1243f-118">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1243f-118">Select one of the following:</span></span><br /><br /> <span data-ttu-id="1243f-119">-   **Horas**.</span><span class="sxs-lookup"><span data-stu-id="1243f-119">-   **Hours**.</span></span> <span data-ttu-id="1243f-120">Escriba el número de horas que se repita el proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="1243f-120">Type the number of hours to repeat the batch process.</span></span><br /><span data-ttu-id="1243f-121">-   **Mensajes**.</span><span class="sxs-lookup"><span data-stu-id="1243f-121">-   **Messages**.</span></span> <span data-ttu-id="1243f-122">Escriba el número de mensajes que van a procesar antes de que el proceso por lotes siguiente comienza.</span><span class="sxs-lookup"><span data-stu-id="1243f-122">Type the number of messages you want to process before the next batch process begins.</span></span>|  
    |<span data-ttu-id="1243f-123">**Control de proceso por lotes**</span><span class="sxs-lookup"><span data-stu-id="1243f-123">**Batch Control**</span></span>|<span data-ttu-id="1243f-124">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1243f-124">Select one of the following:</span></span><br /><br /> <span data-ttu-id="1243f-125">-   **Iniciar la programación**: seleccione esta opción para iniciar el programa por lotes.</span><span class="sxs-lookup"><span data-stu-id="1243f-125">-   **Start Schedule**: Select to start the batch schedule.</span></span><br /><span data-ttu-id="1243f-126">-   **Enviar ahora**: seleccione esta opción para iniciar el lote se procesará inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="1243f-126">-   **Send Now**: Select to start the batch process immediately.</span></span><br /><span data-ttu-id="1243f-127">-   **Detener la programación**: seleccione esta opción para detener la programación por lotes actual.</span><span class="sxs-lookup"><span data-stu-id="1243f-127">-   **Stop Schedule**: Select to stop the current batch schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1243f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1243f-128">See Also</span></span>  
 [<span data-ttu-id="1243f-129">Configuración de confirmaciones de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="1243f-129">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)