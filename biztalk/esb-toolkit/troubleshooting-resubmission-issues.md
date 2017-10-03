---
title: "Solucionar problemas de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b60ad45-d793-4de6-b9bc-3e8ef34f2b61
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1a143924b97117a708caea3006f74db6e029ca4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-resubmission-issues"></a>Solucionar problemas de reenvío
Si tiene problemas para volver a enviar mensajes, compruebe lo siguiente:  
  
-   ¿Puede acceder a la ubicación de recepción a través del explorador? Si está intentando volver a enviar a WCF rampa o SOAP rampa, debe ser la dirección URL del formulario http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc o http://localhost/ESB.OnRampServices/ProcessItinerary.asmx. Si está intentando volver a enviar a una ubicación de recepción HTTP, puede usar el Explorador de Internet para determinar si la ubicación de recepción está funcionando correctamente mediante la anexión de un mensaje de ejemplo para la cadena de consulta, como se muestra en el ejemplo siguiente.  
  
    ```  
    http://localhost/HTTPOnRamp/BTSHttpReceive.dll?<SampleMessage>Sample Message Content</SampleMessage>  
    ```  
  
-   Compruebe que el HTTP de BizTalk recibe adaptador está configurado correctamente.