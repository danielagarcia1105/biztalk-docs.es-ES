---
title: Solucionar problemas de reenvío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b60ad45-d793-4de6-b9bc-3e8ef34f2b61
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1a143924b97117a708caea3006f74db6e029ca4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295100"
---
# <a name="troubleshooting-resubmission-issues"></a><span data-ttu-id="2165c-102">Solucionar problemas de reenvío</span><span class="sxs-lookup"><span data-stu-id="2165c-102">Troubleshooting Resubmission Issues</span></span>
<span data-ttu-id="2165c-103">Si tiene problemas para volver a enviar mensajes, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2165c-103">If you have problems resubmitting messages, check the following:</span></span>  
  
-   <span data-ttu-id="2165c-104">¿Puede acceder a la ubicación de recepción a través del explorador?</span><span class="sxs-lookup"><span data-stu-id="2165c-104">Can you access the receive location through your browser?</span></span> <span data-ttu-id="2165c-105">Si está intentando volver a enviar a WCF rampa o SOAP rampa, debe ser la dirección URL del formulario http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc o http://localhost/ESB.OnRampServices/ProcessItinerary.asmx.</span><span class="sxs-lookup"><span data-stu-id="2165c-105">If you are trying to resubmit to the WCF on-ramp or the SOAP on-ramp, the URL should be of the form http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc or http://localhost/ESB.OnRampServices/ProcessItinerary.asmx.</span></span> <span data-ttu-id="2165c-106">Si está intentando volver a enviar a una ubicación de recepción HTTP, puede usar el Explorador de Internet para determinar si la ubicación de recepción está funcionando correctamente mediante la anexión de un mensaje de ejemplo para la cadena de consulta, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2165c-106">If you are trying to resubmit to an HTTP receive location, you can use your Internet browser to determine whether the receive location is functioning properly by appending a sample message to the query string, as shown in the following example.</span></span>  
  
    ```  
    http://localhost/HTTPOnRamp/BTSHttpReceive.dll?<SampleMessage>Sample Message Content</SampleMessage>  
    ```  
  
-   <span data-ttu-id="2165c-107">Compruebe que el HTTP de BizTalk recibe adaptador está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2165c-107">Verify that the BizTalk HTTP receive adapter is properly configured.</span></span>