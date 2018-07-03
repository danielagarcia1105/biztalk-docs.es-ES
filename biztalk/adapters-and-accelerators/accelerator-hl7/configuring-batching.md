---
title: Configuración de procesamiento por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, configuring
- configuring, batching
ms.assetid: 33c72d5e-31dd-44a8-8418-1faab3239e8e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ea79c4b96ac54e6b2d1eed281b60a261ca5cc1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976333"
---
# <a name="configuring-batching"></a><span data-ttu-id="5c957-102">Configuración de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="5c957-102">Configuring Batching</span></span>
<span data-ttu-id="5c957-103">Usa [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para crear el lote, el Explorador de configuración por lotes en / por lotes de procesamiento por lotes y para seleccionar los esquemas disponibles para el procesamiento por lotes saliente.</span><span class="sxs-lookup"><span data-stu-id="5c957-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to create batch, batch in/batch out batching, and to select available schemas for outbound batching.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c957-104">Debe configurar a socios comerciales mediante el Explorador de BizTalk antes de configurar el procesamiento por lotes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5c957-104">You must configure trading partners using BizTalk Explorer before you can configure message batching.</span></span>  
  
 <span data-ttu-id="5c957-105">La siguiente ilustración muestra el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración Explorer **definición de lote** ficha.</span><span class="sxs-lookup"><span data-stu-id="5c957-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Definition** tab.</span></span>  
  
 <span data-ttu-id="5c957-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")</span><span class="sxs-lookup"><span data-stu-id="5c957-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")</span></span>  
  
 <span data-ttu-id="5c957-107">Use los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración y configurar el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="5c957-107">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and configure batching.</span></span>  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a><span data-ttu-id="5c957-108">Para habilitar el procesamiento por lotes de mensajes por lotes saliente (creación de lote)</span><span class="sxs-lookup"><span data-stu-id="5c957-108">To enable message batching for outbound batching (Create Batch)</span></span>  
  
1.  <span data-ttu-id="5c957-109">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="5c957-109">In the **Start** menu, open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5c957-110">En la consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Aplicación 1**.</span><span class="sxs-lookup"><span data-stu-id="5c957-110">In the Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="5c957-111">Haga clic en **orquestaciones**, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5c957-111">Click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="5c957-112">En el cuadro de diálogo Propiedades de orquestación, haga clic en **enlaces** en el árbol de consola.</span><span class="sxs-lookup"><span data-stu-id="5c957-112">In the Orchestration Properties dialog box, click **Bindings** in the console tree.</span></span>  
  
5.  <span data-ttu-id="5c957-113">En el **enlaces** panel, seleccione el host adecuado para **Host**.</span><span class="sxs-lookup"><span data-stu-id="5c957-113">In the **Bindings** pane, select the appropriate host for **Host**.</span></span> <span data-ttu-id="5c957-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c957-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="5c957-115">Haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **Enlist**.</span><span class="sxs-lookup"><span data-stu-id="5c957-115">Right-click **BatchOrchestration.Orchestration_1**, and then select **Enlist**.</span></span>  
  
7.  <span data-ttu-id="5c957-116">Haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="5c957-116">Right-click **BatchOrchestration.Orchestration_1**, and then select **Start**.</span></span>  
  
### <a name="to-run-btahl7-configuration-explorer"></a><span data-ttu-id="5c957-117">Para ejecutar el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="5c957-117">To run BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="5c957-118">En el **iniciar** menú Abrir **Acelerador de Microsoft BizTalk para HL7** y, a continuación, haga clic en **Explorador de configuración de BTAHL7**.</span><span class="sxs-lookup"><span data-stu-id="5c957-118">In the **Start** menu, open **Microsoft BizTalk Accelerator for HL7** , and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-configure-batching"></a><span data-ttu-id="5c957-119">Para configurar el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="5c957-119">To configure batching</span></span>  
  
- <span data-ttu-id="5c957-120">En [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración, en el **Explorador de configuración de BTAHL7** cuadro de diálogo el **partes** pestaña, seleccione la entidad que desea configurar, y, a continuación, en el **por lotes Definición** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c957-120">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Definition** tab, do the following:</span></span>  
  
  |<span data-ttu-id="5c957-121">Use</span><span class="sxs-lookup"><span data-stu-id="5c957-121">Use this</span></span>|<span data-ttu-id="5c957-122">Para</span><span class="sxs-lookup"><span data-stu-id="5c957-122">To do this</span></span>|  
  |--------------|----------------|  
  |<span data-ttu-id="5c957-123">**Fragmentación necesaria**</span><span class="sxs-lookup"><span data-stu-id="5c957-123">**Fragmentation required**</span></span>|<span data-ttu-id="5c957-124">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5c957-124">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="5c957-125">-   **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5c957-125">-   **Yes**.</span></span> <span data-ttu-id="5c957-126">Para habilitar la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="5c957-126">To enable fragmentation.</span></span><br /><span data-ttu-id="5c957-127">-   **No**.</span><span class="sxs-lookup"><span data-stu-id="5c957-127">-   **No**.</span></span> <span data-ttu-id="5c957-128">Para deshabilitar la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="5c957-128">To disable fragmentation.</span></span> <span data-ttu-id="5c957-129">**Nota:** para una entidad nueva, **requerida fragmentación** el valor predeterminado es **No**.</span><span class="sxs-lookup"><span data-stu-id="5c957-129">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>|  
  |<span data-ttu-id="5c957-130">**Seleccionar los mensajes**</span><span class="sxs-lookup"><span data-stu-id="5c957-130">**Select Messages**</span></span>|<span data-ttu-id="5c957-131">Seleccione los tipos de mensaje que desea enviar como un lote desde el **mensajes disponibles** ventana y, a continuación, haga clic en la migración a la flecha derecha (**>>**).</span><span class="sxs-lookup"><span data-stu-id="5c957-131">Select the message types you want to send as a batch from the **Available Messages** window, and then click the Move to the right arrow (**>>**).</span></span>|  
  |<span data-ttu-id="5c957-132">**Seleccione las confirmaciones de mensajes**</span><span class="sxs-lookup"><span data-stu-id="5c957-132">**Select Message Acknowledgments**</span></span>|<span data-ttu-id="5c957-133">Seleccione los tipos de mensaje para el que desea que las confirmaciones que se envían como un lote a partir del **confirmaciones de mensajes disponibles** ventana y, a continuación, haga clic en el traslado a la derecha (**>>**).</span><span class="sxs-lookup"><span data-stu-id="5c957-133">Select the message types for which you want the acknowledgments to send as a batch from the **Available Message Acks** window, and then click the Move to the right (**>>**).</span></span>|  
  
  > [!NOTE]
  >  <span data-ttu-id="5c957-134">Puede que no vea los esquemas que agregue a su en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proyecto mientras se encuentre en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se está ejecutando el Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="5c957-134">You may not see schemas that you add to your In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] project while In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer is running.</span></span> <span data-ttu-id="5c957-135">Con el fin de ver estos archivos, es posible que deba reiniciar en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="5c957-135">In order to view these files, you may need to restart In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c957-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c957-136">See Also</span></span>  
 [<span data-ttu-id="5c957-137">Programación del procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="5c957-137">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)