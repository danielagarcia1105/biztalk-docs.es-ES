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
ms.openlocfilehash: 69659359af123af7d9239241128cae06934d9a54
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="running-the-designer-extensibility-sample"></a>Ejecutar el ejemplo de extensibilidad del diseñador
El ejemplo de extensibilidad del diseñador utiliza dos dispositivos Extender de ejemplo para demostrar cómo puede proporcionar opciones de configuración de tiempo de diseño para los solucionadores personalizados y servicios itinerarios.  
  
 **Para ejecutar el ejemplo de extensibilidad del diseñador**  
  
1.  Inicie Visual Studio.  
  
2.  En Visual Studio, seleccione **New** en el **archivo** menú y, a continuación, haga clic en **proyecto**.  
  
3.  Seleccione la plantilla de biblioteca de clases de C#, tipo **ItineraryLibrary** en el **nombre** cuadro y, a continuación, haga clic en **Aceptar**.  
  
4.  En el Explorador de soluciones, haga clic en el proyecto ItineraryLibrary, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
5.  En el **nombre** , escriba **TestItinerary**, y, a continuación, presione ENTRAR.  
  
6.  En el cuadro de herramientas, haga clic en un elemento de modelo de rampa On y, a continuación, arrástrelo a la superficie de diseño.  
  
7.  En el cuadro de herramientas, haga clic en un elemento de modelo de servicio de itinerario y, a continuación, arrástrelo a la superficie de diseño.  
  
8.  En el cuadro de herramientas, haga clic en otro elemento de modelo de servicio de itinerario y, a continuación, arrástrelo a la superficie de diseño.  
  
9. En el cuadro de herramientas, haga clic en un elemento de modelo de rampa de Off y, a continuación, arrástrelo a la superficie de diseño.  
  
10. En el cuadro de herramientas, haga clic en la herramienta conector y, a continuación, arrastre una conexión entre el **OnRamp1** elemento del modelo y la **ItineraryService1** elemento del modelo.  
  
11. En el cuadro de herramientas, haga clic en la herramienta conector y, a continuación, arrastre una conexión entre el **ItineraryService1** elemento del modelo y la **ItineraryService2** elemento del modelo.  
  
12. En el cuadro de herramientas, haga clic en la herramienta conector y, a continuación, arrastre una conexión entre el **ItineraryService2** elemento del modelo y la **OffRamp1** elemento del modelo.  
  
13. Haga clic en el **OnRamp1** elemento del modelo y, a continuación, en la ventana Propiedades, establezca la propiedad de extensor **extensión de servicio de ESB en rampa**.  
  
14. Establecer el **aplicación de BizTalk** propiedad **Microsoft.Practices.ESB**.  
  
15. Establecer el **puerto de recepción** propiedad **OnRamp.Itinerary**.  
  
16. Haga clic en el **ItinearyService1** elemento del modelo y, a continuación, en la ventana Propiedades, establezca la **Extender** propiedad **extensión de servicio de itinerario de orquestación de ejemplo**.  
  
    > [!NOTE]
    >  Se trata de la extensión personalizada que se instala como parte del ejemplo de extensibilidad del diseñador. Permite agregar propiedades a la bolsa de propiedades que se pasa a un servicio de itinerarios basado en la orquestación.  
  
17. Establecer el **OtherValue** propiedad **1**.  
  
18. Establecer el **ServiceName** propiedad **Microsoft.Practices.ESB.Services.Routing**.  
  
19. Establecer el **SomeValue** propiedad **2**.  
  
20. Haga clic en el **resolución** colección de **ItineraryService1**y, a continuación, haga clic en **agregar nueva resolución**.  
  
21. Haga clic en **Resolver1**y, a continuación, en la ventana Propiedades, establezca la **implementación de la resolución** propiedad **ejemplo resolución extensión**.  
  
22. Establecer el **SomeResolverValue** propiedad **probar**y, a continuación, establezca la propiedad de versión en **1.0**.  
  
23. Haga clic en el **ItineraryService2** elemento del modelo y, a continuación, en la ventana Propiedades, establezca la **extensor del servicio de itinerario** propiedad **extensión de servicio fuera de rampa itinerario**.  
  
24. Establecer el **fuera de rampa** propiedad **OffRamp1 > controladores de envío**.  
  
25. Haga clic en el **OffRamp1** elemento del modelo y, a continuación, en la ventana Propiedades, establezca la **Extender** propiedad **extensión de servicio fuera de rampa ESB**.  
  
26. Establecer el **aplicación de BizTalk** propiedad **GlobalBank.ESB**.  
  
27. Establecer el **puerto de envío** propiedad **DynamicResolutionOneWay**.  
  
28. Haga clic en la superficie de diseño y, a continuación, haga clic en **Exportar modelo**.  
  
29. Examine el código XML generado.  
  
    > [!NOTE]
    >  Observe el **PropertyBag** elemento y las propiedades que contiene. Observe también la cadena de conexión de la resolución de ejemplo y cómo se configura en función de las propiedades especificadas.