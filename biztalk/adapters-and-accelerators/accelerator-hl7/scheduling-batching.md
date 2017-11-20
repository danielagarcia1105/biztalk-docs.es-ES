---
title: Programar el procesamiento por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08337171897a4a78e605054e9126e8c8238d5fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scheduling-batching"></a><span data-ttu-id="d5604-102">Programar el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="d5604-102">Scheduling Batching</span></span>
<span data-ttu-id="d5604-103">Usa [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Explorador de configuración para activar, solicitar o finalizar un lote saliente.</span><span class="sxs-lookup"><span data-stu-id="d5604-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="d5604-104">Activar un lote saliente consta de dos pasos: configurar basado en tiempo o mensaje de recuento de criterios y, a continuación, iniciar la orquestación de procesamiento por lotes saliente.</span><span class="sxs-lookup"><span data-stu-id="d5604-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="d5604-105">La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **programación por lotes** ficha.</span><span class="sxs-lookup"><span data-stu-id="d5604-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Schedule** tab.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")  
  
 <span data-ttu-id="d5604-106">Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración y la programación de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="d5604-106">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and schedule batching.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="d5604-107">Para abrir el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="d5604-107">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="d5604-108">Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="d5604-108">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-schedule-message-batching"></a><span data-ttu-id="d5604-109">Para programar el procesamiento por lotes de mensajes</span><span class="sxs-lookup"><span data-stu-id="d5604-109">To schedule message batching</span></span>  
  
1.  <span data-ttu-id="d5604-110">Abra el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="d5604-110">Open BTAHL7 Configuration Explorer.</span></span>  
  
2.  <span data-ttu-id="d5604-111">En el Explorador de configuración de BTAHL7, en la **Explorador de configuración de BTAHL7** cuadro de diálogo la **partes** ficha, seleccione la entidad que desea configurar, y, a continuación, en la **programación por lotes** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5604-111">In BTAHL7 Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Schedule** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d5604-112">Use</span><span class="sxs-lookup"><span data-stu-id="d5604-112">Use this</span></span>|<span data-ttu-id="d5604-113">Para</span><span class="sxs-lookup"><span data-stu-id="d5604-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d5604-114">**Horas antes de que en primer lugar por lotes**</span><span class="sxs-lookup"><span data-stu-id="d5604-114">**Hours before first batch**</span></span>|<span data-ttu-id="d5604-115">Escriba el número de horas antes de que el primer lote consiste en iniciar.</span><span class="sxs-lookup"><span data-stu-id="d5604-115">Type the number of hours before the first batch is to start.</span></span>|  
    |<span data-ttu-id="d5604-116">**Repita el proceso por lotes después de**</span><span class="sxs-lookup"><span data-stu-id="d5604-116">**Repeat Batch After**</span></span>|<span data-ttu-id="d5604-117">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5604-117">Select one of the following:</span></span><br /><br /> <span data-ttu-id="d5604-118">-   **Horas**.</span><span class="sxs-lookup"><span data-stu-id="d5604-118">-   **Hours**.</span></span> <span data-ttu-id="d5604-119">Escriba el número de horas que se repita el proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="d5604-119">Type the number of hours to repeat the batch process.</span></span><br /><span data-ttu-id="d5604-120">-   **Mensajes**.</span><span class="sxs-lookup"><span data-stu-id="d5604-120">-   **Messages**.</span></span> <span data-ttu-id="d5604-121">Escriba el número de mensajes que van a procesar antes de que el proceso por lotes siguiente comienza.</span><span class="sxs-lookup"><span data-stu-id="d5604-121">Type the number of messages you want to process before the next batch process begins.</span></span>|  
    |<span data-ttu-id="d5604-122">**Control de proceso por lotes**</span><span class="sxs-lookup"><span data-stu-id="d5604-122">**Batch Control**</span></span>|<span data-ttu-id="d5604-123">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5604-123">Select one of the following:</span></span><br /><br /> <span data-ttu-id="d5604-124">-   **Iniciar la programación**: seleccione esta opción para iniciar el programa por lotes.</span><span class="sxs-lookup"><span data-stu-id="d5604-124">-   **Start Schedule**: Select to start the batch schedule.</span></span><br /><span data-ttu-id="d5604-125">-   **Enviar ahora**: seleccione esta opción para iniciar el lote se procesará inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="d5604-125">-   **Send Now**: Select to start the batch process immediately.</span></span><br /><span data-ttu-id="d5604-126">-   **Detener la programación**: seleccione esta opción para detener la programación por lotes actual.</span><span class="sxs-lookup"><span data-stu-id="d5604-126">-   **Stop Schedule**: Select to stop the current batch schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5604-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5604-127">See Also</span></span>  
 [<span data-ttu-id="d5604-128">Configurar confirmaciones de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="d5604-128">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)