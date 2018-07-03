---
title: Ejecutar la Web de varios servicios ejemplo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b201c7c3-213a-4009-8872-5a4c1cbb8195
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765d9785bde94f363ea56178f3cc0f500381d4e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997525"
---
# <a name="running-the-multiple-web-services-sample"></a><span data-ttu-id="2cfb6-102">Ejecutar el ejemplo de varios servicios Web</span><span class="sxs-lookup"><span data-stu-id="2cfb6-102">Running the Multiple Web Services Sample</span></span>
<span data-ttu-id="2cfb6-103">El ejemplo de varios servicios Web utiliza la aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de rampa de itinerario.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-103">The Multiple Web Services sample uses the Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="2cfb6-104">**Para ejecutar el ejemplo de varios servicios Web**</span><span class="sxs-lookup"><span data-stu-id="2cfb6-104">**To run the Multiple Web Services sample**</span></span>  
  
1. <span data-ttu-id="2cfb6-105">Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="2cfb6-106">En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="2cfb6-107">Desactive el **usar el servicio de WCF** casilla, por lo que puede utilizarse un itinerario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-107">Clear the **Use WCF Service** check box, so that a client-side itinerary can be utilized.</span></span>  
  
4. <span data-ttu-id="2cfb6-108">Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta \Source\Samples\MultipleWebServices\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-108">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the \Source\Samples\MultipleWebServices\Itineraries folder.</span></span>  
  
5. <span data-ttu-id="2cfb6-109">Seleccione el **dos servicios de manera** casilla de verificación para la aplicación llevará a cabo un itinerario bidireccional de servicios de operación.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-109">Select the **Two Way Service** check box so the application will perform a two-way itinerary services operation.</span></span>  
  
6. <span data-ttu-id="2cfb6-110">Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7. <span data-ttu-id="2cfb6-111">Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de rampa de itinerario.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="2cfb6-112">Espere a que aparezca en un mensaje de respuesta del **resultado** cuadro.</span><span class="sxs-lookup"><span data-stu-id="2cfb6-112">Wait for a response message to appear in the **Result** box.</span></span>  
  
   <span data-ttu-id="2cfb6-113">Para obtener información acerca de cómo el ejemplo de varios servicios Web usa el servicio de itinerarios de ESB, consulte [cómo varias Web Services funciona el ejemplo](../esb-toolkit/how-the-multiple-web-services-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="2cfb6-113">For information about how the Multiple Web Services sample uses the ESB Itinerary service, see [How the Multiple Web Services Sample Works](../esb-toolkit/how-the-multiple-web-services-sample-works.md).</span></span>