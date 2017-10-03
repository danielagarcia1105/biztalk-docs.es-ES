---
title: "Ejecutar el ejemplo de dispersión y recopilación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53676974-ea1f-4c95-9dbb-98fff92286fa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dcafa519aac074ccb339373a591b590846c9341
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-scatter-gather-sample"></a>Ejecutar el ejemplo de dispersión y recopilación
El ejemplo de dispersión y recopilación usa un Windows Forms probar la aplicación de cliente proporcionado con el ejemplo de itinerario en rampa para demostrar cómo este patrón aplica a las características del servicio de itinerario.  
  
 **Para ejecutar el ejemplo de dispersión y recopilación**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.  
  
2.  En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.  
  
3.  Haga clic en el **LoadItinerary** y, a continuación, seleccione el itinerario de ejemplo denominado ScatterGatherItinerary.xml desde la carpeta \Source\Samples\ScatterGather\Itineraries.  
  
4.  Desactive el **es la respuesta de solicitud** casilla de verificación para la aplicación realizará un itinerario unidireccional de servicios de operación.  
  
5.  (Opcional) Establecer el **usar servicio de WCF** casilla de verificación si desea que la aplicación para utilizar la OnRamp.Itinerary.Response.WCF ubicación de recepción en lugar del predeterminado OnRamp.Itinerary.Response.SOAP ubicación de recepción.  
  
6.  Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.  
  
7.  Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de itinerario en rampa. Abra el \Source\Samples\DynamicResolution\Test\FileDrop\Out carpeta para ver el mensaje de respuesta.  
  
 Para obtener información acerca de cómo el ejemplo de dispersión recopilar usa el servicio de itinerario de ESB, consulte [cómo funciona el de ejemplo de dispersión y recopilación](../esb-toolkit/how-the-scatter-gather-sample-works.md).