---
title: "Paso 4: Probar la solución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f0ae6cb124ea9d8710797790b9176289faafc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-solution"></a>Paso 4: Probar la solución
En este tema probará la solución colocando un mensaje de solicitud ficticio en la carpeta asociada con el puerto de recepción de archivos. Como se describe en, se coloca un mensaje de solicitud ficticio solo para invocar la **WCF-WebHttp** puerto de envío. Puede crear un mensaje de solicitud ficticio como el siguiente:  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a>Para probar la solución  
  
1.  Desde la consola de administración de BizTalk Server, inicie **BizTalk Application 1**. De este modo, se inician todos los puertos creados en los pasos anteriores.  
  
2.  Abra el Explorador de Windows y desplácese hasta la ubicación que ha asociado a la ubicación de recepción de archivos. En esta ubicación, copie el mensaje de solicitud ficticio.  
  
3.  Cuando el archivo desaparezca, compruebe la ubicación que ha asociado al puerto de envío de archivos que consume el mensaje de respuesta desde la interfaz REST. Debe contener un mensaje de respuesta XML. Abra el mensaje XML para ver los detalles de los vuelos de las compañías aéreas estadounidenses con retrasos.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 5: Invocar una interfaz REST con BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)