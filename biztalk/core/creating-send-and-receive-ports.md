---
title: "Creación de envío y puertos de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, receive ports
- adapters [JD Edwards OneWorld adapters], receive ports
- creating, receive ports [JD Edwards OneWorld adapters]
- send ports, creating [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], send ports
- adapters [JD Edwards OneWorld adapters], transport properties
- JD Edwards OneWorld adapters, send ports
- JD Edwards OneWorld adapters, transport properties
- receive ports, creating [JD Edwards OneWorld adapters]
- creating, send ports [JD Edwards OneWorld adapters]
ms.assetid: fb4ca8b1-40d9-4beb-a791-554086f8ca98
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da4b117ca2d032ef1dc10731128acca903a51790
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating-send-and-receive-ports"></a><span data-ttu-id="c9f47-102">Creación de envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="c9f47-102">Creating Send and Receive Ports</span></span>
<span data-ttu-id="c9f47-103">Use los procedimientos siguientes para crear puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el adaptador de BizTalk para JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="c9f47-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="creating-a-port"></a><span data-ttu-id="c9f47-104">Creación de un puerto</span><span class="sxs-lookup"><span data-stu-id="c9f47-104">Creating a Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="c9f47-105">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="c9f47-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="c9f47-106">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c9f47-107">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**y, a continuación, expanda el aplicación para la que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c9f47-107">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="c9f47-108">Haga clic en **puertos de envío** y haga clic en **New**y, a continuación, haga clic en **puerto de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-108">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="c9f47-109">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9f47-109">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="c9f47-110">En el **nombre** , escriba un nombre de puerto de envío (por ejemplo, `SSOSendToJDE OneWorld`).</span><span class="sxs-lookup"><span data-stu-id="c9f47-110">In the **Name** box, type a send port name (for example, `SSOSendToJDE OneWorld`).</span></span>  
  
    -   <span data-ttu-id="c9f47-111">Desde el **tipo** lista desplegable, seleccione **JDEdwards**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-111">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="c9f47-112">Desde el **controlador de envío** lista desplegable, seleccione la dirección del controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="c9f47-112">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
    -   <span data-ttu-id="c9f47-113">Para el **canalización de envío**, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-113">For the **Send Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    -   <span data-ttu-id="c9f47-114">Para el **canalización de recepción**, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-114">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
5.  <span data-ttu-id="c9f47-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-115">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="c9f47-116">Crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="c9f47-116">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="c9f47-117">Para crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="c9f47-117">To create a receive port</span></span>  
  
1.  <span data-ttu-id="c9f47-118">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-118">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c9f47-119">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**y, a continuación, expanda el aplicación para la que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c9f47-119">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="c9f47-120">Haga clic en **puertos de recepción** y haga clic en **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-120">Right-click **Receive Ports** and click **New**, and then click **One-way Receive Port**.</span></span>  
  
     <span data-ttu-id="c9f47-121">En el **propiedades del puerto de recepción unidireccional** pantalla, en la **nombre** , escriba `ReceiveFromHttp`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-121">On the **One-Way Receive Port Properties** screen, in the **Name** field, type `ReceiveFromHttp`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="c9f47-122">Escriba la siguiente información en el **propiedades del puerto de recepción unidireccional** ventana:</span><span class="sxs-lookup"><span data-stu-id="c9f47-122">Enter the following information in the **One-way Receive Port Properties** window:</span></span>  
  
    -   <span data-ttu-id="c9f47-123">En el **nombre** , escriba `ReceiveFromHTTP`.</span><span class="sxs-lookup"><span data-stu-id="c9f47-123">In the **Name** field, type `ReceiveFromHTTP`.</span></span>  
  
    -   <span data-ttu-id="c9f47-124">Para el **tipo de transporte**, seleccione **HTTP**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-124">For the **Transport Type**, select **HTTP**.</span></span>  
  
5.  <span data-ttu-id="c9f47-125">Haga clic en el botón de puntos suspensivos (…) de la dirección (URI).</span><span class="sxs-lookup"><span data-stu-id="c9f47-125">Click the ellipsis (…) button in the address (URI).</span></span>  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  <span data-ttu-id="c9f47-126">Establezca el directorio virtual más la extensión ISAPI, /mySSODemo/BTSHTTPReceive.dll.</span><span class="sxs-lookup"><span data-stu-id="c9f47-126">Set the Virtual directory plus ISAPI extension, /mySSODemo/BTSHTTPReceive.dll.</span></span>  
  
    2.  <span data-ttu-id="c9f47-127">Seleccione **devolver controlador de correlación en caso de éxito**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-127">Select **Return correlation handle on success**.</span></span>  
  
    3.  <span data-ttu-id="c9f47-128">Seleccione **Use Single Sign-On**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-128">Select **Use Single Sign-On**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="c9f47-129">En el **controlador de recepción** lista desplegable, seleccione **BizTalkServerIsolatedHost**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-129">In the **Receive Handler** drop-down list, select **BizTalkServerIsolatedHost**.</span></span>  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  <span data-ttu-id="c9f47-130">Para el **canalización de recepción**, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c9f47-130">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f47-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9f47-131">See Also</span></span>  
 <span data-ttu-id="c9f47-132">[Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="c9f47-132">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 <span data-ttu-id="c9f47-133">[Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="c9f47-133">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="c9f47-134">Seguridad en el adaptador</span><span class="sxs-lookup"><span data-stu-id="c9f47-134">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)