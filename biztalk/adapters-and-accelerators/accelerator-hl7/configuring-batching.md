---
title: Configurar el procesamiento por lotes | Documentos de Microsoft
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
ms.openlocfilehash: b9ab9ead01273e54826db670e7e6d6a2e9af6200
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204572"
---
# <a name="configuring-batching"></a><span data-ttu-id="c8612-102">Configurar el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="c8612-102">Configuring Batching</span></span>
<span data-ttu-id="c8612-103">Utiliza [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para crear el lote, el Explorador de configuración por lotes en / lote procesamiento por lotes y para seleccionar los esquemas disponibles para el procesamiento por lotes saliente.</span><span class="sxs-lookup"><span data-stu-id="c8612-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to create batch, batch in/batch out batching, and to select available schemas for outbound batching.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8612-104">Debe configurar a socios comerciales mediante el Explorador de BizTalk para poder configurar el procesamiento por lotes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c8612-104">You must configure trading partners using BizTalk Explorer before you can configure message batching.</span></span>  
  
 <span data-ttu-id="c8612-105">La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **definición por lotes** ficha.</span><span class="sxs-lookup"><span data-stu-id="c8612-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Definition** tab.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")  
  
 <span data-ttu-id="c8612-106">Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración y configurar el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="c8612-106">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and configure batching.</span></span>  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a><span data-ttu-id="c8612-107">Para habilitar el procesamiento por lotes de mensajes por lotes saliente (Crear lote)</span><span class="sxs-lookup"><span data-stu-id="c8612-107">To enable message batching for outbound batching (Create Batch)</span></span>  
  
1.  <span data-ttu-id="c8612-108">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c8612-108">In the **Start** menu, open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c8612-109">En la consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Aplicación 1**.</span><span class="sxs-lookup"><span data-stu-id="c8612-109">In the Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="c8612-110">Haga clic en **orquestaciones**, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c8612-110">Click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="c8612-111">En el cuadro de diálogo Propiedades de orquestación, haga clic en **enlaces** en el árbol de consola.</span><span class="sxs-lookup"><span data-stu-id="c8612-111">In the Orchestration Properties dialog box, click **Bindings** in the console tree.</span></span>  
  
5.  <span data-ttu-id="c8612-112">En el **enlaces** panel, seleccione un host apropiado para **Host**.</span><span class="sxs-lookup"><span data-stu-id="c8612-112">In the **Bindings** pane, select the appropriate host for **Host**.</span></span> <span data-ttu-id="c8612-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8612-113">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="c8612-114">Haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **dar de alta**.</span><span class="sxs-lookup"><span data-stu-id="c8612-114">Right-click **BatchOrchestration.Orchestration_1**, and then select **Enlist**.</span></span>  
  
7.  <span data-ttu-id="c8612-115">Haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="c8612-115">Right-click **BatchOrchestration.Orchestration_1**, and then select **Start**.</span></span>  
  
### <a name="to-run-btahl7-configuration-explorer"></a><span data-ttu-id="c8612-116">Para ejecutar el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="c8612-116">To run BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="c8612-117">En el **iniciar** menú Abrir **Acelerador de Microsoft BizTalk para HL7** y, a continuación, haga clic en **BTAHL7 configuración explorador**.</span><span class="sxs-lookup"><span data-stu-id="c8612-117">In the **Start** menu, open **Microsoft BizTalk Accelerator for HL7** , and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-configure-batching"></a><span data-ttu-id="c8612-118">Para configurar el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="c8612-118">To configure batching</span></span>  
  
-   <span data-ttu-id="c8612-119">En [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración, en el **Explorador de configuración de BTAHL7** cuadro de diálogo la **partes** ficha, seleccione la entidad que desea configurar, y, a continuación, en la **por lotes Definición de** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8612-119">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Definition** tab, do the following:</span></span>  
  
    |<span data-ttu-id="c8612-120">Use</span><span class="sxs-lookup"><span data-stu-id="c8612-120">Use this</span></span>|<span data-ttu-id="c8612-121">Para</span><span class="sxs-lookup"><span data-stu-id="c8612-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c8612-122">**Requerido fragmentación**</span><span class="sxs-lookup"><span data-stu-id="c8612-122">**Fragmentation required**</span></span>|<span data-ttu-id="c8612-123">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c8612-123">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="c8612-124">-   **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c8612-124">-   **Yes**.</span></span> <span data-ttu-id="c8612-125">Para habilitar la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="c8612-125">To enable fragmentation.</span></span><br /><span data-ttu-id="c8612-126">-   **Ya no**.</span><span class="sxs-lookup"><span data-stu-id="c8612-126">-   **No**.</span></span> <span data-ttu-id="c8612-127">Para deshabilitar la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="c8612-127">To disable fragmentation.</span></span> <span data-ttu-id="c8612-128">**Nota:** para una entidad nueva, **requerida fragmentación** tiene como valor predeterminado **No**.</span><span class="sxs-lookup"><span data-stu-id="c8612-128">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>|  
    |<span data-ttu-id="c8612-129">**Seleccionar los mensajes**</span><span class="sxs-lookup"><span data-stu-id="c8612-129">**Select Messages**</span></span>|<span data-ttu-id="c8612-130">Seleccione los tipos de mensaje que desea enviar como un lote a partir de la **mensajes disponibles** ventana y, a continuación, haga clic en el movimiento a la flecha derecha (**>>**).</span><span class="sxs-lookup"><span data-stu-id="c8612-130">Select the message types you want to send as a batch from the **Available Messages** window, and then click the Move to the right arrow (**>>**).</span></span>|  
    |<span data-ttu-id="c8612-131">**Seleccione las confirmaciones de mensaje**</span><span class="sxs-lookup"><span data-stu-id="c8612-131">**Select Message Acknowledgments**</span></span>|<span data-ttu-id="c8612-132">Seleccione los tipos de mensaje para el que desea que las confirmaciones para enviar como un lote a partir de la **confirmaciones de mensajes disponible** ventana y, a continuación, haga clic en el movimiento a la derecha (**>>**).</span><span class="sxs-lookup"><span data-stu-id="c8612-132">Select the message types for which you want the acknowledgments to send as a batch from the **Available Message Acks** window, and then click the Move to the right (**>>**).</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="c8612-133">Puede que no vea los esquemas que agregue a su en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proyecto mientras se encuentre en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración Explorer se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c8612-133">You may not see schemas that you add to your In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] project while In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer is running.</span></span> <span data-ttu-id="c8612-134">Para ver estos archivos, debe reiniciar en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="c8612-134">In order to view these files, you may need to restart In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8612-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8612-135">See Also</span></span>  
 [<span data-ttu-id="c8612-136">Programar el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="c8612-136">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)