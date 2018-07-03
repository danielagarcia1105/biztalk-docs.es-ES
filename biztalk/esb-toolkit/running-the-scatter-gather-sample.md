---
title: Ejecutar el ejemplo de dispersión y recopilación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53676974-ea1f-4c95-9dbb-98fff92286fa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda345b5a96f36125432e454b5f239f756a76652
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023762"
---
# <a name="running-the-scatter-gather-sample"></a>Ejecutar el ejemplo de dispersión y recopilación
El ejemplo de dispersión y recopilación usa un los formularios de Windows probar la aplicación de cliente proporcionado con el ejemplo de rampa de itinerario para demostrar cómo este patrón aplica a las características del servicio de itinerarios.  
  
 **Para ejecutar el ejemplo de dispersión y recopilación**  
  
1. Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.  
  
2. En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.  
  
3. Haga clic en el **LoadItinerary** y, a continuación, seleccione el itinerario de ejemplo denominado ScatterGatherItinerary.xml desde la carpeta \Source\Samples\ScatterGather\Itineraries.  
  
4. Desactive el **es la respuesta de solicitud** casilla de verificación para la aplicación llevará a cabo un itinerario unidireccional de servicios de operación.  
  
5. (Opcional) Establecer el **usar servicio de WCF** casilla de verificación si desea que la aplicación para usar el OnRamp.Itinerary.Response.WCF la ubicación de recepción en lugar del predeterminado OnRamp.Itinerary.Response.SOAP ubicación de recepción.  
  
6. Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.  
  
7. Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de rampa de itinerario. Abra el \Source\Samples\DynamicResolution\Test\FileDrop\Out carpeta para ver el mensaje de respuesta.  
  
   Para obtener información acerca de cómo el ejemplo de dispersión recopilar usa el servicio de itinerarios de ESB, consulte [cómo funciona el de ejemplo de dispersión y recopilación](../esb-toolkit/how-the-scatter-gather-sample-works.md).