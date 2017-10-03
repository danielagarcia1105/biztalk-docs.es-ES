---
title: "Crear un servicio de itinerarios personalizado mediante una orquestación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723c0bc93192267f404d42e7fe859bb37ea59895
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a>Crear un servicio de itinerarios personalizado mediante una orquestación de BizTalk
El marco de trabajo itinerario que forma parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la ejecución de pasos itinerarios con orquestaciones. Puede implementar un servicio personalizado de itinerarios como una orquestación de Microsoft BizTalk Server según los requisitos funcionales, que pueden incluir lo siguiente:  
  
-   Varias invocaciones de servicio (como se muestra en el [instalar y ejecutar el ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))  
  
-   Correlación de mediación y mensaje de protocolo (por ejemplo, HTTP-MQSeries)  
  
-   Las decisiones de enrutamiento complejas basan en enriquecimiento del mensaje de datos externos de orígenes  
  
-   Lógica de procesamiento de negocios  
  
 Cada servicio itinerario implementado con una orquestación de BizTalk Server es responsable de lo siguiente:  
  
-   Excepciones y control de errores mediante el marco para la administración de excepciones de ESB o controladores de excepción personalizada opcional que admiten el reenvío (itinerarios unidireccionales)  
  
-   Avanzar el itinerario y publicar los mensajes salientes a través de BizTalk Server para que pueda ejecutar el siguiente paso de servicio itinerarios  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a>Para crear un servicio de itinerarios personalizado mediante una orquestación de BizTalk Server  
  
1.  Crear nuevo proyecto de BizTalk Server que contiene una nueva orquestación; Por ejemplo, MyCustomeItineraryService.odx.  
  
2.  Agregue referencias a los ensamblados siguientes:  
  
    -   **Microsoft.Practices.ESB.Itinerary**  
  
    -   **Microsoft.Practices.ESB.Itinerary.Schemas**  
  
    -   **Microsoft.Practices.ESB.ExceptionHandling**  
  
    -   **Microsoft.Practices.ESB.ExceptionHandling.Faults**  
  
3.  Definir un enlace directo lógico puerto de recepción y una forma recepción activada en la orquestación.  
  
4.  Definir un filtro de suscripción para activar la orquestación del contexto del mensaje itinerarios para que la orquestación ejecuta la **MyCustomItineraryService** paso. El código siguiente muestra un ejemplo de un filtro adecuado.  
  
    ```csharp  
    (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
        == "MyCustomItineraryService")   
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
        == "Orchestration")  
    ```  
  
5.  Definir una orquestación de tipo **Microsoft.Practices.ESB.Itinerary.ItineraryStep**. Agregar una actividad de expresión a la orquestación que rellena esta variable, como se muestra en el código siguiente.  
  
    ```csharp  
    // Retrieve the current itinerary step.  
    itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
    step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
    itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
    step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
    ```  
  
6.  Agregue su implementación personalizada para el itinerario que crea el mensaje de salida para los siguientes pasos itinerarios; Por ejemplo, OutboundMsg.  
  
7.  Avanzar el itinerario mediante la siguiente actividad de expresión que utiliza el contexto del mensaje de mensaje entrante.  
  
    ```csharp  
    OutboundMessage(*) = InboundMessage(*);   
    itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
    ```  
  
8.  Enviar el mensaje saliente con el itinerario actualizado a través de un puerto de envío de enlace directo para activar el servicio de itinerarios siguiente.  
  
 Para obtener más información acerca de cómo implementar un servicio personalizado de itinerarios mediante orquestaciones de BizTalk Server, vea [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) y [instalar y ejecutar la dispersión y recopilación Ejemplo](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).