---
title: 'Paso 15: Configurar el envío y puertos de recepción | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, ports
ms.assetid: d532b196-473e-4c8f-b4ed-acef674fc698
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 020d83db1db86f9ff9ce116578cf58f19ba08241
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206460"
---
# <a name="step-15-configure-the-send-and-receive-ports"></a><span data-ttu-id="b959e-102">Paso 15: Configurar el envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="b959e-102">Step 15: Configure the Send and Receive Ports</span></span>
<span data-ttu-id="b959e-103">En los pasos anteriores, creó un envío lógico y puerto de recepción mediante el Diseñador de orquestaciones y establece el enlace de puerto para "Especificar más tarde".</span><span class="sxs-lookup"><span data-stu-id="b959e-103">In previous steps, you created a logical send and receive port using Orchestration Designer and set the port binding to "Specify Later".</span></span> <span data-ttu-id="b959e-104">En este paso, use el Explorador de BizTalk para finalizar la configuración del puerto definiendo las ubicaciones físicas de origen y de destino y enlazar los puertos físicos a los puertos lógicos que creó en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="b959e-104">In this step, you use BizTalk Explorer to finalize the port configuration by defining the physical source and destination locations and binding the physical ports to the logical ports that you created in the orchestration.</span></span>  
  
## <a name="configure-the-send-and-receive-ports"></a><span data-ttu-id="b959e-105">Configurar el envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="b959e-105">Configure the send and receive ports</span></span>  
  
1.  <span data-ttu-id="b959e-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Aplicación de BizTalk 1**.</span><span class="sxs-lookup"><span data-stu-id="b959e-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="b959e-107">Haga clic en **puertos de envío**, elija Nuevo y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="b959e-107">Right-click **Send Ports**, point to New, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="b959e-108">En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba **MLLPSendPort**.</span><span class="sxs-lookup"><span data-stu-id="b959e-108">In the Send Port Properties dialog box, in the **Name** box, type **MLLPSendPort**.</span></span>  
  
4.  <span data-ttu-id="b959e-109">Para **tipo**, seleccione **MLLP**.</span><span class="sxs-lookup"><span data-stu-id="b959e-109">For **Type**, select **MLLP**.</span></span>  
  
5.  <span data-ttu-id="b959e-110">Haga clic en el **configurar** situado a la derecha de la **tipo** campo.</span><span class="sxs-lookup"><span data-stu-id="b959e-110">Click the **Configure** button to the right of the **Type** field.</span></span>  
  
6.  <span data-ttu-id="b959e-111">En el cuadro de diálogo Propiedades de transporte de MLLP para **nombre de la conexión** escriba **MLLPConnection**.</span><span class="sxs-lookup"><span data-stu-id="b959e-111">In the MLLP Transport Properties dialog box, for **Connection Name** enter **MLLPConnection**.</span></span> <span data-ttu-id="b959e-112">Para **Host** escriba **localhost**.</span><span class="sxs-lookup"><span data-stu-id="b959e-112">For **Host** enter **localhost**.</span></span> <span data-ttu-id="b959e-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b959e-113">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="b959e-114">En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b959e-114">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="b959e-115">En la consola de administración, haga clic en **MLLPSendPort** de puerto y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="b959e-115">In the Administration Console, right-click **MLLPSendPort** port, and then click **Start**.</span></span>  
  
9. <span data-ttu-id="b959e-116">Expanda **configuración de plataforma**, haga clic en **instancias de Host**, haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="b959e-116">Expand **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Start**.</span></span> <span data-ttu-id="b959e-117">Si ya se está ejecutando el host, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="b959e-117">If the host is already running, click **Restart**.</span></span>  
  
10. <span data-ttu-id="b959e-118">Haga clic en **orquestaciones**, haga clic en **BTAHL7_Project.Doorbell_Orchestration**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b959e-118">Click **Orchestrations**, right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="b959e-119">En el cuadro de diálogo Propiedades de orquestación, en el árbol de consola, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="b959e-119">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
12. <span data-ttu-id="b959e-120">En el **enlaces** panel, para **Host**, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="b959e-120">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span>  
  
13. <span data-ttu-id="b959e-121">Para **SOAPReceivePort**, seleccione **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** en el **puertos de recepción** columna.</span><span class="sxs-lookup"><span data-stu-id="b959e-121">For **SOAPReceivePort**, select **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** in the **Receive Ports** column.</span></span>  
  
14. <span data-ttu-id="b959e-122">Para **MLLPSendPort**, seleccione **MLLPSendPort** en el **grupos de puertos de envío y puertos de envío** columna.</span><span class="sxs-lookup"><span data-stu-id="b959e-122">For **MLLPSendPort**, select **MLLPSendPort** in the **Send Ports/Send Port Groups** column.</span></span>  
  
15. <span data-ttu-id="b959e-123">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b959e-123">Click **OK** to save the changes.</span></span>  
  
## <a name="msh-5-and-msh-6"></a><span data-ttu-id="b959e-124">MSH 5 y 6 de MSH</span><span class="sxs-lookup"><span data-stu-id="b959e-124">MSH 5 and MSH 6</span></span>  
 <span data-ttu-id="b959e-125">Los campos de encabezado de MSH 5 y 6 de MSH contienen la aplicación de destino y la utilidad, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b959e-125">The MSH 5 and MSH 6 header fields contain the destination application and facility, respectively.</span></span> <span data-ttu-id="b959e-126">En el Explorador de configuración, puede especificar los valores para cada uno de los tres componentes de MSH 5 y 6 de MSH, en casos si desea que la información de destino en el mensaje va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="b959e-126">In Configuration Explorer, you can specify the values for each of the three components of MSH 5 and MSH 6, in cases when you want the destination information in the message to be changed.</span></span> <span data-ttu-id="b959e-127">Este es un escenario probable cuando el mensaje original no incluye información específica de la entidad.</span><span class="sxs-lookup"><span data-stu-id="b959e-127">This is a likely scenario when the original message does not include party-specific information.</span></span> <span data-ttu-id="b959e-128">Este paso es aplicable en el modelo declarativo (publicador y suscriptor).</span><span class="sxs-lookup"><span data-stu-id="b959e-128">This step is applicable in the declarative (publisher/subscriber) model.</span></span> <span data-ttu-id="b959e-129">Realice este paso si es aplicable en su entorno.</span><span class="sxs-lookup"><span data-stu-id="b959e-129">You perform this step if it is applicable in your environment.</span></span> <span data-ttu-id="b959e-130">Para obtener más información acerca de cómo establecer estos valores, consulte [partes - Explorador de configuración de BTAHL7](parties-tab.md).</span><span class="sxs-lookup"><span data-stu-id="b959e-130">For more information about setting these values, see [Parties - BTAHL7 Configuration Explorer](parties-tab.md).</span></span>  
  
 <span data-ttu-id="b959e-131">Continúe con [paso 16: iniciar la orquestación](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="b959e-131">Proceed to [Step 16: Start the Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b959e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b959e-132">See Also</span></span>  
 [<span data-ttu-id="b959e-133">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="b959e-133">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)