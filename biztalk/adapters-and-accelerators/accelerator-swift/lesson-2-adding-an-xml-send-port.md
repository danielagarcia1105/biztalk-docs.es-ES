---
title: 'Lección 2: Agregar un puerto de envío XML | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, XML ports
- XML ports
ms.assetid: 03b2ee43-7874-4ef9-b716-8e16e96d8382
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d8aac412bf81492793eec2f4936d84b54fda0d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960706"
---
# <a name="lesson-2-adding-an-xml-send-port"></a><span data-ttu-id="82035-102">Lección 2: Agregar un puerto de envío de XML</span><span class="sxs-lookup"><span data-stu-id="82035-102">Lesson 2: Adding an XML Send Port</span></span>
<span data-ttu-id="82035-103">Use un puerto de envío para definir cómo desea que los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="82035-103">You use a send port to define how you want the messages sent.</span></span> <span data-ttu-id="82035-104">En esta lección, creará un puerto de envío para definir cómo se deberían enviar los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="82035-104">In this lesson, you create a send port to define how XML messages should be sent.</span></span>  
  
### <a name="to-add-an-xml-send-port"></a><span data-ttu-id="82035-105">Para agregar un puerto de envío XML</span><span class="sxs-lookup"><span data-stu-id="82035-105">To add an XML send port</span></span>  
  
1.  <span data-ttu-id="82035-106">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="82035-106">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="82035-107">En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba **MT103_XML_SendPort**.</span><span class="sxs-lookup"><span data-stu-id="82035-107">In the Send Port Properties dialog box, in the **Name** box, type **MT103_XML_SendPort**.</span></span>  
  
3.  <span data-ttu-id="82035-108">En el **transporte** sección, para la **tipo** cuadro, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="82035-108">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="82035-109">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="82035-109">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="82035-110">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="82035-110">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="82035-111">En el cuadro de diálogo Buscar carpeta, desplácese a la  **\<unidad\>: \Labs\Outbound** carpeta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82035-111">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs\Outbound** folder, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="82035-112">En el cuadro de diálogo Propiedades de transporte de archivo, asegúrese de que **%MessageID%.xml** se escribe en el **nombre de archivo** cuadro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82035-112">In the FILE Transport Properties dialog box, ensure that **%MessageID%.xml** is entered in the **File Name** box, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="82035-113">En el cuadro de diálogo Propiedades de puerto de envío, asegúrese de que **BizTalkServerApplication** está seleccionada para la **controlador de envío** cuadro y que **PassThruTransmit** está seleccionada para el **Canalización de envío** cuadro.</span><span class="sxs-lookup"><span data-stu-id="82035-113">In the Send Port Properties dialog box, ensure that **BizTalkServerApplication** is selected for the **Send handler** box, and that **PassThruTransmit** is selected for the **Send pipeline** box.</span></span>  
  
9. <span data-ttu-id="82035-114">En el panel izquierdo, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82035-114">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="82035-115">Use</span><span class="sxs-lookup"><span data-stu-id="82035-115">Use this</span></span>|<span data-ttu-id="82035-116">Para</span><span class="sxs-lookup"><span data-stu-id="82035-116">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="82035-117">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="82035-117">**Property**</span></span>|<span data-ttu-id="82035-118">Seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="82035-118">Select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="82035-119">**Operador**</span><span class="sxs-lookup"><span data-stu-id="82035-119">**Operator**</span></span>|<span data-ttu-id="82035-120">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="82035-120">Select **==**.</span></span>|  
    |<span data-ttu-id="82035-121">**Valor**</span><span class="sxs-lookup"><span data-stu-id="82035-121">**Value**</span></span>|<span data-ttu-id="82035-122">Tipo de **MT103_FlatFile_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="82035-122">Type **MT103_FlatFile_ReceivePort**.</span></span>|  
    |<span data-ttu-id="82035-123">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="82035-123">**Group**</span></span>|<span data-ttu-id="82035-124">Seleccione **y**.</span><span class="sxs-lookup"><span data-stu-id="82035-124">Select **And**.</span></span>|  
  
10. <span data-ttu-id="82035-125">Haga clic dentro de la siguiente línea de propiedad y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82035-125">Click inside the next property line and do the following:</span></span>  
  
    |<span data-ttu-id="82035-126">Use</span><span class="sxs-lookup"><span data-stu-id="82035-126">Use this</span></span>|<span data-ttu-id="82035-127">Para</span><span class="sxs-lookup"><span data-stu-id="82035-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="82035-128">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="82035-128">**Property**</span></span>|<span data-ttu-id="82035-129">Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**</span><span class="sxs-lookup"><span data-stu-id="82035-129">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**</span></span>|  
    |<span data-ttu-id="82035-130">**Operador**</span><span class="sxs-lookup"><span data-stu-id="82035-130">**Operator**</span></span>|<span data-ttu-id="82035-131">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="82035-131">Select **==**.</span></span>|  
    |<span data-ttu-id="82035-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="82035-132">**Value**</span></span>|<span data-ttu-id="82035-133">Tipo de **False** para mensajes válidos.</span><span class="sxs-lookup"><span data-stu-id="82035-133">Type **False** for valid messages.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="82035-134">Agrega el **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False"** cláusula de expresión de filtro para que el puerto de envío envía solo correctamente analizar y validar mensajes.</span><span class="sxs-lookup"><span data-stu-id="82035-134">You add the **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False"** filter expression clause so that the send port sends only successfully parsed and validated messages.</span></span> <span data-ttu-id="82035-135">A diferencia de una canalización de recepción mediante nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] desensambladores, el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Desensamblador no suspenderá un mensaje con errores (erróneo), pero en su lugar, se publica en el cuadro de mensajes y marcas como error, utilizando las propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="82035-135">Unlike a receive pipeline using native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] disassemblers, the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] disassembler will not suspend a failed (erroneous) message, but instead publishes it to the MessageBox and marks it as failed, using promoted properties.</span></span> <span data-ttu-id="82035-136">A4SWIFT asocia una representación XML de los errores que se recopilaron para el mensaje con errores antes de publicarlos en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="82035-136">A4SWIFT attaches an XML representation of the errors that were collected to the failed message before publishing it to the MessageBox.</span></span>  
    > <span data-ttu-id="82035-137">Sin incluir la "Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False" cláusula de expresión de filtro, el puerto de envío enviará todos los mensajes: superado o no superado.</span><span class="sxs-lookup"><span data-stu-id="82035-137">Without including the "Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False" filter expression clause, your send port will send all messages: passed or failed.</span></span> <span data-ttu-id="82035-138">Para obtener más información acerca de las suscripciones de mensajes con errores, vea [trabajar con suscripciones de mensajes de error](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="82035-138">For more information about failed message subscriptions, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
11. <span data-ttu-id="82035-139">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82035-139">Click **Apply**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="82035-140">En la consola de administración de BizTalk Server, en **puertos de envío**, haga clic en **MT103_XML_SendPort**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="82035-140">In the BizTalk Server Administration Console, in **Send Ports**, right-click **MT103_XML_SendPort**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="82035-141">Continúe con [módulo 6: implementar las reglas de negocios](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md).</span><span class="sxs-lookup"><span data-stu-id="82035-141">Proceed to [Module 6: Deploying the Business Rules](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md).</span></span>