---
title: Ejecutar el ejemplo de enriquecimiento de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7015a2fe-3727-48f3-a2ed-c368e0630626
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4ed3b3ebc24a908dfefd70711db0d40638c2d3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-message-enrichment-sample"></a>Ejecutar el ejemplo de enriquecimiento de mensajes
El ejemplo Message Enrichment utiliza una aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de itinerario en rampa.  
  
 **Para ejecutar el ejemplo Message Enrichment**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.  
  
2.  En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.  
  
3.  Desactive el **usar el servicio de WCF** casilla de verificación para que se puede utilizar un itinerario del lado cliente.  
  
4.  Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta \Source\Samples\MessageEnrichment\Itineraries.  
  
5.  Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo OrderDoc.xml desde la carpeta \Source\Samples\MessageEnrichment\Test\.  
  
6.  Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de itinerario en rampa.  
  
7.  Vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml para ver el mensaje de salida.  
  
 Para obtener información sobre cómo funciona el ejemplo Message Enrichment, consulte [mensaje enriquecimiento ejemplo funcionamiento del](../esb-toolkit/how-the-message-enrichment-sample-works.md).