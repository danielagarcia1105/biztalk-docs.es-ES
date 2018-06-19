---
title: Crear el puerto de envío FRR para enviar a SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cbda5d505f17f2dd7462cb0b16868a340f625c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210412"
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a><span data-ttu-id="a3970-102">Crear el puerto de envío FRR para enviar para SWIFT</span><span class="sxs-lookup"><span data-stu-id="a3970-102">Creating the FRR Send Port for Sending to SWIFT</span></span>
<span data-ttu-id="a3970-103">Para realizar la conciliación de respuesta de FIN, debe crear un puerto de envío que envía un mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="a3970-103">To perform FIN Response Reconciliation, you need to create a send port that sends a message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the SWIFT Network.</span></span>  
  
 <span data-ttu-id="a3970-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="a3970-104">**Summary**</span></span>  
  
 <span data-ttu-id="a3970-105">Crear un puerto de envío con los componentes y las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3970-105">Create a send port with the following properties and components:</span></span>  
  
|<span data-ttu-id="a3970-106">Propiedad/componente</span><span class="sxs-lookup"><span data-stu-id="a3970-106">Property/Component</span></span>|<span data-ttu-id="a3970-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="a3970-107">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="a3970-108">Puerto de envío</span><span class="sxs-lookup"><span data-stu-id="a3970-108">Send port</span></span>|<span data-ttu-id="a3970-109">Puerto unidireccional estático</span><span class="sxs-lookup"><span data-stu-id="a3970-109">Static one-way port</span></span>|  
|<span data-ttu-id="a3970-110">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="a3970-110">Transport type</span></span>|<span data-ttu-id="a3970-111">MQSeries</span><span class="sxs-lookup"><span data-stu-id="a3970-111">MQSeries</span></span>|  
|<span data-ttu-id="a3970-112">Definición de la cola (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="a3970-112">Queue Definition (MQSeries)</span></span>|<span data-ttu-id="a3970-113">Administrador de cola de MQSeries server cola</span><span class="sxs-lookup"><span data-stu-id="a3970-113">MQSeries server Queue manager Queue</span></span>|  
|<span data-ttu-id="a3970-114">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="a3970-114">Send pipeline</span></span>|<span data-ttu-id="a3970-115">El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de envío que ha creado para FRR</span><span class="sxs-lookup"><span data-stu-id="a3970-115">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR</span></span>|  
|<span data-ttu-id="a3970-116">Filtros</span><span class="sxs-lookup"><span data-stu-id="a3970-116">Filters</span></span>|<span data-ttu-id="a3970-117">Como se muestra en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="a3970-117">As shown in the table below</span></span>|  
  
### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a><span data-ttu-id="a3970-118">Para agregar un puerto de envío personalizada para enviar a SWIFT</span><span class="sxs-lookup"><span data-stu-id="a3970-118">To add a custom send port for sending to SWIFT</span></span>  
  
1.  <span data-ttu-id="a3970-119">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto estático de una waySend**.</span><span class="sxs-lookup"><span data-stu-id="a3970-119">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  
  
2.  <span data-ttu-id="a3970-120">En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba un nombre para el puerto de envío, por ejemplo, FRRSWIFTSendPort.</span><span class="sxs-lookup"><span data-stu-id="a3970-120">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRSWIFTSendPort.</span></span>  
  
3.  <span data-ttu-id="a3970-121">Para **tipo**, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="a3970-121">For **Type**, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="a3970-122">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a3970-122">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a3970-123">En el cuadro de diálogo Propiedades de transporte MQSeries, haga clic en **definición de la cola**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="a3970-123">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis () button.</span></span>  
  
6.  <span data-ttu-id="a3970-124">En el cuadro de diálogo Definición de la cola, especifique el servidor, un administrador de cola y una cola de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="a3970-124">In the Queue Definition dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="a3970-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3970-125">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="a3970-126">En el cuadro de diálogo Propiedades de transporte MQSeries, compruebe que las propiedades son según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a3970-126">In the MQSeries Transport Properties dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="a3970-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3970-127">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a3970-128">Para obtener más información acerca de las propiedades de transporte de MQSeries, consulte la documentación de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="a3970-128">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  
  
8.  <span data-ttu-id="a3970-129">En el cuadro de diálogo Propiedades de puerto de envío, para **controlador de envío**, compruebe que está seleccionado BizTalkServerApplication.</span><span class="sxs-lookup"><span data-stu-id="a3970-129">In the Send Port Properties dialog box, for **Send handler**, verify that BizTalkServerApplication is selected.</span></span>  
  
9. <span data-ttu-id="a3970-130">Para **canalización de envío**, seleccione la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de envío que ha creado para FRR.</span><span class="sxs-lookup"><span data-stu-id="a3970-130">For **Send Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR.</span></span>  
  
10. <span data-ttu-id="a3970-131">Haga clic en **filtros** en el panel izquierdo y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3970-131">Click **Filters** in the left pane, and then do the following:</span></span>  
  
    |<span data-ttu-id="a3970-132">Use</span><span class="sxs-lookup"><span data-stu-id="a3970-132">Use this</span></span>|<span data-ttu-id="a3970-133">Para</span><span class="sxs-lookup"><span data-stu-id="a3970-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a3970-134">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="a3970-134">**Property**</span></span>|<span data-ttu-id="a3970-135">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span><span class="sxs-lookup"><span data-stu-id="a3970-135">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>|  
    |<span data-ttu-id="a3970-136">**Operador**</span><span class="sxs-lookup"><span data-stu-id="a3970-136">**Operator**</span></span>|<span data-ttu-id="a3970-137">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="a3970-137">Select **==**.</span></span>|  
    |<span data-ttu-id="a3970-138">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a3970-138">**Value**</span></span>|<span data-ttu-id="a3970-139">Tipo de **False**.</span><span class="sxs-lookup"><span data-stu-id="a3970-139">Type **False**.</span></span>|  
    |<span data-ttu-id="a3970-140">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="a3970-140">**Group**</span></span>|<span data-ttu-id="a3970-141">Seleccione **y**.</span><span class="sxs-lookup"><span data-stu-id="a3970-141">Select **And**.</span></span>|  
    |<span data-ttu-id="a3970-142">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="a3970-142">**Property**</span></span>|<span data-ttu-id="a3970-143">Tipo de **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**.</span><span class="sxs-lookup"><span data-stu-id="a3970-143">Type **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**.</span></span>|  
    |<span data-ttu-id="a3970-144">**Operador**</span><span class="sxs-lookup"><span data-stu-id="a3970-144">**Operator**</span></span>|<span data-ttu-id="a3970-145">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="a3970-145">Select **==**.</span></span>|  
    |<span data-ttu-id="a3970-146">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a3970-146">**Value**</span></span>|<span data-ttu-id="a3970-147">Tipo de **True**.</span><span class="sxs-lookup"><span data-stu-id="a3970-147">Type **True**.</span></span>|  
  
11. <span data-ttu-id="a3970-148">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3970-148">Click **Apply**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="a3970-149">Haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="a3970-149">Right-click the send port, and then click **Start**.</span></span>