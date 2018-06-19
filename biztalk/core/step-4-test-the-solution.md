---
title: 'Paso 4: Probar la solución | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f0ae6cb124ea9d8710797790b9176289faafc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277412"
---
# <a name="step-4-test-the-solution"></a><span data-ttu-id="c8d71-102">Paso 4: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="c8d71-102">Step 4: Test the Solution</span></span>
<span data-ttu-id="c8d71-103">En este tema probará la solución colocando un mensaje de solicitud ficticio en la carpeta asociada con el puerto de recepción de archivos.</span><span class="sxs-lookup"><span data-stu-id="c8d71-103">In this topic you test the solution by dropping a dummy request message in the folder you associated with the FILE receive port.</span></span> <span data-ttu-id="c8d71-104">Como se describe en, se coloca un mensaje de solicitud ficticio solo para invocar la **WCF-WebHttp** puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c8d71-104">As explained in, you drop a dummy request message only to invoke the **WCF-WebHttp** send port.</span></span> <span data-ttu-id="c8d71-105">Puede crear un mensaje de solicitud ficticio como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8d71-105">You can create a dummy request message like the following:</span></span>  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="c8d71-106">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="c8d71-106">To test the solution</span></span>  
  
1.  <span data-ttu-id="c8d71-107">Desde la consola de administración de BizTalk Server, inicie **BizTalk Application 1**.</span><span class="sxs-lookup"><span data-stu-id="c8d71-107">From the BizTalk Server Administration Console, start **BizTalk Application 1**.</span></span> <span data-ttu-id="c8d71-108">De este modo, se inician todos los puertos creados en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="c8d71-108">This starts all the ports that we created in previous steps.</span></span>  
  
2.  <span data-ttu-id="c8d71-109">Abra el Explorador de Windows y desplácese hasta la ubicación que ha asociado a la ubicación de recepción de archivos.</span><span class="sxs-lookup"><span data-stu-id="c8d71-109">Open Windows Explorer, and navigate to the location that you associated with the FILE receive location.</span></span> <span data-ttu-id="c8d71-110">En esta ubicación, copie el mensaje de solicitud ficticio.</span><span class="sxs-lookup"><span data-stu-id="c8d71-110">At this location, copy the dummy request message.</span></span>  
  
3.  <span data-ttu-id="c8d71-111">Cuando el archivo desaparezca, compruebe la ubicación que ha asociado al puerto de envío de archivos que consume el mensaje de respuesta desde la interfaz REST.</span><span class="sxs-lookup"><span data-stu-id="c8d71-111">When the file disappears, check the location you associated with FILE send port that consumes the response message from the REST interface.</span></span> <span data-ttu-id="c8d71-112">Debe contener un mensaje de respuesta XML.</span><span class="sxs-lookup"><span data-stu-id="c8d71-112">It should contain an XML response message.</span></span> <span data-ttu-id="c8d71-113">Abra el mensaje XML para ver los detalles de los vuelos de las compañías aéreas estadounidenses con retrasos.</span><span class="sxs-lookup"><span data-stu-id="c8d71-113">Open the XML message to see the details of flights from US air carries that are delayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d71-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8d71-114">See Also</span></span>  
 [<span data-ttu-id="c8d71-115">Tutorial 5: Invocar una interfaz REST con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c8d71-115">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)