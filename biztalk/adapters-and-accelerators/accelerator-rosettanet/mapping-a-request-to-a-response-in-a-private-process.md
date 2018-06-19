---
title: Asignar una solicitud a una respuesta en un proceso privado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- private processes, mapping requests
- private processes, customizing
- orchestrations, adding maps
- maps, adding to orchestrations
- maps, creating
- customizing private processes
- requests, mapping
- requests, private processes
ms.assetid: 5452c0a2-3a9b-43e7-bfa7-713eef0eab3b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966ad6ad752c36be36b4013743eaba3af5434d0a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008373"
---
# <a name="mapping-a-request-to-a-response-in-a-private-process"></a><span data-ttu-id="8e73c-102">Asignar una solicitud a una respuesta en un proceso privado</span><span class="sxs-lookup"><span data-stu-id="8e73c-102">Mapping a Request to a Response in a Private Process</span></span>
<span data-ttu-id="8e73c-103">Este tema describe cómo asignar un mensaje de solicitud recibido por el proceso de servicio de respuesta privada: desde la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proceso de servicio de respuesta pública, en un mensaje de respuesta que se puede enviar a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] el proceso de servicio de respuesta pública.</span><span class="sxs-lookup"><span data-stu-id="8e73c-103">This topic describes how to map a request message received by the private responder process—from the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] public responder process, to a response message that can be sent to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public responder process.</span></span>  
  
 <span data-ttu-id="8e73c-104">Cuando un servicio de respuesta recibe un mensaje de solicitud, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enruta el mensaje de solicitud de la orquestación de proceso público a la orquestación de procesos privado, el programa de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="8e73c-104">When a responder receives a request message, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] routes the request message from the public-process orchestration, to the private-process orchestration, to the line-of-business (LOB) program.</span></span> <span data-ttu-id="8e73c-105">El servicio de respuesta requiere el contenido del servicio de respuesta desde el sistema LOB para generar un mensaje de respuesta de RosettaNet al iniciador.</span><span class="sxs-lookup"><span data-stu-id="8e73c-105">The responder requires the response service content from the LOB program to generate a RosettaNet response message back to the initiator.</span></span> <span data-ttu-id="8e73c-106">Muchos de los elementos en el mensaje de respuesta se rellenan con los valores del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="8e73c-106">Many of the elements in the response message are populated using the values from the request message.</span></span> <span data-ttu-id="8e73c-107">Como resultado, puede incorporar un mapa en la orquestación de procesos privados de servicio de respuesta para ayudar a que el sistema LOB generar el mensaje de contenido del servicio de respuesta en el formato requerido.</span><span class="sxs-lookup"><span data-stu-id="8e73c-107">As a result, you can incorporate a map in the responder private-process orchestration to help the LOB program generate the response service-content message in the required format.</span></span>  
  
 <span data-ttu-id="8e73c-108">El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK contiene los siguientes ejemplos que puede utilizar cuando se agrega una asignación a un proceso privado de servicio de respuesta:</span><span class="sxs-lookup"><span data-stu-id="8e73c-108">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK contains the following samples that you can use when you add a map to a responder private-process:</span></span>  
  
-   [<span data-ttu-id="8e73c-109">Solicitud de 3A2 al ejemplo de asignación de respuesta de 3A2</span><span class="sxs-lookup"><span data-stu-id="8e73c-109">3A2 Request to 3A2 Response Map Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)  
  
-   [<span data-ttu-id="8e73c-110">Solicitud de 3A4 al ejemplo de asignación de respuesta de 3A4</span><span class="sxs-lookup"><span data-stu-id="8e73c-110">3A4 Request to 3A4 Response Map Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)  
  
-   [<span data-ttu-id="8e73c-111">Orquestación PIPAutomation de acción doble</span><span class="sxs-lookup"><span data-stu-id="8e73c-111">Double Action PIPAutomation Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)  
  
-   [<span data-ttu-id="8e73c-112">Orquestación del respondedor privado 3A4 mediante una regla de negocio</span><span class="sxs-lookup"><span data-stu-id="8e73c-112">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)  
  
### <a name="to-create-the-map"></a><span data-ttu-id="8e73c-113">Para crear la asignación</span><span class="sxs-lookup"><span data-stu-id="8e73c-113">To create the map</span></span>  
  
1.  <span data-ttu-id="8e73c-114">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-114">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="8e73c-115">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-115">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="8e73c-116">Busque la carpeta que contiene el proyecto de BizTalk que contiene la orquestación de procesos privado al que desea agregar el mapa.</span><span class="sxs-lookup"><span data-stu-id="8e73c-116">Locate the folder that contains the BizTalk project that contains the private-process orchestration to which you want to add the map.</span></span>  
  
4.  <span data-ttu-id="8e73c-117">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, seleccione **Agregar** y, después, haga clic en **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-117">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
5.  <span data-ttu-id="8e73c-118">En la ventana Agregar nuevo elemento, en la **categorías** panel, haga clic en **archivos de asignación**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-118">In the Add New Item window, in the **Categories** pane, click **Map Files**.</span></span> <span data-ttu-id="8e73c-119">En el panel Plantillas, haga clic en **mapa**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-119">In the Templates pane, click **Map**.</span></span> <span data-ttu-id="8e73c-120">En el **nombre** , escriba un nombre para la asignación y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-120">In the **Name** box, type a name for the map, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="8e73c-121">En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-121">In the Source Schema pane, click **Open Source Schema**.</span></span>  
  
7.  <span data-ttu-id="8e73c-122">En la ventana del selector de tipos de BizTalk, expanda **esquemas**, seleccione el esquema PIP para el mensaje de solicitud que se desea crear una asignación de y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-122">In the BizTalk Type Picker window, expand **Schemas**, select the PIP schema for the request message that you want to map from, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8e73c-123">En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-123">In the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
9. <span data-ttu-id="8e73c-124">En la ventana del selector de tipos de BizTalk, expanda **referencias**, expanda **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expanda **esquemas**, seleccione el esquema PIP para el mensaje de respuesta a la que desea asignar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-124">In the BizTalk Type Picker window, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expand **Schemas**, select the PIP schema for the response message to which you want to map, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="8e73c-125">Haga clic en el \< *esquema* \> nodo del esquema de origen y, a continuación, haga clic en **Expandir nodo de árbol**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-125">Right-click the \<*Schema*\> node of the source schema, and then click **Expand Tree Node**.</span></span>  
  
11. <span data-ttu-id="8e73c-126">Repita el paso 10 para el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8e73c-126">Repeat step 10 for the destination schema.</span></span>  
  
12. <span data-ttu-id="8e73c-127">En el panel de esquema de origen, haga clic y mantenga en un campo que desea asignar a un campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8e73c-127">In the Source Schema pane, click and hold on a field that you want to map to a field in the destination schema.</span></span> <span data-ttu-id="8e73c-128">Arrastre hasta el nodo correspondiente en el panel de esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8e73c-128">Drag to the corresponding node in the Destination Schema pane.</span></span>  
  
13. <span data-ttu-id="8e73c-129">Repita el paso 12 para todos los campos que se deben asignar entre los dos esquemas.</span><span class="sxs-lookup"><span data-stu-id="8e73c-129">Repeat step 12 for all fields that you have to map between the two schemas.</span></span>  
  
14. <span data-ttu-id="8e73c-130">Valide y pruebe la asignación.</span><span class="sxs-lookup"><span data-stu-id="8e73c-130">Validate and test the map.</span></span> <span data-ttu-id="8e73c-131">Para obtener más información, vea el tema "Compilar y probar asignaciones" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8e73c-131">For more information, see the "Compiling and Testing Maps" topic in BizTalk Server Help.</span></span>  
  
### <a name="to-add-the-map-to-the-orchestration"></a><span data-ttu-id="8e73c-132">Para agregar la asignación a la orquestación</span><span class="sxs-lookup"><span data-stu-id="8e73c-132">To add the map to the orchestration</span></span>  
  
1.  <span data-ttu-id="8e73c-133">En el Explorador de soluciones, haga doble clic en la orquestación de procesos privado.</span><span class="sxs-lookup"><span data-stu-id="8e73c-133">In Solution Explorer, double-click the private-process orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e73c-134">Asegúrese de que la orquestación tiene referencias a los ensamblados que contienen los esquemas.</span><span class="sxs-lookup"><span data-stu-id="8e73c-134">Make sure that the orchestration has references to the assemblies that contain the schemas.</span></span>  
  
2.  <span data-ttu-id="8e73c-135">En el cuadro de herramientas, haga clic en el **transformar** forma y arrástrelo hasta el punto en la orquestación a la que se tiene que transformar el mensaje de solicitud en el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8e73c-135">In the Toolbox, click the **Transform** shape, and drag it to the point in the orchestration at which you have to transform the request message into the response message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e73c-136">Para obtener un ejemplo de la colocación de la **transformar** forma, vea la orquestación PIP3A4PrivateResponder.odx.</span><span class="sxs-lookup"><span data-stu-id="8e73c-136">For an example of the placement of the **Transform** shape, see the PIP3A4PrivateResponder.odx orchestration.</span></span> <span data-ttu-id="8e73c-137">Se encuentra en \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\PipAutomation\3A4\PR.</span><span class="sxs-lookup"><span data-stu-id="8e73c-137">It is located in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4\PR.</span></span> <span data-ttu-id="8e73c-138">Este ejemplo pone el **transformar** forma inmediatamente en el **IsActivityDoubleAction** forma.</span><span class="sxs-lookup"><span data-stu-id="8e73c-138">This sample puts the **Transform** shape immediately under the **IsActivityDoubleAction** shape.</span></span> <span data-ttu-id="8e73c-139">Para obtener más información, consulte [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span><span class="sxs-lookup"><span data-stu-id="8e73c-139">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e73c-140">Para obtener un ejemplo de cómo se pueden incorporar varias asignaciones para varias PIP, consulte [orquestación de PIPAutomation de doble acción](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="8e73c-140">For an example of how you can incorporate multiple maps for multiple PIPs, see [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).</span></span>  
  
3.  <span data-ttu-id="8e73c-141">En la superficie de diseño de orquestación, haga clic en **ConstructMessage1**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-141">On the orchestration design surface, click **ConstructMessage1**.</span></span> <span data-ttu-id="8e73c-142">En la ventana Propiedades, escriba un nombre para la forma y un nombre para el mensaje va a construir.</span><span class="sxs-lookup"><span data-stu-id="8e73c-142">In the Properties window, type a name for the shape, and a name for the message to be constructed.</span></span>  
  
4.  <span data-ttu-id="8e73c-143">En la superficie de diseño de orquestación, haga clic en **transformar**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-143">On the orchestration design surface, click **Transform**.</span></span> <span data-ttu-id="8e73c-144">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) junto a **nombre de asignación**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-144">In the Properties window, click the ellipsis button (**...**) next to **Map Name**.</span></span>  
  
5.  <span data-ttu-id="8e73c-145">En la ventana Configuración de transformación, haga clic en **mapa existente**y en **nombre completo de asignación**, haga clic en la asignación que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="8e73c-145">In the Transform Configuration window, click **Existing Map**, and in **Fully Qualified Map Name**, click the map that you just created.</span></span>  
  
6.  <span data-ttu-id="8e73c-146">En **transformar**, haga clic en **origen**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-146">Under **Transform**, click **Source**.</span></span> <span data-ttu-id="8e73c-147">Haga clic en el cuadro vacío en la variable y seleccione el nombre del mensaje de solicitud de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8e73c-147">Click the empty box under variable, and select the name of the request message from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="8e73c-148">En **transformar**, haga clic en **destino**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-148">Under **Transform**, click **Destination**.</span></span> <span data-ttu-id="8e73c-149">Haga clic en el cuadro vacío en la variable y seleccione el nombre del mensaje de respuesta de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8e73c-149">Click the empty box under variable, and select the name of the response message from the drop-down list.</span></span>  
  
8.  <span data-ttu-id="8e73c-150">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8e73c-150">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e73c-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e73c-151">See Also</span></span>  
 [<span data-ttu-id="8e73c-152">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="8e73c-152">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)