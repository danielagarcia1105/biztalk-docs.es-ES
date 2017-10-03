---
title: "Ejecutar el ejemplo de extensibilidad del diseñador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05ac3b50-5bf2-4566-8654-472391476d1f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b26c483568e1ceb05679d7548721c1cce818fde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-designer-extensibility-sample"></a><span data-ttu-id="0b720-102">Ejecutar el ejemplo de extensibilidad del diseñador</span><span class="sxs-lookup"><span data-stu-id="0b720-102">Running the Designer Extensibility Sample</span></span>
<span data-ttu-id="0b720-103">El ejemplo de extensibilidad del diseñador utiliza dos dispositivos Extender de ejemplo para demostrar cómo puede proporcionar opciones de configuración de tiempo de diseño para los solucionadores personalizados y servicios itinerarios.</span><span class="sxs-lookup"><span data-stu-id="0b720-103">The Designer Extensibility sample uses two sample extenders to demonstrate how you can provide design-time configuration options for custom resolvers and for itinerary services.</span></span>  
  
 <span data-ttu-id="0b720-104">**Para ejecutar el ejemplo de extensibilidad del diseñador**</span><span class="sxs-lookup"><span data-stu-id="0b720-104">**To run the Designer Extensibility sample**</span></span>  
  
1.  <span data-ttu-id="0b720-105">Inicie [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b720-105">Start [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0b720-106">En Visual Studio, seleccione **New** en el **archivo** menú y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0b720-106">In Visual Studio, point to **New** on the **File** menu, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="0b720-107">Seleccione la plantilla de biblioteca de clases de C#, tipo **ItineraryLibrary** en el **nombre** cuadro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0b720-107">Select the C# Class Library template, type **ItineraryLibrary** in the **Name** box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="0b720-108">En el Explorador de soluciones, haga clic en el proyecto ItineraryLibrary, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="0b720-108">In Solution Explorer, right-click the ItineraryLibrary project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
5.  <span data-ttu-id="0b720-109">En el **nombre** , escriba **TestItinerary**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0b720-109">In the **Name** box, type **TestItinerary**, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="0b720-110">En el cuadro de herramientas, haga clic en un elemento de modelo de rampa On y, a continuación, arrástrelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="0b720-110">In the Toolbox, click an On-Ramp model element, and then drag it to the design surface.</span></span>  
  
7.  <span data-ttu-id="0b720-111">En el cuadro de herramientas, haga clic en un elemento de modelo de servicio de itinerario y, a continuación, arrástrelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="0b720-111">In the Toolbox, click an Itinerary Service model element, and then drag it to the design surface.</span></span>  
  
8.  <span data-ttu-id="0b720-112">En el cuadro de herramientas, haga clic en otro elemento de modelo de servicio de itinerario y, a continuación, arrástrelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="0b720-112">In the Toolbox, click another Itinerary Service model element, and then drag it to the design surface.</span></span>  
  
9. <span data-ttu-id="0b720-113">En el cuadro de herramientas, haga clic en un elemento de modelo de rampa de Off y, a continuación, arrástrelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="0b720-113">In the Toolbox, click an Off-Ramp model element, and then drag it to the design surface.</span></span>  
  
10. <span data-ttu-id="0b720-114">En el cuadro de herramientas, haga clic en la herramienta conector y, a continuación, arrastre una conexión entre el **OnRamp1** elemento del modelo y la **ItineraryService1** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="0b720-114">In the Toolbox, click the Connector tool, and then drag a connection between the **OnRamp1** model element and the **ItineraryService1** model element.</span></span>  
  
11. <span data-ttu-id="0b720-115">En el cuadro de herramientas, haga clic en la herramienta conector y, a continuación, arrastre una conexión entre el **ItineraryService1** elemento del modelo y la **ItineraryService2** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="0b720-115">In the Toolbox, click the Connector tool, and then drag a connection between the **ItineraryService1** model element and the **ItineraryService2** model element.</span></span>  
  
12. <span data-ttu-id="0b720-116">En el cuadro de herramientas, haga clic en la herramienta conector y, a continuación, arrastre una conexión entre el **ItineraryService2** elemento del modelo y la **OffRamp1** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="0b720-116">In the Toolbox, click the Connector tool, and then drag a connection between the **ItineraryService2** model element and the **OffRamp1** model element.</span></span>  
  
13. <span data-ttu-id="0b720-117">Haga clic en el **OnRamp1** elemento del modelo y, a continuación, en la ventana Propiedades, establezca la propiedad de extensor **extensión de servicio de ESB en rampa**.</span><span class="sxs-lookup"><span data-stu-id="0b720-117">Click the **OnRamp1** model element, and then in the Properties window, set the Extender property to **On-Ramp ESB Service Extension**.</span></span>  
  
14. <span data-ttu-id="0b720-118">Establecer el **aplicación de BizTalk** propiedad **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="0b720-118">Set the **BizTalk Application** property to **Microsoft.Practices.ESB**.</span></span>  
  
15. <span data-ttu-id="0b720-119">Establecer el **puerto de recepción** propiedad **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="0b720-119">Set the **Receive Port** property to **OnRamp.Itinerary**.</span></span>  
  
16. <span data-ttu-id="0b720-120">Haga clic en el **ItinearyService1** elemento del modelo y, a continuación, en la ventana Propiedades, establezca la **Extender** propiedad **extensión de servicio de itinerario de orquestación de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="0b720-120">Click the **ItinearyService1** model element, and then in the Properties window, set the **Extender** property to **Sample Orchestration Itinerary Service Extension**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b720-121">Se trata de la extensión personalizada que se instala como parte del ejemplo de extensibilidad del diseñador.</span><span class="sxs-lookup"><span data-stu-id="0b720-121">This is the custom extension installed as part of the Designer Extensibility sample.</span></span> <span data-ttu-id="0b720-122">Permite agregar propiedades a la bolsa de propiedades que se pasa a un servicio de itinerarios basado en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0b720-122">It allows you to add properties to the property bag passed to an orchestration-based itinerary service.</span></span>  
  
17. <span data-ttu-id="0b720-123">Establecer el **OtherValue** propiedad **1**.</span><span class="sxs-lookup"><span data-stu-id="0b720-123">Set the **OtherValue** property to **1**.</span></span>  
  
18. <span data-ttu-id="0b720-124">Establecer el **ServiceName** propiedad **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="0b720-124">Set the **ServiceName** property to **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
19. <span data-ttu-id="0b720-125">Establecer el **SomeValue** propiedad **2**.</span><span class="sxs-lookup"><span data-stu-id="0b720-125">Set the **SomeValue** property to **2**.</span></span>  
  
20. <span data-ttu-id="0b720-126">Haga clic en el **resolución** colección de **ItineraryService1**y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="0b720-126">Right-click the **Resolver** collection of **ItineraryService1**, and then click **Add new Resolver**.</span></span>  
  
21. <span data-ttu-id="0b720-127">Haga clic en **Resolver1**y, a continuación, en la ventana Propiedades, establezca la **implementación de la resolución** propiedad **ejemplo resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="0b720-127">Click **Resolver1**, and then in the Properties window, set the **Resolver Implementation** property to **Sample Resolver Extension**.</span></span>  
  
22. <span data-ttu-id="0b720-128">Establecer el **SomeResolverValue** propiedad **probar**y, a continuación, establezca la propiedad de versión en **1.0**.</span><span class="sxs-lookup"><span data-stu-id="0b720-128">Set the **SomeResolverValue** property to **test**, and then set the version property to **1.0**.</span></span>  
  
23. <span data-ttu-id="0b720-129">Haga clic en el **ItineraryService2** elemento del modelo y, a continuación, en la ventana Propiedades, establezca la **extensor del servicio de itinerario** propiedad **extensión de servicio fuera de rampa itinerario**.</span><span class="sxs-lookup"><span data-stu-id="0b720-129">Click the **ItineraryService2** model element, and then in the Properties window, set the **Itinerary Service Extender** property to **Off-Ramp Itinerary Service Extension**.</span></span>  
  
24. <span data-ttu-id="0b720-130">Establecer el **fuera de rampa** propiedad **OffRamp1 > controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="0b720-130">Set the **Off-Ramp** property to **OffRamp1 > Send Handlers**.</span></span>  
  
25. <span data-ttu-id="0b720-131">Haga clic en el **OffRamp1** elemento del modelo y, a continuación, en la ventana Propiedades, establezca la **Extender** propiedad **extensión de servicio fuera de rampa ESB**.</span><span class="sxs-lookup"><span data-stu-id="0b720-131">Click the **OffRamp1** model element, and then in the Properties window, set the **Extender** property to **Off-Ramp ESB Service Extension**.</span></span>  
  
26. <span data-ttu-id="0b720-132">Establecer el **aplicación de BizTalk** propiedad **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="0b720-132">Set the **BizTalk Application** property to **GlobalBank.ESB**.</span></span>  
  
27. <span data-ttu-id="0b720-133">Establecer el **puerto de envío** propiedad **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="0b720-133">Set the **Send Port** property to **DynamicResolutionOneWay**.</span></span>  
  
28. <span data-ttu-id="0b720-134">Haga clic en la superficie de diseño y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="0b720-134">Right-click the design surface, and then click **Export Model**.</span></span>  
  
29. <span data-ttu-id="0b720-135">Examine el código XML generado.</span><span class="sxs-lookup"><span data-stu-id="0b720-135">Examine the generated XML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b720-136">Observe el **PropertyBag** elemento y las propiedades que contiene.</span><span class="sxs-lookup"><span data-stu-id="0b720-136">Notice the **PropertyBag** element and the properties it contains.</span></span> <span data-ttu-id="0b720-137">Observe también la cadena de conexión de la resolución de ejemplo y cómo se configura en función de las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="0b720-137">Also notice the Sample resolver connection string and how it was configured based on the properties entered.</span></span>