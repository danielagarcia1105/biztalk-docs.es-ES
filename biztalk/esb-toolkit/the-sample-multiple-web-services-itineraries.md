---
title: El ejemplo Web varios servicios itinerarios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f67a4c6-b547-4261-ab3f-db78603ac588
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8beeda266ae29eb4bb3e7c2a373c9ac6fc2b2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-sample-multiple-web-services-itineraries"></a>El ejemplo itinerarios de los servicios Web de varios
En la tabla siguiente enumera todos los archivos itinerarios predefinidos incluidos con el ejemplo de varios servicios Web. Estos se encuentran en la carpeta \Source\Samples\MultipleWebServices\Itineraries.  
  
|Nombre de archivo|Description|  
|---------------|-----------------|  
|OneWayMessagingMultipleServices.xml|Este itinerario unidireccional transforma un mensaje de NAOrderDoc para CNOrderDoc y, a continuación, enruta al servicio en orden Candian utilizando el DynamicResolutionSolicitResp fuera de rampa. La respuesta, a continuación, se transforma en el mensaje de CNOrderDoc mediante el servicio de transformación basado en mensajería y, a continuación, se enruta nuevo en el servicio de pedidos canadiense utilizando el DynamicResolutionSolicitResp fuera de rampa. La respuesta devuelta se enruta a la carpeta de Source\Samples\DynamicResolution\Test\Filedrop\Out mediante el servicio de enrutamiento.|  
|TwoWayMessagingMultipleServices.xml|Este itinerario bidireccional transforma un mensaje de NAOrderDoc para CNOrderDoc y, a continuación, enruta al servicio de pedidos canadiense. A continuación, toma la respuesta del servicio de pedidos canadiense, lo transforma a un mensaje de CNOrderDoc y lo nuevo, a continuación, enruta al servicio de pedidos canadiense. El resultado, a continuación, se devuelve al llamador. Todos los transformación y enrutamiento tiene lugar a través de servicios de mensajería. Ambos pendientes desactivar usar el puerto de envío DynamicResolutionSolicitRespForwarder.|  
|TwoWayMessagingOrchestrationMultipleServices.xml|Este itinerario bidireccional utiliza servicios de mensajería para transformar un mensaje de NAOrderDoc para CNOrderDoc y, a continuación, enruta ese mensaje en el servicio de orden canadiense utilizando el puerto de envío DynamicResolutionSolicitRespForwarder. La respuesta se transforma utilizando la implementación basada en la orquestación del servicio en la transformación y, a continuación, se pasa al personalizado Microsoft.Practices.ESB.Routing.TwoWay basada en orquestación itinerario servicio proporcionado como parte de la muestra. Este servicio envía un mensaje al servicio Web especificado por la resolución asociada (en este caso, el servicio de pedidos canadiense) y, a continuación, se recibe y devuelve la respuesta del servicio. Esta respuesta se envía de vuelta al llamador.|  
|TwoWayOrchestrationsMultipleServices.xml|Este itinerario bidireccional utiliza un servicio de mensajería para transformar un mensaje de NAOrderDoc para CNOrderDoc y, a continuación, usa la orquestación Microsoft.Practices.ESB.Routing.TwoWay para enrutar ese mensaje al servicio de pedidos canadiense y devolver el resultado. A continuación, se transforme el mensaje a un mensaje de CNOrderDoc mediante el servicio de transformación basada en la orquestación; Después de eso, se envía al servicio de pedidos canadiense mediante el servicio de Microsoft.Practices.ESB.Routing.TwoWay basada en orquestación itinerario. El resultado, a continuación, se devuelve al llamador.|  
|TwoWay-parcial-Selector-Required.xml|Este dos usos itinerarios de forma que un servicio de mensajería para enrutar un NAOrderDoc de mensajes al servicio de pedidos canadiense mediante DynamicResolutionSolicitResp fuera de rampa. El NAOrderDoc se transforma en CNOrderDoc con los servicios de transformación basado en mensajería y canadiense llama. A continuación, se devuelve la respuesta al llamador.|