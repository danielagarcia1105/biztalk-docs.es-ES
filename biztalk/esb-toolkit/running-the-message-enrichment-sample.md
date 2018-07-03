---
title: Ejecución del ejemplo de enriquecimiento de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7015a2fe-3727-48f3-a2ed-c368e0630626
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 192d300702b8194096f40e5f54b57717669730ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015133"
---
# <a name="running-the-message-enrichment-sample"></a><span data-ttu-id="985c6-102">Ejecución del ejemplo de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="985c6-102">Running the Message Enrichment Sample</span></span>
<span data-ttu-id="985c6-103">El ejemplo Message Enrichment usa una aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de rampa de itinerario.</span><span class="sxs-lookup"><span data-stu-id="985c6-103">The Message Enrichment sample uses a Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="985c6-104">**Para ejecutar el ejemplo Message Enrichment**</span><span class="sxs-lookup"><span data-stu-id="985c6-104">**To run Message Enrichment sample**</span></span>  
  
1. <span data-ttu-id="985c6-105">Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="985c6-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="985c6-106">En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="985c6-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="985c6-107">Desactive el **usar el servicio de WCF** casilla de verificación, por lo que puede utilizarse un itinerario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="985c6-107">Clear the **Use WCF Service** check box so that a client-side itinerary can be utilized.</span></span>  
  
4. <span data-ttu-id="985c6-108">Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta \Source\Samples\MessageEnrichment\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="985c6-108">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the \Source\Samples\MessageEnrichment\Itineraries folder.</span></span>  
  
5. <span data-ttu-id="985c6-109">Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo OrderDoc.xml desde la carpeta \Source\Samples\MessageEnrichment\Test\.</span><span class="sxs-lookup"><span data-stu-id="985c6-109">Click the **LoadMessage** button, and then select the OrderDoc.xml sample message from the \Source\Samples\MessageEnrichment\Test\ folder.</span></span>  
  
6. <span data-ttu-id="985c6-110">Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de rampa de itinerario.</span><span class="sxs-lookup"><span data-stu-id="985c6-110">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span>  
  
7. <span data-ttu-id="985c6-111">Vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml para ver el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="985c6-111">Browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml to see the output message.</span></span>  
  
   <span data-ttu-id="985c6-112">Para obtener información sobre cómo funciona el ejemplo Message Enrichment, consulte [mensaje enriquecimiento de ejemplo de funcionamiento](../esb-toolkit/how-the-message-enrichment-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="985c6-112">For information about how the Message Enrichment sample works, see [How the Message Enrichment Sample Works](../esb-toolkit/how-the-message-enrichment-sample-works.md).</span></span>