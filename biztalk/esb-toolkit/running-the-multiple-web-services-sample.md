---
title: Ejecuta la Web de varios servicios de ejemplo | Documentos de Microsoft
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
ms.openlocfilehash: 4ec54fabb7ed140fd88b5a2d5a07d788805c741e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294804"
---
# <a name="running-the-multiple-web-services-sample"></a><span data-ttu-id="2f368-102">Ejecutar el ejemplo de servicios Web varios</span><span class="sxs-lookup"><span data-stu-id="2f368-102">Running the Multiple Web Services Sample</span></span>
<span data-ttu-id="2f368-103">El ejemplo de varios servicios Web usa la aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de itinerario en rampa.</span><span class="sxs-lookup"><span data-stu-id="2f368-103">The Multiple Web Services sample uses the Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="2f368-104">**Para ejecutar el ejemplo de varios servicios Web**</span><span class="sxs-lookup"><span data-stu-id="2f368-104">**To run the Multiple Web Services sample**</span></span>  
  
1.  <span data-ttu-id="2f368-105">Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="2f368-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="2f368-106">En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="2f368-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="2f368-107">Desactive el **usar el servicio de WCF** casilla, por lo que puede utilizarse un itinerario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="2f368-107">Clear the **Use WCF Service** check box, so that a client-side itinerary can be utilized.</span></span>  
  
4.  <span data-ttu-id="2f368-108">Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta \Source\Samples\MultipleWebServices\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="2f368-108">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the \Source\Samples\MultipleWebServices\Itineraries folder.</span></span>  
  
5.  <span data-ttu-id="2f368-109">Seleccione el **dos servicios de manera** casilla de verificación para la aplicación realizará un itinerario bidireccional de servicios de operación.</span><span class="sxs-lookup"><span data-stu-id="2f368-109">Select the **Two Way Service** check box so the application will perform a two-way itinerary services operation.</span></span>  
  
6.  <span data-ttu-id="2f368-110">Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.</span><span class="sxs-lookup"><span data-stu-id="2f368-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7.  <span data-ttu-id="2f368-111">Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de itinerario en rampa.</span><span class="sxs-lookup"><span data-stu-id="2f368-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="2f368-112">Espere a que un mensaje de respuesta que aparezcan en el **resultado** cuadro.</span><span class="sxs-lookup"><span data-stu-id="2f368-112">Wait for a response message to appear in the **Result** box.</span></span>  
  
 <span data-ttu-id="2f368-113">Para obtener información acerca de cómo el ejemplo de varios servicios Web usa el servicio de itinerario de ESB, consulte [cómo varios Web Services funciona el ejemplo](../esb-toolkit/how-the-multiple-web-services-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="2f368-113">For information about how the Multiple Web Services sample uses the ESB Itinerary service, see [How the Multiple Web Services Sample Works](../esb-toolkit/how-the-multiple-web-services-sample-works.md).</span></span>