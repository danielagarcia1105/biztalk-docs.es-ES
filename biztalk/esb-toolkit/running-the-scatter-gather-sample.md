---
title: Ejecutar el ejemplo de dispersión y recopilación | Documentos de Microsoft
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
ms.openlocfilehash: 7dcafa519aac074ccb339373a591b590846c9341
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294660"
---
# <a name="running-the-scatter-gather-sample"></a><span data-ttu-id="83f9c-102">Ejecutar el ejemplo de dispersión y recopilación</span><span class="sxs-lookup"><span data-stu-id="83f9c-102">Running the Scatter-Gather Sample</span></span>
<span data-ttu-id="83f9c-103">El ejemplo de dispersión y recopilación usa un Windows Forms probar la aplicación de cliente proporcionado con el ejemplo de itinerario en rampa para demostrar cómo este patrón aplica a las características del servicio de itinerario.</span><span class="sxs-lookup"><span data-stu-id="83f9c-103">The Scatter-Gather sample uses a the Windows Forms test client application provided with the Itinerary On-Ramp sample to demonstrate how this pattern applies the features of the Itinerary service.</span></span>  
  
 <span data-ttu-id="83f9c-104">**Para ejecutar el ejemplo de dispersión y recopilación**</span><span class="sxs-lookup"><span data-stu-id="83f9c-104">**To run the Scatter-Gather sample**</span></span>  
  
1.  <span data-ttu-id="83f9c-105">Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="83f9c-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="83f9c-106">En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="83f9c-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="83f9c-107">Haga clic en el **LoadItinerary** y, a continuación, seleccione el itinerario de ejemplo denominado ScatterGatherItinerary.xml desde la carpeta \Source\Samples\ScatterGather\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="83f9c-107">Click the **LoadItinerary** button, and then select the sample itinerary named ScatterGatherItinerary.xml from the \Source\Samples\ScatterGather\Itineraries folder.</span></span>  
  
4.  <span data-ttu-id="83f9c-108">Desactive el **es la respuesta de solicitud** casilla de verificación para la aplicación realizará un itinerario unidireccional de servicios de operación.</span><span class="sxs-lookup"><span data-stu-id="83f9c-108">Clear the **Is Request Response** check box so the application will perform a one-way itinerary services operation.</span></span>  
  
5.  <span data-ttu-id="83f9c-109">(Opcional) Establecer el **usar servicio de WCF** casilla de verificación si desea que la aplicación para utilizar la OnRamp.Itinerary.Response.WCF ubicación de recepción en lugar del predeterminado OnRamp.Itinerary.Response.SOAP ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="83f9c-109">(Optional) Set the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6.  <span data-ttu-id="83f9c-110">Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.</span><span class="sxs-lookup"><span data-stu-id="83f9c-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7.  <span data-ttu-id="83f9c-111">Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de itinerario en rampa.</span><span class="sxs-lookup"><span data-stu-id="83f9c-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="83f9c-112">Abra el \Source\Samples\DynamicResolution\Test\FileDrop\Out carpeta para ver el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="83f9c-112">Open the folder \Source\Samples\DynamicResolution\Test\FileDrop\Out to see the response message.</span></span>  
  
 <span data-ttu-id="83f9c-113">Para obtener información acerca de cómo el ejemplo de dispersión recopilar usa el servicio de itinerario de ESB, consulte [cómo funciona el de ejemplo de dispersión y recopilación](../esb-toolkit/how-the-scatter-gather-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="83f9c-113">For information about how the Scatter Gather sample uses the ESB Itinerary service, see [How the Scatter-Gather Sample Works](../esb-toolkit/how-the-scatter-gather-sample-works.md).</span></span>