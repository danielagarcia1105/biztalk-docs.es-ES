---
title: "Pestaña de entidades en el Acelerador para HL7 en BizTalk Server | Documentos de Microsoft"
description: "Use el Explorador de configuración de BTAHL7 para ver entidades existentes y configurar confirmaciones de BizTalk Server"
ms.custom: 
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e01052c8-25c5-4736-8403-33f16fbd3fb7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d8572da051d046d46b6e895f11f07d3f9d9771c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="parties-in-btahl7-configuration-explorer"></a><span data-ttu-id="72fa2-103">Partes en el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="72fa2-103">Parties in BTAHL7 Configuration Explorer</span></span>
<span data-ttu-id="72fa2-104">Usa el **partes** ficha para ver las partes disponibles y especificar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración para una entidad determinada que elija y para configurar las propiedades para las confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="72fa2-104">You use the **Parties** tab to view the available parties and specify [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration for a particular party that you choose, and to configure properties for acknowledgments.</span></span> 

## <a name="parties-ui-explained"></a><span data-ttu-id="72fa2-105">Explican las partes de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="72fa2-105">Parties UI explained</span></span>
<span data-ttu-id="72fa2-106">El **partes** pestaña contiene un panel izquierdo y derecho.</span><span class="sxs-lookup"><span data-stu-id="72fa2-106">The **Parties** tab contains both a left and right pane.</span></span> <span data-ttu-id="72fa2-107">Las entidades disponibles aparecen en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="72fa2-107">The available parties appear in the left pane.</span></span> <span data-ttu-id="72fa2-108">El panel derecho contiene las siguientes pestañas para la entidad seleccionada:</span><span class="sxs-lookup"><span data-stu-id="72fa2-108">The right pane contains the following tabs for the selected party:</span></span>  
  
-   <span data-ttu-id="72fa2-109">**Alias de entidad**.</span><span class="sxs-lookup"><span data-stu-id="72fa2-109">**Party Aliases**.</span></span> <span data-ttu-id="72fa2-110">Utilice esta ficha para ver información acerca de la entidad que ha seleccionado en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="72fa2-110">Use this tab to view information about the party you have selected from the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72fa2-111">Utilice el Explorador de BizTalk para crear entidades.</span><span class="sxs-lookup"><span data-stu-id="72fa2-111">You use BizTalk Explorer to create parties.</span></span>  
  
-   <span data-ttu-id="72fa2-112">**Procesar por lotes definición**.</span><span class="sxs-lookup"><span data-stu-id="72fa2-112">**Batch Definition**.</span></span> <span data-ttu-id="72fa2-113">Use esta ficha para configurar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="72fa2-113">Use this tab to configure [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
-   <span data-ttu-id="72fa2-114">**Procesar por lotes programación**.</span><span class="sxs-lookup"><span data-stu-id="72fa2-114">**Batch Schedule**.</span></span> <span data-ttu-id="72fa2-115">Utilice esta ficha para activar los lotes salientes.</span><span class="sxs-lookup"><span data-stu-id="72fa2-115">Use this tab to activate outbound batches.</span></span>  
  
-   <span data-ttu-id="72fa2-116">**Confirmación**.</span><span class="sxs-lookup"><span data-stu-id="72fa2-116">**Acknowledgment**.</span></span> <span data-ttu-id="72fa2-117">Utilice esta ficha para especificar las propiedades de confirmaciones entrantes y generadas.</span><span class="sxs-lookup"><span data-stu-id="72fa2-117">Use this tab to specify the properties for inbound and generated acknowledgments.</span></span>  
  
-   <span data-ttu-id="72fa2-118">**Validación**.</span><span class="sxs-lookup"><span data-stu-id="72fa2-118">**Validation**.</span></span> <span data-ttu-id="72fa2-119">Use esta ficha para seleccionar las opciones de validación de mensajes para mensajes entrantes y generados.</span><span class="sxs-lookup"><span data-stu-id="72fa2-119">Use this tab to select the message validation options for inbound and generated messages.</span></span>  
  
-   <span data-ttu-id="72fa2-120">**Mapa de MSH**.</span><span class="sxs-lookup"><span data-stu-id="72fa2-120">**MSH Map**.</span></span> <span data-ttu-id="72fa2-121">Use esta ficha para habilitar las transformaciones de encabezado de mensaje para los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="72fa2-121">Use this tab to enable message header transformations for inbound messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72fa2-122">Debe configurar alias de entidad, las definiciones de lote, programaciones de lote e información de confirmación para todas las entidades comerciales.</span><span class="sxs-lookup"><span data-stu-id="72fa2-122">You must configure party aliases, batch definitions, batch schedules, and acknowledgment information for all trading parties.</span></span>  
    > 
    >  <span data-ttu-id="72fa2-123">Puede actualizar la lista de entidades presionando F5 o haciendo clic en la lista de entidades y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="72fa2-123">You can refresh the parties list by pressing F5, or by right-clicking the parties list, and select **Refresh**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="72fa2-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="72fa2-124">Next steps</span></span>  
  
-   [<span data-ttu-id="72fa2-125">Pestaña de alias de entidad</span><span class="sxs-lookup"><span data-stu-id="72fa2-125">Party Aliases Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/party-aliases-tab.md)  
  
-   [<span data-ttu-id="72fa2-126">Pestaña de la definición de proceso por lotes</span><span class="sxs-lookup"><span data-stu-id="72fa2-126">Batch Definition Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/batch-definition-tab.md)  
  
-   [<span data-ttu-id="72fa2-127">Ficha de programación por lotes</span><span class="sxs-lookup"><span data-stu-id="72fa2-127">Batch Schedule Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/batch-schedule-tab.md)  
  
-   [<span data-ttu-id="72fa2-128">Ficha de confirmación</span><span class="sxs-lookup"><span data-stu-id="72fa2-128">Acknowledgment Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-tab.md)  
  
-   [<span data-ttu-id="72fa2-129">Ficha validación</span><span class="sxs-lookup"><span data-stu-id="72fa2-129">Validation Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-tab.md)  
  
-   [<span data-ttu-id="72fa2-130">Pestaña asignación de MSH</span><span class="sxs-lookup"><span data-stu-id="72fa2-130">MSH Map Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-map-tab.md)