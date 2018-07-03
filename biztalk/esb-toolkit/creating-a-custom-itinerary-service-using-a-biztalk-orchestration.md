---
title: Creación de un servicio de itinerarios personalizado mediante una orquestación de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa36acc84358a8e91a0b9daaa4370270fb5860b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988541"
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a>Creación de un servicio de itinerarios personalizado mediante una orquestación de BizTalk
El marco de itinerarios que forma parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la ejecución de pasos de itinerarios mediante orquestaciones. Puede implementar un servicio de itinerarios personalizado como una orquestación de Microsoft BizTalk Server según sus requisitos funcionales, que pueden incluir lo siguiente:  
  
- Varias invocaciones de servicio (tal como lo demuestra el [instalar y ejecutar el ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))  
  
- Correlación de mediación y mensaje de protocolo (por ejemplo, HTTP-MQSeries)  
  
- Decisiones de enrutamiento complejas basan en enriquecimiento de mensajes de datos externos de orígenes  
  
- Lógica de procesamiento empresarial  
  
  Cada servicio de itinerarios implementado mediante una orquestación de BizTalk Server es responsable de lo siguiente:  
  
- Errores y excepciones con el marco de control de excepciones de ESB o controladores de excepción personalizada opcional que admiten el reenvío (itinerarios unidireccionales)  
  
- Avanzar el itinerario y la publicación de mensajes salientes a través de BizTalk Server para que puedan ejecutar el siguiente paso de servicio de itinerarios  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a>Para crear un servicio de itinerarios personalizado mediante una orquestación de BizTalk Server  
  
1. Crear nuevo proyecto de BizTalk Server que contiene una nueva orquestación; Por ejemplo, MyCustomeItineraryService.odx.  
  
2. Agregue referencias a los ensamblados siguientes:  
  
   -   **Microsoft.Practices.ESB.Itinerary**  
  
   -   **Microsoft.Practices.ESB.Itinerary.Schemas**  
  
   -   **Microsoft.Practices.ESB.ExceptionHandling**  
  
   -   **Microsoft.Practices.ESB.ExceptionHandling.Faults**  
  
3. Definir un enlace directo lógico puerto de recepción y una forma recepción activada en la orquestación.  
  
4. Definir un filtro de suscripción para activar la orquestación desde el contexto del mensaje itinerarios para que la orquestación ejecuta la **MyCustomItineraryService** paso. El código siguiente muestra un ejemplo de un filtro adecuado.  
  
   ```csharp  
   (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
       == "MyCustomItineraryService")   
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
       == "Orchestration")  
   ```  
  
5. Definir una orquestación de tipo **Microsoft.Practices.ESB.Itinerary.ItineraryStep**. Agregue una actividad de expresión a la orquestación que rellena esta variable, como se muestra en el código siguiente.  
  
   ```csharp  
   // Retrieve the current itinerary step.  
   itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
   step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
   itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
   step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
   ```  
  
6. Agregue su implementación personalizada para el itinerario que crea el mensaje de salida para los siguientes pasos itinerarios; Por ejemplo, OutboundMsg.  
  
7. Pase el itinerario mediante la siguiente actividad de expresión que usa el contexto del mensaje del mensaje entrante.  
  
   ```csharp  
   OutboundMessage(*) = InboundMessage(*);   
   itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
   ```  
  
8. Enviar el mensaje saliente con el itinerario actualizado a través de un puerto de envío de enlace directo para activar el servicio de itinerarios siguiente.  
  
   Para obtener más información acerca de cómo implementar un servicio de itinerarios personalizado mediante las orquestaciones de BizTalk Server, consulte [instalar y ejecutar el ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) y [instalar y ejecutar la dispersión y recopilación Ejemplo](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).