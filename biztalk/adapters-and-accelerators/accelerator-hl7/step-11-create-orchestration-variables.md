---
title: "Paso 11: Crear Variables de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
- message enrichment tutorial, orchestrations
ms.assetid: 3d1f792d-fe74-4373-86fa-3debda55e732
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c12a437371c5412cfafa4140e74733655962fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-11-create-orchestration-variables"></a><span data-ttu-id="4780c-102">Paso 11: Crear Variables de orquestación</span><span class="sxs-lookup"><span data-stu-id="4780c-102">Step 11: Create Orchestration Variables</span></span>
<span data-ttu-id="4780c-103">En este paso, creará las variables de orquestación de las instancias de mensajes enviados y recibidos por la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4780c-103">In this step, you create the orchestration variables for the message instances sent and received by the orchestration.</span></span>  
  
 <span data-ttu-id="4780c-104">El Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) serializador espera los siguientes nombres de elemento.</span><span class="sxs-lookup"><span data-stu-id="4780c-104">The BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) serializer expects the following part names.</span></span> <span data-ttu-id="4780c-105">Si crea un mensaje de varias partes con ningún otro nombre de parte, el serializador rechaza el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4780c-105">If you create a multipart message with any other part names, the serializer rejects the message.</span></span> <span data-ttu-id="4780c-106">Los nombres de parte de mensaje son:</span><span class="sxs-lookup"><span data-stu-id="4780c-106">The message part names are:</span></span>  
  
-   <span data-ttu-id="4780c-107">MSHSegment</span><span class="sxs-lookup"><span data-stu-id="4780c-107">MSHSegment</span></span>  
  
-   <span data-ttu-id="4780c-108">BodySegments</span><span class="sxs-lookup"><span data-stu-id="4780c-108">BodySegments</span></span>  
  
-   <span data-ttu-id="4780c-109">Segmentos de Z</span><span class="sxs-lookup"><span data-stu-id="4780c-109">Z segments</span></span>  
  
 <span data-ttu-id="4780c-110">La siguiente es información importante acerca de los elementos del segmento de Z:</span><span class="sxs-lookup"><span data-stu-id="4780c-110">The following is important information about Z segment parts:</span></span>  
  
-   <span data-ttu-id="4780c-111">Todos los mensajes contienen tres partes como se describió anteriormente, independientemente de si está presente un segmento de Z o no.</span><span class="sxs-lookup"><span data-stu-id="4780c-111">All messages contain three parts as described above, regardless of whether a Z segment is present or not.</span></span>  
  
-   <span data-ttu-id="4780c-112">Usar un elemento de segmento de Z para contener los datos de la instancia de mensaje, que es final y no está definido en el esquema (lo que también significa que no se ha declarado).</span><span class="sxs-lookup"><span data-stu-id="4780c-112">You use a Z segment part to contain data from the message instance, which is trailing and not defined in the schema (which also means that it is undeclared).</span></span>  
  
-   <span data-ttu-id="4780c-113">Si no hay ningún dato no declarado, la parte del segmento de Z está en blanco.</span><span class="sxs-lookup"><span data-stu-id="4780c-113">If there is no undeclared data, the Z segment part is blank.</span></span> <span data-ttu-id="4780c-114">No ve los elementos del segmento de Z al ver el XML intermedio en el asignador de BizTalk; Sin embargo, en la herramienta de mantenimiento de BizTalk y seguimiento de actividad (HAT), verá tres partes para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="4780c-114">You do not see the Z segment parts when viewing the intermediate XML within BizTalk Mapper; however, in the BizTalk Health and Activity Tracking (HAT) tool, you see three parts to each message.</span></span>  
  
### <a name="to-create-orchestration-variables"></a><span data-ttu-id="4780c-115">Para crear variables de orquestación</span><span class="sxs-lookup"><span data-stu-id="4780c-115">To create orchestration variables</span></span>  
  
1.  <span data-ttu-id="4780c-116">Haga clic en el **Vista orquestación** ficha junto a la **el Explorador de soluciones** ficha bajo el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="4780c-116">Click the **Orchestration View** tab next to the **Solution Explorer** tab beneath the Solutions Explorer.</span></span>  
  
2.  <span data-ttu-id="4780c-117">En el **Vista orquestación** panel, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="4780c-117">In the **Orchestration View** pane, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="4780c-118">Cambiar el **identificador** propiedad en el **propiedades** panel para **DoorbellInputMessage**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4780c-118">Change the **Identifier** property in the **Properties** pane to **DoorbellInputMessage**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="4780c-119">En el **propiedades** panel, en la lista desplegable para **tipo de mensaje**, expanda **esquemas**y, a continuación, haga clic en **BTAHL7_Project.Doorbell**.</span><span class="sxs-lookup"><span data-stu-id="4780c-119">In the **Properties** pane, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7_Project.Doorbell**.</span></span>  
  
5.  <span data-ttu-id="4780c-120">Repita los pasos 2 y 3 para crear otro mensaje denominado **DoorbellOutputMessage**.</span><span class="sxs-lookup"><span data-stu-id="4780c-120">Repeat steps 2 and 3 to create another message named **DoorbellOutputMessage**.</span></span>  
  
6.  <span data-ttu-id="4780c-121">En el **propiedades** panel, en la lista desplegable para **tipo de mensaje**, expanda **esquemas**y, a continuación, haga clic en **BTAHL7Schemas.ADT_A04_22_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="4780c-121">In the **Properties** pane, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7Schemas.ADT_A04_22_GLO_DEF**.</span></span>  
  
7.  <span data-ttu-id="4780c-122">En el **Vista orquestación** panel, expanda el **tipos** nodo.</span><span class="sxs-lookup"><span data-stu-id="4780c-122">In the **Orchestration View** pane, expand the **Types** node.</span></span> <span data-ttu-id="4780c-123">Haga clic en **tipos de mensaje de varias partes**y, a continuación, haga clic en **nuevo tipo de mensaje de varias partes**.</span><span class="sxs-lookup"><span data-stu-id="4780c-123">Right-click **Multi-part Message Types**, and then click **New Multi-part Message Type**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="4780c-124">crea un nuevo tipo de mensaje denominado **MultipartType_1** junto con un nuevo mensaje denominado **MessagePart_1**.</span><span class="sxs-lookup"><span data-stu-id="4780c-124"> creates a new message type named **MultipartType_1** along with a new message named **MessagePart_1**.</span></span>  
  
8.  <span data-ttu-id="4780c-125">Haga clic en **MultipartType_1**y en el **propiedades** ventana, haga clic en **identificador** y escriba el nuevo nombre **DoorbellFinalMessageType**, y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4780c-125">Click **MultipartType_1**, and in the **Properties** window, click **Identifier** and type the new name **DoorbellFinalMessageType**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4780c-126">En los pasos 9 a 15, creará las partes del mensaje de varias partes.</span><span class="sxs-lookup"><span data-stu-id="4780c-126">In steps 9 through 15, you will create the parts of the multipart message.</span></span> <span data-ttu-id="4780c-127">Es importante el orden en que se crean las partes de un mensaje de varias partes.</span><span class="sxs-lookup"><span data-stu-id="4780c-127">The order in which you create the parts of a multipart message is important.</span></span> <span data-ttu-id="4780c-128">Cree siempre el encabezado, el cuerpo y, luego, el segmento de Z.</span><span class="sxs-lookup"><span data-stu-id="4780c-128">Always create the header, then the body, then the Z segment.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4780c-129">Una vez que ha creado y denominado las partes del mensaje, no cambie el nombre de ellos.</span><span class="sxs-lookup"><span data-stu-id="4780c-129">Once you have created and named the message parts, do not rename them.</span></span> <span data-ttu-id="4780c-130">Si es necesario, elimine la antigua parte del cuerpo y crear un nuevo elemento de cuerpo con un nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="4780c-130">If necessary, delete the old body part, and create a new body part with a new name.</span></span>  
  
9. <span data-ttu-id="4780c-131">En el **tipos** ventana, en **tipos de mensaje de varias partes**, expanda **DoorbellFinalMessageType**y, a continuación, haga clic en **MessagePart_1**.</span><span class="sxs-lookup"><span data-stu-id="4780c-131">In the **Types** window, under **Multi-part Message Types**, expand **DoorbellFinalMessageType**, and then click **MessagePart_1**.</span></span> <span data-ttu-id="4780c-132">En el **propiedades** panel, escriba **MSHSegment** para **identificador**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4780c-132">In the **Properties** pane, enter **MSHSegment** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="4780c-133">En la lista desplegable para **tipo**, expanda **clases .NET**y, a continuación, haga clic en \< **seleccionar ensamblados de referencia de >**.</span><span class="sxs-lookup"><span data-stu-id="4780c-133">In the drop-down list for **Type**, expand **.NET Classes**, and then click \<**Select from referenced assemblies>**.</span></span>  
  
10. <span data-ttu-id="4780c-134">En el **Seleccionar tipo de artefacto** cuadro de diálogo, en el panel izquierdo, haga clic en **System.Xml**.</span><span class="sxs-lookup"><span data-stu-id="4780c-134">In the **Select Artifact Type** dialog box, in the left pane, click **System.Xml**.</span></span> <span data-ttu-id="4780c-135">En el panel derecho, haga clic en **XmlDocument**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4780c-135">In the right pane, click **XmlDocument**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="4780c-136">En la ventana Vista orquestación, haga clic en **DoorbellFinalMessageType**y, a continuación, haga clic en **nueva parte de mensaje** para crear MessagePart_1.</span><span class="sxs-lookup"><span data-stu-id="4780c-136">In the Orchestration View window, right-click **DoorbellFinalMessageType**, and then click **New Message Part** to create MessagePart_1.</span></span>  
  
12. <span data-ttu-id="4780c-137">En el **propiedades** ventana, escriba **BodySegments** para **identificador**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4780c-137">In the **Properties** window, enter **BodySegments** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="4780c-138">En la lista desplegable para **tipo**, expanda **esquemas**y, a continuación, seleccione **BTAHL7Schemas.ADT_A04_22_GLO_DEF** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4780c-138">In the drop-down list for **Type**, expand **Schemas**, and then select **BTAHL7Schemas.ADT_A04_22_GLO_DEF** from the drop-down list.</span></span>  
  
13. <span data-ttu-id="4780c-139">Establecer el **parte del cuerpo del mensaje** propiedad **True**.</span><span class="sxs-lookup"><span data-stu-id="4780c-139">Set the **Message Body Part** property to **True**.</span></span>  
  
14. <span data-ttu-id="4780c-140">En el **Vista orquestación** ventana, haga clic en **DoorbellFinalMessageType**y, a continuación, haga clic en **nueva parte de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="4780c-140">In the **Orchestration View** window, right-click **DoorbellFinalMessageType**, and then click **New Message Part**.</span></span>  
  
15. <span data-ttu-id="4780c-141">En el **propiedades** panel, escriba **ZSegments** para **identificador**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4780c-141">In the **Properties** pane, enter **ZSegments** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="4780c-142">Haga clic en **tipo**, expanda **clases .NET**y, a continuación, haga clic en **System.String** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4780c-142">Click **Type**, expand **.NET Classes**, and then click **System.String** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4780c-143">Usa **System.String** para la Z segmentos parte del mensaje, porque un segmento de Z contiene datos de cadena que no es necesario para que se ajuste a un esquema.</span><span class="sxs-lookup"><span data-stu-id="4780c-143">You use **System.String** for the Z segments message part, because a Z segment contains string data that does not need to conform to a schema.</span></span>  
  
16. <span data-ttu-id="4780c-144">En el **Vista orquestación** ventana, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="4780c-144">In the **Orchestration View** window, right-click **Messages**, and then click **New Message**.</span></span>  
  
17. <span data-ttu-id="4780c-145">En el **propiedades** ventana, escriba **DoorbellFinalMessage** para **identificador**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4780c-145">In the **Properties** window, enter **DoorbellFinalMessage** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="4780c-146">En la lista desplegable para **tipo de mensaje**, expanda **tipos de mensaje de varias partes**y, a continuación, haga clic en **BTAHL7_Project.DoorbellFinalMessageType**.</span><span class="sxs-lookup"><span data-stu-id="4780c-146">In the drop-down list for **Message Type**, expand **Multi-part Message Types**, and then click **BTAHL7_Project.DoorbellFinalMessageType**.</span></span>  
  
18. <span data-ttu-id="4780c-147">En el **Vista orquestación** ventana, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**.</span><span class="sxs-lookup"><span data-stu-id="4780c-147">In the **Orchestration View** window, right-click **Variables**, and then click **New Variable**.</span></span>  
  
19. <span data-ttu-id="4780c-148">En el **propiedades** panel, escriba **HeaderInfo** para **identificador**, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4780c-148">In the **Properties** pane, enter **HeaderInfo** for **Identifier**, then press **Enter**.</span></span> <span data-ttu-id="4780c-149">En la lista desplegable para **tipo**, haga doble clic en \< **clase .NET >**.</span><span class="sxs-lookup"><span data-stu-id="4780c-149">In the drop-down list for **Type**, double-click \<**.NET Class>**.</span></span>  
  
20. <span data-ttu-id="4780c-150">En el **Seleccionar tipo de artefacto** ventana, en el panel izquierdo, haga clic en **System.Xml**.</span><span class="sxs-lookup"><span data-stu-id="4780c-150">In the **Select Artifact Type** window, in the left pane, click **System.Xml**.</span></span> <span data-ttu-id="4780c-151">En el panel derecho, haga clic en **XmlDocument**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4780c-151">In the right pane, click **XmlDocument**, and then click **OK**.</span></span>  
  
21. <span data-ttu-id="4780c-152">En el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="4780c-152">In the **File** menu, click **Save All**.</span></span>  
  
 <span data-ttu-id="4780c-153">Continúe con [paso 12: configurar formas de orquestación](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="4780c-153">Proceed to [Step 12: Configure Orchestration Shapes](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4780c-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="4780c-154">See Also</span></span>  
 [<span data-ttu-id="4780c-155">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="4780c-155">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)