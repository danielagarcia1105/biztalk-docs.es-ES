---
title: Ejecutar un escenario de itinerarios personalizado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fd69e29-e853-4b16-9966-29ab98dd5bea
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8659c5b37cba0520fb4a4c0f4c63c8d6ecff37be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="execute-a-custom-itinerary-scenario"></a>Ejecutar un escenario de itinerarios personalizado
Puede usar el cliente de prueba de itinerario aplicación ejecutar escenarios personalizados de itinerarios.  
  
### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a>Para ejecutar un escenario de itinerarios personalizado mediante la aplicación de cliente de prueba de itinerario  
  
1.  En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test\bin\Debug donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos e iniciar la aplicación denominada Esb.Itinerary.Test.exe.  
  
2.  Seleccione un tipo de servicio en la **ServiceType** la lista desplegable, especifique un nombre para la solicitud y, a continuación, seleccione la **IsRequestResponse** casilla de verificación si se trata de una operación de solicitud/respuesta. Puede especificar una operación bidireccional y decide usar la versión WCF del servicio Web de itinerario; Para ello, seleccione las casillas de verificación en la **opciones del servicio Web** en la parte superior de la ventana de la aplicación.  
  
3.  Para especificar las resoluciones para usar con el servicio seleccionado en el **AddResolversfortheService** sección de la ventana, seleccione una resolución de tipo en la lista desplegable y, a continuación, haga clic en **AddResolver**. Puede agregar a más de una resolución si es necesario. Después de agregar todas las resoluciones necesarias, haga clic en el **AddService** botón para agregar esta invocación del servicio para el itinerario.  
  
4.  Si desea agregar más llamadas de servicio para el itinerario, repita los pasos 2 y 3. También puede usar el **RemoveService** y **ClearServices** botones para modificar la lista de servicios en el itinerario.  
  
5.  Si desea repetir el itinerario actual en otro momento, guardar el itinerario actual completando en el disco, haga clic en el **SaveItinerary** botón. Puede cargar de nuevo haciendo clic en el **LoadItinerary** botón. Esto significa que no es necesario especificar los servicios y las resoluciones en el itinerario cada vez que se ejecuta este escenario con diferentes mensajes o la configuración del servicio Web de itinerario.  
  
6.  Cargar un mensaje adecuado. Para ello, escriba la ruta de acceso y el nombre del mensaje en el **LoadMessage** texto cuadro o haga clic en el botón de puntos suspensivos (...) y, a continuación, seleccione el archivo de mensaje necesarios.  
  
7.  Haga clic en el **SubmitRequest** botón para enviar el mensaje para su procesamiento con la configuración de itinerarios especificada. Si el procesamiento devuelve un resultado, este nombre aparecerá en la **resultado** cuadro de texto.