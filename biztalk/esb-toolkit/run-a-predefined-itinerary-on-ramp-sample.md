---
title: Ejecutar un ejemplo en rampa itinerario predefinido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4400193-20ac-479a-8bf9-b1c99eb35231
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38320cc6877815ccbf7b078190a3c2be1c6f74b0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976682"
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a>Ejecutar un ejemplo en rampa itinerario predefinido
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye 20 casos de uso de itinerario predefinidos pueden ejecutar. Para obtener una lista de estos casos de uso, consulte [los escenarios de ejemplo de itinerario](../esb-toolkit/the-sample-itinerary-scenarios.md).  
  
> [!NOTE]
>  Antes de ejecutar cualquiera de los ejemplos, debe importar manualmente el archivo de enlace de itinerarios adecuado desde la carpeta \Source\Samples\Itinerary\Install\Binding en la aplicación de GlobalBank.ESB BizTalk. Este archivo de enlace restablece las propiedades de los dos puertos de envío dinámico. Importe el archivo de enlace denominado GlobalBank.ESB.Itinerary_Bindings.xml.  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a>Para ejecutar uno de los ejemplos de itinerario en rampa predefinidos  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
2.  En el Explorador de Windows, abra la subcarpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test\bin\Debug donde instaló los ejemplos del Kit de herramientas de ESB de BizTalk y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.  
  
3.  Haga clic en el **LoadItinerary** y, a continuación, seleccione el itinerario de ejemplo denominado TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml desde la carpeta \Source\Samples\Itinerary\Itineraries.  
  
4.  En el **opciones del servicio Web** sección, seleccione la **servicio bidireccional** casilla de verificación. Esto indica que el cliente de prueba para realizar una operación de servicio itinerarios de solicitud-respuesta.  
  
5.  (Opcional) Seleccione el **usar servicio de WCF** casilla de verificación si desea que la aplicación para utilizar la OnRamp.Itinerary.Response.WCF ubicación de recepción en lugar del predeterminado OnRamp.Itinerary.Response.SOAP ubicación de recepción.  
  
6.  Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.  
  
7.  Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de itinerario en rampa. La figura 1 muestra el resultado.  
  
 ![Itinerario en rampa](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")  
  
 **Figura 1**  
  
 **La aplicación de cliente de itinerario en rampa ejecuta uno de los ejemplos de itinerario en rampa**  
  
 El nombre del servicio especificado en la definición de itinerarios corresponde directamente a la **ServiceName** propiedad del servicio al que se suscribe el ejemplo. En el ejemplo itinerario ejecutado en el procedimiento anterior (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml), el primer servicio que se ejecuta es un servicio basado en la orquestación que realiza la transformación. La siguiente sección de la itinerario especifica este servicio.  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 El servicio de orquestación en este  **\<servicio\>**  elemento especifica la orquestación de enlace directo que tiene las propiedades de filtro se muestra en la figura 2. Tenga en cuenta que la orquestación se suscribe sólo a los mensajes que tienen el valor **Microsoft.Practices.ESB.Services.Transform** para el **ServiceName** propiedad de contexto, el valor  **Pendiente** para el **ServiceState** propiedad de contexto y el valor de la orquestación para la **ServiceType** propiedad de contexto.  
  
 ![Expresión de filtro](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")  
  
 **Figura 2**  
  
 **La expresión de filtro para la orquestación de enlace directo usada en el ejemplo de itinerario en rampa**