---
title: Crear el puerto de envío FRR para enviar a SWIFT | Microsoft Docs
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
ms.openlocfilehash: 1583072986eba20b5a0202e6973a5c08095aab01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972325"
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a><span data-ttu-id="9a624-102">Crear el puerto de envío FRR para enviar a SWIFT</span><span class="sxs-lookup"><span data-stu-id="9a624-102">Creating the FRR Send Port for Sending to SWIFT</span></span>
<span data-ttu-id="9a624-103">Para llevar a cabo la conciliación de respuestas de FIN, deberá crear un puerto de envío que envía un mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="9a624-103">To perform FIN Response Reconciliation, you need to create a send port that sends a message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the SWIFT Network.</span></span>  

 <span data-ttu-id="9a624-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="9a624-104">**Summary**</span></span>  

 <span data-ttu-id="9a624-105">Cree un puerto de envío con los componentes y las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a624-105">Create a send port with the following properties and components:</span></span>  


|     <span data-ttu-id="9a624-106">Propiedad o el componente</span><span class="sxs-lookup"><span data-stu-id="9a624-106">Property/Component</span></span>      |                                                               <span data-ttu-id="9a624-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="9a624-107">Setting</span></span>                                                                |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
|          <span data-ttu-id="9a624-108">Puerto de envío</span><span class="sxs-lookup"><span data-stu-id="9a624-108">Send port</span></span>          |                                                         <span data-ttu-id="9a624-109">Puerto unidireccional estático</span><span class="sxs-lookup"><span data-stu-id="9a624-109">Static one-way port</span></span>                                                          |
|       <span data-ttu-id="9a624-110">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="9a624-110">Transport type</span></span>        |                                                               <span data-ttu-id="9a624-111">MQSeries</span><span class="sxs-lookup"><span data-stu-id="9a624-111">MQSeries</span></span>                                                               |
| <span data-ttu-id="9a624-112">Definición de la cola (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="9a624-112">Queue Definition (MQSeries)</span></span> |                                                 <span data-ttu-id="9a624-113">Administrador de cola de MQSeries server cola</span><span class="sxs-lookup"><span data-stu-id="9a624-113">MQSeries server Queue manager Queue</span></span>                                                  |
|        <span data-ttu-id="9a624-114">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="9a624-114">Send pipeline</span></span>        | <span data-ttu-id="9a624-115">El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de envío que ha creado para FRR</span><span class="sxs-lookup"><span data-stu-id="9a624-115">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR</span></span> |
|           <span data-ttu-id="9a624-116">Filtros</span><span class="sxs-lookup"><span data-stu-id="9a624-116">Filters</span></span>           |                                                     <span data-ttu-id="9a624-117">Como se muestra en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="9a624-117">As shown in the table below</span></span>                                                      |

### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a><span data-ttu-id="9a624-118">Para agregar un puerto de envío personalizada para enviar a SWIFT</span><span class="sxs-lookup"><span data-stu-id="9a624-118">To add a custom send port for sending to SWIFT</span></span>  

1. <span data-ttu-id="9a624-119">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto estático de uno waySend**.</span><span class="sxs-lookup"><span data-stu-id="9a624-119">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  

2. <span data-ttu-id="9a624-120">En el cuadro de diálogo Propiedades de puerto de envío, en el **nombre** , escriba un nombre para el puerto de envío, como FRRSWIFTSendPort.</span><span class="sxs-lookup"><span data-stu-id="9a624-120">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRSWIFTSendPort.</span></span>  

3. <span data-ttu-id="9a624-121">Para **tipo**, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="9a624-121">For **Type**, select **MQSeries**.</span></span>  

4. <span data-ttu-id="9a624-122">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="9a624-122">Click **Configure**.</span></span>  

5. <span data-ttu-id="9a624-123">En el cuadro de diálogo Propiedades de transporte MQSeries, haga clic en **definición de la cola**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="9a624-123">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis () button.</span></span>  

6. <span data-ttu-id="9a624-124">En el cuadro de diálogo Definición de la cola, especifique el servidor, Administrador de cola y cola de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="9a624-124">In the Queue Definition dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="9a624-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9a624-125">Click **OK**.</span></span>  

7. <span data-ttu-id="9a624-126">En el cuadro de diálogo Propiedades de transporte MQSeries, compruebe que las propiedades son según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9a624-126">In the MQSeries Transport Properties dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="9a624-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9a624-127">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9a624-128">Para obtener más información acerca de las propiedades de transporte de MQSeries, vea la documentación de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="9a624-128">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  

8. <span data-ttu-id="9a624-129">En el cuadro de diálogo Propiedades de puerto de envío para **controlador de envío**, compruebe que está seleccionado BizTalkServerApplication.</span><span class="sxs-lookup"><span data-stu-id="9a624-129">In the Send Port Properties dialog box, for **Send handler**, verify that BizTalkServerApplication is selected.</span></span>  

9. <span data-ttu-id="9a624-130">Para **canalización de envío**, seleccione el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de envío que ha creado para FRR.</span><span class="sxs-lookup"><span data-stu-id="9a624-130">For **Send Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR.</span></span>  

10. <span data-ttu-id="9a624-131">Haga clic en **filtros** en el panel izquierdo y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a624-131">Click **Filters** in the left pane, and then do the following:</span></span>  


    |   <span data-ttu-id="9a624-132">Use</span><span class="sxs-lookup"><span data-stu-id="9a624-132">Use this</span></span>   |                            <span data-ttu-id="9a624-133">Para</span><span class="sxs-lookup"><span data-stu-id="9a624-133">To do this</span></span>                             |
    |--------------|-------------------------------------------------------------------|
    | <span data-ttu-id="9a624-134">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="9a624-134">**Property**</span></span> |  <span data-ttu-id="9a624-135">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span><span class="sxs-lookup"><span data-stu-id="9a624-135">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>  |
    | <span data-ttu-id="9a624-136">**Operador**</span><span class="sxs-lookup"><span data-stu-id="9a624-136">**Operator**</span></span> |                          <span data-ttu-id="9a624-137">Seleccione **==**.</span><span class="sxs-lookup"><span data-stu-id="9a624-137">Select **==**.</span></span>                           |
    |  <span data-ttu-id="9a624-138">**Value**</span><span class="sxs-lookup"><span data-stu-id="9a624-138">**Value**</span></span>   |                          <span data-ttu-id="9a624-139">Tipo **False**.</span><span class="sxs-lookup"><span data-stu-id="9a624-139">Type **False**.</span></span>                          |
    |  <span data-ttu-id="9a624-140">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="9a624-140">**Group**</span></span>   |                          <span data-ttu-id="9a624-141">Seleccione **y**.</span><span class="sxs-lookup"><span data-stu-id="9a624-141">Select **And**.</span></span>                          |
    | <span data-ttu-id="9a624-142">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="9a624-142">**Property**</span></span> | <span data-ttu-id="9a624-143">Tipo **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**.</span><span class="sxs-lookup"><span data-stu-id="9a624-143">Type **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**.</span></span> |
    | <span data-ttu-id="9a624-144">**Operador**</span><span class="sxs-lookup"><span data-stu-id="9a624-144">**Operator**</span></span> |                          <span data-ttu-id="9a624-145">Seleccione **==**.</span><span class="sxs-lookup"><span data-stu-id="9a624-145">Select **==**.</span></span>                           |
    |  <span data-ttu-id="9a624-146">**Value**</span><span class="sxs-lookup"><span data-stu-id="9a624-146">**Value**</span></span>   |                          <span data-ttu-id="9a624-147">Tipo **True**.</span><span class="sxs-lookup"><span data-stu-id="9a624-147">Type **True**.</span></span>                           |


11. <span data-ttu-id="9a624-148">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9a624-148">Click **Apply**, and then click **OK**.</span></span>  

12. <span data-ttu-id="9a624-149">Haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9a624-149">Right-click the send port, and then click **Start**.</span></span>
