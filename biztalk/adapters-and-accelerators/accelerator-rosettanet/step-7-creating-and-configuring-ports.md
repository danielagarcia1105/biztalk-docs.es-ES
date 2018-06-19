---
title: 'Paso 7: Crear y configurar puertos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
- private process tutorial, configuring ports
ms.assetid: c00344c6-506a-4560-a948-e5fed2b9fd58
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44a9696f907928f31a740e4d8545567921a82df9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965242"
---
# <a name="step-7-creating-and-configuring-ports"></a><span data-ttu-id="1e579-102">Paso 7: Crear y configurar puertos</span><span class="sxs-lookup"><span data-stu-id="1e579-102">Step 7: Creating and Configuring Ports</span></span>
<span data-ttu-id="1e579-103">En este paso, se creará y configurará los puertos que se usan para comunicarse con los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="1e579-103">In this step, you create and configure the ports you use to communicate with business processes.</span></span> <span data-ttu-id="1e579-104">Cada puerto tiene un tipo, la dirección y la propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="1e579-104">Each port has a type, direction, and binding property.</span></span> <span data-ttu-id="1e579-105">Estas propiedades establecen la dirección y el patrón de comunicación, la ubicación de donde se envía o recibe el mensaje y cómo se produce la comunicación.</span><span class="sxs-lookup"><span data-stu-id="1e579-105">These properties establish the direction and pattern of communication, the location of where the message is sent or received, and how the communication occurs.</span></span>  
  
### <a name="to-create-a-logical-send-port"></a><span data-ttu-id="1e579-106">Para crear un puerto de envío lógico</span><span class="sxs-lookup"><span data-stu-id="1e579-106">To create a logical send port</span></span>  
  
1.  <span data-ttu-id="1e579-107">En Visual Studio, en el cuadro de herramientas, arrastre el **puerto** dar forma a la superficie de diseño de orquestación y colóquela en la **superficie para el puerto** para abrir el **Asistente de configuración de puerto**.</span><span class="sxs-lookup"><span data-stu-id="1e579-107">In Visual Studio, from the Toolbox, drag the **Port** shape to the orchestration design surface and drop it on the **Port Surface** to open the **Port Configuration Wizard**.</span></span>  
  
2.  <span data-ttu-id="1e579-108">En el **Asistente para configuración de puertos** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e579-108">On the **Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="1e579-109">En el **propiedades de puerto** página, en la **nombre** , escriba **ContosoSQLReqResponsePort**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e579-109">On the **Port Properties** page, in the **Name** box, type **ContosoSQLReqResponsePort**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="1e579-110">En el **seleccionar un tipo de puerto** página, en la **nombre de tipo de puerto** , escriba **ContosoSQLReqResponsePortName**.</span><span class="sxs-lookup"><span data-stu-id="1e579-110">On the **Select a Port Type** page, in the **Port Type Name** box, type **ContosoSQLReqResponsePortName**.</span></span>  
  
5.  <span data-ttu-id="1e579-111">Para **patrón de comunicación**, seleccione **solicitud-respuesta**.</span><span class="sxs-lookup"><span data-stu-id="1e579-111">For **Communication Pattern**, select **Request-Response**.</span></span>  
  
6.  <span data-ttu-id="1e579-112">Para **restricciones de acceso**, seleccione **interno: limitado a este proyecto**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e579-112">For **Access Restrictions**, select **Internal - limited to this project**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="1e579-113">En el **enlace de puerto** página, seleccione **enviaré una solicitud y recibiré una respuesta**, deje el **enlace de puerto** opción establecida en **especificar más tarde**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e579-113">On the **Port Binding** page, select **I'll be sending a request and receiving a response**, leave the **Port Binding** option set to **Specify Later**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="1e579-114">Haga clic en **finalizar** para crear el puerto.</span><span class="sxs-lookup"><span data-stu-id="1e579-114">Click **Finish** to create the port.</span></span>  
  
### <a name="to-change-the-variable-type-for-the-orchestration-ports"></a><span data-ttu-id="1e579-115">Para cambiar el tipo de variable para los puertos de orquestación</span><span class="sxs-lookup"><span data-stu-id="1e579-115">To change the variable type for the orchestration ports</span></span>  
  
1.  <span data-ttu-id="1e579-116">En la Vista orquestación, expanda **tipos**, expanda **tipos de puerto**, expanda **ContosoSQLReqResponsePortName**, expanda **Operation_1**, y, a continuación, seleccione **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="1e579-116">In Orchestration View, expand **Types**, expand **Port Types**, expand **ContosoSQLReqResponsePortName**, expand **Operation_1**, and then select **Request**.</span></span>  
  
2.  <span data-ttu-id="1e579-117">En la ventana Propiedades, seleccione la **tipo de mensaje** propiedad, expanda **esquemas** y, a continuación, haga clic en  **\<seleccionar del ensamblado mencionado\>**  .</span><span class="sxs-lookup"><span data-stu-id="1e579-117">In the Properties window, select the **Message Type** property, expand **Schemas** and then click **\<Select from referenced assembly\>**.</span></span>  
  
3.  <span data-ttu-id="1e579-118">En el cuadro de diálogo Seleccionar tipo de artefacto, haga clic en **ContosoPriceAndAvailability**.</span><span class="sxs-lookup"><span data-stu-id="1e579-118">In the Select Artifact Type dialog box, click **ContosoPriceAndAvailability**.</span></span>  
  
4.  <span data-ttu-id="1e579-119">En el panel derecho, seleccione **rootPriceRequest**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e579-119">In the right pane, select **rootPriceRequest**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="1e579-120">En la Vista orquestación, en **Operation_1**, seleccione **respuesta** para el **ContosoSQLReqResponsePortName** tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="1e579-120">In Orchestration View, under **Operation_1**, select **Response** for the **ContosoSQLReqResponsePortName** port type.</span></span>  
  
6.  <span data-ttu-id="1e579-121">En la ventana Propiedades, seleccione la **tipo de mensaje** propiedad, expanda **esquemas** y, a continuación, haga clic en \< **seleccionar del ensamblado mencionado\>**  .</span><span class="sxs-lookup"><span data-stu-id="1e579-121">In the Properties window, select the **Message Type** property, expand **Schemas** and then click \<**Select from referenced assembly\>**.</span></span>  
  
7.  <span data-ttu-id="1e579-122">En el **Seleccionar tipo de artefacto** cuadro de diálogo, haga clic en **ContosoPriceAndAvailability**.</span><span class="sxs-lookup"><span data-stu-id="1e579-122">In the **Select Artifact Type** dialog box, click **ContosoPriceAndAvailability**.</span></span>  
  
8.  <span data-ttu-id="1e579-123">En el panel derecho, seleccione **rootPriceResponse**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e579-123">In the right pane, select **rootPriceResponse**, and then click **OK**.</span></span>  
  
### <a name="to-connect-the-ports-to-the-receive-shapes"></a><span data-ttu-id="1e579-124">Para conectar los puertos a las formas de recepción</span><span class="sxs-lookup"><span data-stu-id="1e579-124">To connect the ports to the Receive shapes</span></span>  
  
1.  <span data-ttu-id="1e579-125">En la superficie de diseño de orquestación, seleccione la **Send_1** forma.</span><span class="sxs-lookup"><span data-stu-id="1e579-125">On the orchestration design surface, select the **Send_1** shape.</span></span>  
  
2.  <span data-ttu-id="1e579-126">En la ventana Propiedades, seleccione la **mensaje** propiedad y, a continuación, seleccione **Contoso3A2RequestMessage** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1e579-126">In the Properties window, select the **Message** property, and then select **Contoso3A2RequestMessage** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="1e579-127">Conectar el **ContosoSQLReqResponsePort** seleccionando el indicador verde junto a la **solicitar** etiqueta y arrastrándolo hasta el indicador verde de la **Send_1** forma.</span><span class="sxs-lookup"><span data-stu-id="1e579-127">Connect the **ContosoSQLReqResponsePort** by selecting the green handle next to the **Request** label and dragging it to the green handle on the **Send_1** shape.</span></span>  
  
4.  <span data-ttu-id="1e579-128">En la superficie de diseño de orquestación, seleccione la **Receive_1** forma.</span><span class="sxs-lookup"><span data-stu-id="1e579-128">On the orchestration design surface, select the **Receive_1** shape.</span></span>  
  
5.  <span data-ttu-id="1e579-129">En la ventana Propiedades, seleccione la **mensaje** propiedad y, a continuación, seleccione **Contoso3A2ResponseMessage** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1e579-129">In the Properties window, select the **Message** property, and then select **Contoso3A2ResponseMessage** from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="1e579-130">Conectar el **ContosoSQLReqResponsePort** seleccionando el indicador verde junto a la **respuesta** etiqueta y arrastrándolo hasta el indicador verde de la **Receive_1** forma.</span><span class="sxs-lookup"><span data-stu-id="1e579-130">Connect the **ContosoSQLReqResponsePort** by selecting the green handle next to the **Response** label and dragging it to the green handle on the **Receive_1** shape.</span></span>  
  
7.  <span data-ttu-id="1e579-131">En el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="1e579-131">In the **File** Menu, click **Save All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e579-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e579-132">See Also</span></span>  
 [<span data-ttu-id="1e579-133">Paso 8: Creación e implementación de la orquestación de Contoso</span><span class="sxs-lookup"><span data-stu-id="1e579-133">Step 8: Building and Deploying the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)