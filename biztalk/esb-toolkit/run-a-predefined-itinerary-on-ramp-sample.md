---
title: Ejecutar un ejemplo de rampa de itinerario predefinido | Microsoft Docs
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
ms.openlocfilehash: 7e428a9106582e5bad3408cfb6643cc5da21ac74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996589"
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a>Ejecutar un ejemplo de rampa de itinerario predefinido
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye 20 casos de uso de itinerario predefinidos que puede ejecutar. Para obtener una lista de estos casos de uso, vea [los escenarios de itinerarios de ejemplo](../esb-toolkit/the-sample-itinerary-scenarios.md).  
  
> [!NOTE]
>  Antes de ejecutar cualquiera de los ejemplos, debe importar manualmente el archivo de enlace de itinerarios adecuado desde la carpeta \Source\Samples\Itinerary\Install\Binding en la aplicación de GlobalBank.ESB BizTalk. Este archivo de enlace restablece las propiedades en los dos puertos de envío dinámico. Importe el archivo de enlace denominado GlobalBank.ESB.Itinerary_Bindings.xml.  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a>Para ejecutar uno de los ejemplos de rampa de itinerario predefinido  
  
1. Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de BizTalk para iniciarlo.  
  
2. En el Explorador de Windows, abra el \Source\Samples\Itinerary\Source\ESB subcarpeta. Itinerary.Test\bin\Debug donde instaló los ejemplos del Kit de herramientas de ESB de BizTalk y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.  
  
3. Haga clic en el **LoadItinerary** y, a continuación, seleccione el itinerario de ejemplo denominado TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml desde la carpeta \Source\Samples\Itinerary\Itineraries.  
  
4. En el **opciones del servicio Web** sección, seleccione el **servicio bidireccional** casilla de verificación. Esto indica al cliente de prueba para realizar una operación de servicio de itinerarios de solicitud-respuesta.  
  
5. (Opcional) Seleccione el **usar servicio de WCF** casilla de verificación si desea que la aplicación para usar el OnRamp.Itinerary.Response.WCF la ubicación de recepción en lugar del predeterminado OnRamp.Itinerary.Response.SOAP ubicación de recepción.  
  
6. Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.  
  
7. Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de rampa de itinerario. Figura 1 muestra el resultado.  
  
   ![Itinerario en rampa](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")  
  
   **Figura 1**  
  
   **La aplicación de cliente de itinerario en rampa ejecutando uno de los ejemplos de itinerario en rampa**  
  
   El nombre del servicio especificado en la definición de itinerarios corresponde directamente a la **ServiceName** propiedad del servicio al que se suscribe el ejemplo. En el ejemplo de itinerario ejecutado en el procedimiento anterior (TwoWay OrchTransform-OrchRoutingGroup OrchTwoWayCustom.xml), el primer servicio que se ejecuta es un servicio basado en la orquestación que realiza una transformación. La siguiente sección del itinerario especifica este servicio.  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 El servicio de orquestación en este **\<servicio\>** elemento especifica la orquestación de enlace directo que tiene las propiedades de filtro se muestra en la figura 2. Tenga en cuenta que la orquestación se suscribe solo a los mensajes que tienen el valor **Microsoft.Practices.ESB.Services.Transform** para el **ServiceName** propiedad de contexto, el valor  **Pendiente** para el **ServiceState** propiedad de contexto y el valor de la orquestación para la **ServiceType** propiedad de contexto.  
  
 ![Expresión de filtro](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")  
  
 **Figura 2**  
  
 **La expresión de filtro para la orquestación de enlace directo usada en el ejemplo de rampa de itinerario**