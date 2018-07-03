---
title: Ficha partes en el Acelerador de HL7 en BizTalk Server | Microsoft Docs
description: Utilice el Explorador de configuración de BTAHL7 para ver las entidades existentes y configurar las confirmaciones en BizTalk Server
ms.custom: ''
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e01052c8-25c5-4736-8403-33f16fbd3fb7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b048cccdcc46f4713967003c81671e062420377
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976317"
---
# <a name="parties-in-btahl7-configuration-explorer"></a><span data-ttu-id="02b11-103">Partes en el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="02b11-103">Parties in BTAHL7 Configuration Explorer</span></span>
<span data-ttu-id="02b11-104">Usa el **partes** pestaña para ver las partes disponibles y especificar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración para una entidad determinada que elija y para configurar las propiedades de las confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="02b11-104">You use the **Parties** tab to view the available parties and specify [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration for a particular party that you choose, and to configure properties for acknowledgments.</span></span> 

## <a name="parties-ui-explained"></a><span data-ttu-id="02b11-105">Explican las partes de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="02b11-105">Parties UI explained</span></span>
<span data-ttu-id="02b11-106">El **partes** ficha contiene el panel izquierdo y derecho.</span><span class="sxs-lookup"><span data-stu-id="02b11-106">The **Parties** tab contains both a left and right pane.</span></span> <span data-ttu-id="02b11-107">Las partes disponibles aparecen en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="02b11-107">The available parties appear in the left pane.</span></span> <span data-ttu-id="02b11-108">El panel derecho contiene las siguientes pestañas para la entidad seleccionada:</span><span class="sxs-lookup"><span data-stu-id="02b11-108">The right pane contains the following tabs for the selected party:</span></span>  
  
- <span data-ttu-id="02b11-109">**Alias de entidad**.</span><span class="sxs-lookup"><span data-stu-id="02b11-109">**Party Aliases**.</span></span> <span data-ttu-id="02b11-110">Utilice esta pestaña para ver información acerca de la entidad que ha seleccionado en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="02b11-110">Use this tab to view information about the party you have selected from the left pane.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="02b11-111">Utilice el Explorador de BizTalk para crear entidades.</span><span class="sxs-lookup"><span data-stu-id="02b11-111">You use BizTalk Explorer to create parties.</span></span>  
  
- <span data-ttu-id="02b11-112">**Definición de lote**.</span><span class="sxs-lookup"><span data-stu-id="02b11-112">**Batch Definition**.</span></span> <span data-ttu-id="02b11-113">Use esta ficha para configurar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="02b11-113">Use this tab to configure [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
- <span data-ttu-id="02b11-114">**Programación de batch**.</span><span class="sxs-lookup"><span data-stu-id="02b11-114">**Batch Schedule**.</span></span> <span data-ttu-id="02b11-115">Use esta ficha para activar los lotes salientes.</span><span class="sxs-lookup"><span data-stu-id="02b11-115">Use this tab to activate outbound batches.</span></span>  
  
- <span data-ttu-id="02b11-116">**Confirmación**.</span><span class="sxs-lookup"><span data-stu-id="02b11-116">**Acknowledgment**.</span></span> <span data-ttu-id="02b11-117">Use esta ficha para especificar las propiedades de las confirmaciones entrantes y generadas.</span><span class="sxs-lookup"><span data-stu-id="02b11-117">Use this tab to specify the properties for inbound and generated acknowledgments.</span></span>  
  
- <span data-ttu-id="02b11-118">**Validación**.</span><span class="sxs-lookup"><span data-stu-id="02b11-118">**Validation**.</span></span> <span data-ttu-id="02b11-119">Use esta ficha para seleccionar las opciones de validación de mensajes para mensajes entrantes y generados.</span><span class="sxs-lookup"><span data-stu-id="02b11-119">Use this tab to select the message validation options for inbound and generated messages.</span></span>  
  
- <span data-ttu-id="02b11-120">**Asignación de MSH**.</span><span class="sxs-lookup"><span data-stu-id="02b11-120">**MSH Map**.</span></span> <span data-ttu-id="02b11-121">Use esta ficha para habilitar las transformaciones de encabezado de mensaje para los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="02b11-121">Use this tab to enable message header transformations for inbound messages.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="02b11-122">Debe configurar los alias de entidad, las definiciones de batch, batch programa y la información de confirmación para todas las entidades comerciales.</span><span class="sxs-lookup"><span data-stu-id="02b11-122">You must configure party aliases, batch definitions, batch schedules, and acknowledgment information for all trading parties.</span></span>  
  > 
  >  <span data-ttu-id="02b11-123">Puede actualizar la lista de entidades, presione F5 o hace doble clic en la lista de entidades y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="02b11-123">You can refresh the parties list by pressing F5, or by right-clicking the parties list, and select **Refresh**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="02b11-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="02b11-124">Next steps</span></span>  
  
-   [<span data-ttu-id="02b11-125">Pestaña de los alias de entidad</span><span class="sxs-lookup"><span data-stu-id="02b11-125">Party Aliases Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/party-aliases-tab.md)  
  
-   [<span data-ttu-id="02b11-126">Pestaña definición de lote</span><span class="sxs-lookup"><span data-stu-id="02b11-126">Batch Definition Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/batch-definition-tab.md)  
  
-   [<span data-ttu-id="02b11-127">Pestaña programación por lotes</span><span class="sxs-lookup"><span data-stu-id="02b11-127">Batch Schedule Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/batch-schedule-tab.md)  
  
-   [<span data-ttu-id="02b11-128">Pestaña confirmación</span><span class="sxs-lookup"><span data-stu-id="02b11-128">Acknowledgment Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-tab.md)  
  
-   [<span data-ttu-id="02b11-129">Pestaña validación</span><span class="sxs-lookup"><span data-stu-id="02b11-129">Validation Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-tab.md)  
  
-   [<span data-ttu-id="02b11-130">Pestaña asignación de MSH</span><span class="sxs-lookup"><span data-stu-id="02b11-130">MSH Map Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-map-tab.md)