---
title: "Crear un puerto de envío de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
ms.assetid: d1ee18f8-a6aa-4cd5-9e65-fb2e0fa2d0c2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf24cb99643acc869123450ce14fd5050ee7408
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-a4swift-send-port"></a><span data-ttu-id="afcd1-102">Crear un puerto de envío de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="afcd1-102">Creating an A4SWIFT Send Port</span></span>
<span data-ttu-id="afcd1-103">Debe crear un puerto de envío para habilitar [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para enviar un mensaje a la red SWIFT, tal como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="afcd1-103">You must create a send port to enable [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to send a message to the SWIFT network, as shown in the following figure.</span></span> <span data-ttu-id="afcd1-104">Este puerto de envío enviará mensajes de archivo sin formato en una carpeta de archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="afcd1-104">This send port will send flat file messages to an outbound file folder.</span></span> <span data-ttu-id="afcd1-105">Este puerto de envío está diseñado para trabajar con la característica de reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="afcd1-105">This send port is designed to work with the Message Repair and New Submission feature.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")  
  
 <span data-ttu-id="afcd1-106">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="afcd1-106">**Summary**</span></span>  
  
 <span data-ttu-id="afcd1-107">Crear e iniciar un puerto de envío unidireccional estático con las propiedades y los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="afcd1-107">Create and start a static one-way send port with the following properties and components:</span></span>  
  
|<span data-ttu-id="afcd1-108">Propiedad/componente</span><span class="sxs-lookup"><span data-stu-id="afcd1-108">Property/Component</span></span>|<span data-ttu-id="afcd1-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="afcd1-109">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="afcd1-110">Puerto de envío</span><span class="sxs-lookup"><span data-stu-id="afcd1-110">Send port</span></span>|<span data-ttu-id="afcd1-111">Puerto unidireccional estático</span><span class="sxs-lookup"><span data-stu-id="afcd1-111">Static one-way port</span></span>|  
|<span data-ttu-id="afcd1-112">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="afcd1-112">Transport type</span></span>|<span data-ttu-id="afcd1-113">FILE</span><span class="sxs-lookup"><span data-stu-id="afcd1-113">FILE</span></span>|  
|<span data-ttu-id="afcd1-114">Carpeta de destino (URI de dirección)</span><span class="sxs-lookup"><span data-stu-id="afcd1-114">Destination folder (Address URI)</span></span>|<span data-ttu-id="afcd1-115">Nombre de la carpeta que desea enviar mensajes desde</span><span class="sxs-lookup"><span data-stu-id="afcd1-115">Name of the folder that you want to send messages from</span></span>|  
|<span data-ttu-id="afcd1-116">Nombre de archivo (dirección URI)</span><span class="sxs-lookup"><span data-stu-id="afcd1-116">File Name (Address URI)</span></span>|<span data-ttu-id="afcd1-117">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="afcd1-117">%MessageID%.txt</span></span>|  
|<span data-ttu-id="afcd1-118">Filtros</span><span class="sxs-lookup"><span data-stu-id="afcd1-118">Filters</span></span>|<span data-ttu-id="afcd1-119">Como se describe en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="afcd1-119">As described in the table below</span></span>|  
  
### <a name="to-add-the-sent-port"></a><span data-ttu-id="afcd1-120">Para agregar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="afcd1-120">To add the sent port</span></span>  
  
1.  <span data-ttu-id="afcd1-121">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-121">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="afcd1-122">En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="afcd1-122">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port.</span></span>  
  
3.  <span data-ttu-id="afcd1-123">En el **transporte** sección, para la **tipo** cuadro, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-123">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="afcd1-124">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="afcd1-124">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="afcd1-125">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-125">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="afcd1-126">En el cuadro de diálogo Buscar carpeta, mover a la carpeta que desea enviar mensajes desde.</span><span class="sxs-lookup"><span data-stu-id="afcd1-126">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="afcd1-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-127">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="afcd1-128">Si esta carpeta no existe, puede crearlo mediante el **crear nueva carpeta** comando.</span><span class="sxs-lookup"><span data-stu-id="afcd1-128">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
7.  <span data-ttu-id="afcd1-129">En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-129">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="afcd1-130">En el **propiedades de puerto de envío** diálogo cuadro, haga clic en la lista desplegable para la **canalización de envío** cuadro y, a continuación, seleccione la canalización de envío personalizada.</span><span class="sxs-lookup"><span data-stu-id="afcd1-130">In the **Send Port Properties** dialog box, click the drop-down list for the **Send pipeline** box, and then select your custom send pipeline.</span></span>  
  
9. <span data-ttu-id="afcd1-131">En el panel izquierdo, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="afcd1-131">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="afcd1-132">Use</span><span class="sxs-lookup"><span data-stu-id="afcd1-132">Use this</span></span>|<span data-ttu-id="afcd1-133">Para</span><span class="sxs-lookup"><span data-stu-id="afcd1-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="afcd1-134">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="afcd1-134">**Property**</span></span>|<span data-ttu-id="afcd1-135">Seleccione **BTS. Operación**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-135">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="afcd1-136">**Operador**</span><span class="sxs-lookup"><span data-stu-id="afcd1-136">**Operator**</span></span>|<span data-ttu-id="afcd1-137">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="afcd1-137">Select **==**.</span></span>|  
    |<span data-ttu-id="afcd1-138">**Valor**</span><span class="sxs-lookup"><span data-stu-id="afcd1-138">**Value**</span></span>|<span data-ttu-id="afcd1-139">Tipo de **A4SWIFT_MRSRCompleted**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-139">Type **A4SWIFT_MRSRCompleted**.</span></span>|  
    |<span data-ttu-id="afcd1-140">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="afcd1-140">**Group**</span></span>|<span data-ttu-id="afcd1-141">Seleccione **o.**</span><span class="sxs-lookup"><span data-stu-id="afcd1-141">Select **Or.**</span></span>|  
    |<span data-ttu-id="afcd1-142">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="afcd1-142">**Property**</span></span>|<span data-ttu-id="afcd1-143">Seleccione **BTS. Operación**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-143">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="afcd1-144">**Operador**</span><span class="sxs-lookup"><span data-stu-id="afcd1-144">**Operator**</span></span>|<span data-ttu-id="afcd1-145">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="afcd1-145">Select **==**.</span></span>|  
    |<span data-ttu-id="afcd1-146">**Valor**</span><span class="sxs-lookup"><span data-stu-id="afcd1-146">**Value**</span></span>|<span data-ttu-id="afcd1-147">Tipo de **A4SWIFT_MRSRFailed**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-147">Type **A4SWIFT_MRSRFailed**.</span></span>|  
    |<span data-ttu-id="afcd1-148">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="afcd1-148">**Group**</span></span>|<span data-ttu-id="afcd1-149">Seleccione **o**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-149">Select **Or**.</span></span>|  
    |<span data-ttu-id="afcd1-150">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="afcd1-150">**Property**</span></span>|<span data-ttu-id="afcd1-151">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-151">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>|  
    |<span data-ttu-id="afcd1-152">**Operador**</span><span class="sxs-lookup"><span data-stu-id="afcd1-152">**Operator**</span></span>|<span data-ttu-id="afcd1-153">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="afcd1-153">Select **==**.</span></span>|  
    |<span data-ttu-id="afcd1-154">**Valor**</span><span class="sxs-lookup"><span data-stu-id="afcd1-154">**Value**</span></span>|<span data-ttu-id="afcd1-155">Tipo de **True**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-155">Type **True**.</span></span>|  
  
10. <span data-ttu-id="afcd1-156">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="afcd1-156">Click **Apply**, and then click **OK.**</span></span>  
  
11. <span data-ttu-id="afcd1-157">En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="afcd1-157">In the **Send Ports** pane, right-click the send port, and then click **Start**.</span></span>