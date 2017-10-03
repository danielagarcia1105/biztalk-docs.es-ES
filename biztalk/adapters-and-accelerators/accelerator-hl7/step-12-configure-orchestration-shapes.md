---
title: "Paso 12: Configurar formas de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, orchestration shapes
- orchestrations, shapes
- message enrichment tutorial, orchestrations
ms.assetid: 9388254b-2841-4489-838e-de913ceff151
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7375912c49c431c67c7ff55025cd2821374b87b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-12-configure-orchestration-shapes"></a><span data-ttu-id="d595a-102">Paso 12: Configurar formas de orquestación</span><span class="sxs-lookup"><span data-stu-id="d595a-102">Step 12: Configure Orchestration Shapes</span></span>
<span data-ttu-id="d595a-103">En este paso, completa la configuración de las formas de orquestación con el fin de quitar las etiquetas inteligentes de configuración incompleta.</span><span class="sxs-lookup"><span data-stu-id="d595a-103">In this step, you complete the configuration of the orchestration shapes in order to remove the insufficient configuration smart tags.</span></span> <span data-ttu-id="d595a-104">Designe **DoorbellOutputMessage** como la salida del primer proceso de transformación, que designa **DoorbellMap.btm** como la asignación que se utiliza en ese proceso.</span><span class="sxs-lookup"><span data-stu-id="d595a-104">You designate **DoorbellOutputMessage** as the output of the first transform process, designating **DoorbellMap.btm** as the map used in that process.</span></span> <span data-ttu-id="d595a-105">A continuación, designe **DoorbellFinalMessage** como la salida del segundo proceso de transformación y agregue la expresión que enriquece el mensaje con los datos de campo adicional.</span><span class="sxs-lookup"><span data-stu-id="d595a-105">You then designate **DoorbellFinalMessage** as the output of the second transform process, and add the expression that enriches the message with additional field data.</span></span>  
  
 <span data-ttu-id="d595a-106">**Requisito previo:** [artículo de Knowledge Base 941261](http://support.microsoft.com/kb/941261) deben aplicarse antes de configurar la configuración de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="d595a-106">**Prerequisite:** [KB article 941261](http://support.microsoft.com/kb/941261) must be applied before setting up Orchestration Configuration.</span></span>  
  
### <a name="to-configure-orchestration-shapes"></a><span data-ttu-id="d595a-107">Para configurar formas de orquestación</span><span class="sxs-lookup"><span data-stu-id="d595a-107">To configure orchestration shapes</span></span>  
  
1.  <span data-ttu-id="d595a-108">En la vista de diseño de orquestación de [!INCLUDE[vs2012](../../includes/vs2012-md.md)], haga clic en el **ConstructMessage_1** forma.</span><span class="sxs-lookup"><span data-stu-id="d595a-108">On the orchestration Design view surface of [!INCLUDE[vs2012](../../includes/vs2012-md.md)], click the **ConstructMessage_1** shape.</span></span>  
  
2.  <span data-ttu-id="d595a-109">En el **propiedades** ventana, haga clic en el **mensajes construidos** propiedad, seleccione **DoorbellOutputMessage** desde la lista desplegable y, a continuación, presione  **Escriba**.</span><span class="sxs-lookup"><span data-stu-id="d595a-109">In the **Properties** window, click the **Messages Constructed** property, select **DoorbellOutputMessage** from the drop-down list, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="d595a-110">En la superficie de la vista de diseño de orquestación, haga clic en el **DoorbellTransform** forma dentro de la **ConstructMessage_1** forma.</span><span class="sxs-lookup"><span data-stu-id="d595a-110">On the orchestration Design view surface, click the **DoorbellTransform** shape inside of the **ConstructMessage_1** shape.</span></span> <span data-ttu-id="d595a-111">En el **propiedades** ventana, haga clic en **nombre de asignación**y, a continuación, haga clic en el botón de puntos suspensivos (...) en el campo de atributo.</span><span class="sxs-lookup"><span data-stu-id="d595a-111">In the **Properties** window, click **Map Name**, and then click the ellipsis (…) button in the attribute field.</span></span>  
  
4.  <span data-ttu-id="d595a-112">En el cuadro de diálogo Configuración de transformación, seleccione **mapa existente**.</span><span class="sxs-lookup"><span data-stu-id="d595a-112">In the Transform Configuration dialog box, select **Existing Map**.</span></span> <span data-ttu-id="d595a-113">En el **nombre completo de asignación** la lista desplegable, haga clic en **BTAHL7_Project.DoorbellMap**.</span><span class="sxs-lookup"><span data-stu-id="d595a-113">In the **Fully Qualified Map Name** drop-down list, click **BTAHL7_Project.DoorbellMap**.</span></span>  
  
5.  <span data-ttu-id="d595a-114">Haga clic en **origen** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="d595a-114">Click **Source** in the left pane.</span></span>  
  
6.  <span data-ttu-id="d595a-115">Haga clic en el cuadro vacío en **nombre de Variable** y haga clic en **DoorBellInputMessage** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d595a-115">Click the empty box under **Variable Name** and click **DoorBellInputMessage** from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="d595a-116">Haga clic en **destino** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="d595a-116">Click **Destination** in the left pane.</span></span>  
  
8.  <span data-ttu-id="d595a-117">Haga clic en el cuadro vacío en **nombre de Variable** y haga clic en **DoorbellOutputMessage** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d595a-117">Click the empty box under **Variable Name** and click **DoorbellOutputMessage** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="d595a-118">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="d595a-118">Click **OK** to save changes.</span></span>  
  
10. <span data-ttu-id="d595a-119">En la superficie de la vista de diseño de orquestación, haga clic en el **ConstructMessage_2** forma.</span><span class="sxs-lookup"><span data-stu-id="d595a-119">On the orchestration Design view surface, click the **ConstructMessage_2** shape.</span></span>  
  
11. <span data-ttu-id="d595a-120">En el **propiedades** ventana, haga clic en **mensajes construidos**, seleccione **DoorbellFinalMessage** desde la lista desplegable y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d595a-120">In the **Properties** window, click **Messages Constructed**, select **DoorbellFinalMessage** from the drop-down list, and then press **Enter**.</span></span>  
  
12. <span data-ttu-id="d595a-121">En la superficie de la vista de diseño de orquestación, haga clic en el **DoorbellFinalTransform** forma dentro de la **ConstructMessage_2** forma.</span><span class="sxs-lookup"><span data-stu-id="d595a-121">On the orchestration Design view surface, click the **DoorbellFinalTransform** shape inside of the **ConstructMessage_2** shape.</span></span> <span data-ttu-id="d595a-122">En el **propiedades** ventana, haga clic en **expresión**y, a continuación, haga clic en el botón de puntos suspensivos (...) para abrir el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d595a-122">In the **Properties** window, click **Expression**, and then click the ellipsis (…) button to open BizTalk Expression Editor.</span></span>  
  
13. <span data-ttu-id="d595a-123">En el Editor de expresiones de BizTalk, haga clic en el campo de texto y pegue el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="d595a-123">In BizTalk Expression Editor, click in the text field and paste the following text:</span></span>  
  
    ```  
    HeaderInfo = new System.Xml.XmlDocument();   
    HeaderInfo.LoadXml("<ns0:MSH_25_GLO_DEF xmlns:ns0=\"http://microsoft.com/HealthCare/HL7/2X\">  
        <MSH><MSH.2_EncodingCharacters>^~\\&</MSH.2_EncodingCharacters><MSH.3_SendingApplication>  
        <HD.0_NamespaceId>SrcApp</HD.0_NamespaceId><HD.1_UniversalId>SrcAppUid</HD.1_UniversalId>  
        </MSH.3_SendingApplication><MSH.4_SendingFacility><HD.0_NamespaceId>srcFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>srcFacUid</HD.1_UniversalId></MSH.4_SendingFacility><MSH.5_ReceivingApplication>  
        <HD.0_NamespaceId>dstApp</HD.0_NamespaceId><HD.1_UniversalId>dstAppUid</HD.1_UniversalId>  
        </MSH.5_ReceivingApplication><MSH.6_ReceivingFacility><HD.0_NamespaceId>dstFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>dstFacUid</HD.1_UniversalId></MSH.6_ReceivingFacility><MSH.7_DateTimeOfMessage>  
        <TS.1>200307092343</TS.1></MSH.7_DateTimeOfMessage><MSH.8_Security>sec</MSH.8_Security>  
        <MSH.9_MessageType><CM_MSG.0_MessageType>ADT</CM_MSG.0_MessageType>  
        <CM_MSG.1_TriggerEvent>A04</CM_MSG.1_TriggerEvent></MSH.9_MessageType>  
        <MSH.10_MessageControlId>msgid2134</MSH.10_MessageControlId><MSH.11_ProcessingId>  
        <PT.0_ProcessingId>P</PT.0_ProcessingId></MSH.11_ProcessingId><MSH.12_VersionId>  
       <VID_0_VersionId>2.2</VID_0_VersionId></MSH.12_VersionId></MSH></ns0:MSH_25_GLO_DEF>");  
  
    DoorbellFinalMessage.MSHSegment = HeaderInfo;  
    DoorbellFinalMessage.BodySegments = DoorbellOutputMessage;  
    DoorbellFinalMessage.ZSegments = "";  
  
    DoorbellFinalMessage(BTAHL7Schemas.MSH1) = 124;   
    DoorbellFinalMessage(BTAHL7Schemas.MessageEncoding) = 65001;  
    DoorbellFinalMessage(BTAHL7Schemas.MSH2) = "^~\\&";  
    DoorbellFinalMessage(BTAHL7Schemas.ParseError) = false;   
    DoorbellFinalMessage(BTAHL7Schemas.ZPartPresent) = false;  
    DoorbellFinalMessage(BTAHL7Schemas.SegmentDelimiter2Char) = true;  
  
    ```  
  
14. <span data-ttu-id="d595a-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d595a-124">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d595a-125">En la expresión "HeaderInfo.LoadXml", elimine los retornos de carro y espacios dentro de la expresión.</span><span class="sxs-lookup"><span data-stu-id="d595a-125">In the "HeaderInfo.LoadXml" expression, delete the carriage returns and spaces within the expression.</span></span> <span data-ttu-id="d595a-126">La instrucción de "HeaderInfo.LoadXml" debe estar en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="d595a-126">The "HeaderInfo.LoadXml" statement should be on one line.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d595a-127">El primer bloque de texto anterior es un ejemplo de un encabezado XML codificado de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="d595a-127">The first block of the preceding text is an example of a hard-coded XML header.</span></span> <span data-ttu-id="d595a-128">El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador requiere un segmento de encabezado.</span><span class="sxs-lookup"><span data-stu-id="d595a-128">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer requires a header segment.</span></span> <span data-ttu-id="d595a-129">Puede personalizar estos valores de encabezado según las necesidades de su entorno.</span><span class="sxs-lookup"><span data-stu-id="d595a-129">You can customize these header values according to the needs of your environment.</span></span> <span data-ttu-id="d595a-130">El segundo bloque de texto anterior define las tres partes de mensaje necesarias en un mensaje de varias partes.</span><span class="sxs-lookup"><span data-stu-id="d595a-130">The second block of the preceding text defines the three message parts required in a multipart message.</span></span> <span data-ttu-id="d595a-131">El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador requiere un mensaje de varias partes.</span><span class="sxs-lookup"><span data-stu-id="d595a-131">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer requires a multipart message.</span></span> <span data-ttu-id="d595a-132">El bloque anterior del texto de la tercero contiene las propiedades promocionadas que la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador examina con el fin de serializar un mensaje XML en un mensaje de archivo sin formato HL7.</span><span class="sxs-lookup"><span data-stu-id="d595a-132">The third block of the preceding text contains the promoted properties that the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer examines in order to serialize an XML message into an HL7 flat-file message.</span></span>  
  
 <span data-ttu-id="d595a-133">Continúe con [paso 13: crear y configurar puertos](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md).</span><span class="sxs-lookup"><span data-stu-id="d595a-133">Proceed to [Step 13: Create and Configure Ports](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d595a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d595a-134">See Also</span></span>  
 [<span data-ttu-id="d595a-135">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="d595a-135">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)