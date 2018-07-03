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
# <a name="running-the-scatter-gather-sample"></a><span data-ttu-id="64edb-102">Ejecutar el ejemplo de dispersión y recopilación</span><span class="sxs-lookup"><span data-stu-id="64edb-102">Running the Scatter-Gather Sample</span></span>
<span data-ttu-id="64edb-103">El ejemplo de dispersión y recopilación usa un los formularios de Windows probar la aplicación de cliente proporcionado con el ejemplo de rampa de itinerario para demostrar cómo este patrón aplica a las características del servicio de itinerarios.</span><span class="sxs-lookup"><span data-stu-id="64edb-103">The Scatter-Gather sample uses a the Windows Forms test client application provided with the Itinerary On-Ramp sample to demonstrate how this pattern applies the features of the Itinerary service.</span></span>  
  
 <span data-ttu-id="64edb-104">**Para ejecutar el ejemplo de dispersión y recopilación**</span><span class="sxs-lookup"><span data-stu-id="64edb-104">**To run the Scatter-Gather sample**</span></span>  
  
1. <span data-ttu-id="64edb-105">Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="64edb-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="64edb-106">En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="64edb-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="64edb-107">Haga clic en el **LoadItinerary** y, a continuación, seleccione el itinerario de ejemplo denominado ScatterGatherItinerary.xml desde la carpeta \Source\Samples\ScatterGather\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="64edb-107">Click the **LoadItinerary** button, and then select the sample itinerary named ScatterGatherItinerary.xml from the \Source\Samples\ScatterGather\Itineraries folder.</span></span>  
  
4. <span data-ttu-id="64edb-108">Desactive el **es la respuesta de solicitud** casilla de verificación para la aplicación llevará a cabo un itinerario unidireccional de servicios de operación.</span><span class="sxs-lookup"><span data-stu-id="64edb-108">Clear the **Is Request Response** check box so the application will perform a one-way itinerary services operation.</span></span>  
  
5. <span data-ttu-id="64edb-109">(Opcional) Establecer el **usar servicio de WCF** casilla de verificación si desea que la aplicación para usar el OnRamp.Itinerary.Response.WCF la ubicación de recepción en lugar del predeterminado OnRamp.Itinerary.Response.SOAP ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="64edb-109">(Optional) Set the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6. <span data-ttu-id="64edb-110">Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.</span><span class="sxs-lookup"><span data-stu-id="64edb-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7. <span data-ttu-id="64edb-111">Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de rampa de itinerario.</span><span class="sxs-lookup"><span data-stu-id="64edb-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="64edb-112">Abra el \Source\Samples\DynamicResolution\Test\FileDrop\Out carpeta para ver el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="64edb-112">Open the folder \Source\Samples\DynamicResolution\Test\FileDrop\Out to see the response message.</span></span>  
  
   <span data-ttu-id="64edb-113">Para obtener información acerca de cómo el ejemplo de dispersión recopilar usa el servicio de itinerarios de ESB, consulte [cómo funciona el de ejemplo de dispersión y recopilación](../esb-toolkit/how-the-scatter-gather-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="64edb-113">For information about how the Scatter Gather sample uses the ESB Itinerary service, see [How the Scatter-Gather Sample Works](../esb-toolkit/how-the-scatter-gather-sample-works.md).</span></span>