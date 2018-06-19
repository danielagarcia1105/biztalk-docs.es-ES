---
title: Cómo los varios servicios Web funciona de ejemplo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16680ca7-16cc-47df-8c39-a3311d468a46
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3d9faf350654be69015ea940b6b4f034d4de74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294164"
---
# <a name="how-the-multiple-web-services-sample-works"></a>Cómo el varios servicios Web de ejemplo funciona
El ejemplo de varios servicios Web utiliza dos técnicas independientes para llamar a varios servicios Web en serie mientras todavía se puede devolver un resultado correcto al llamador original. Un método utiliza un componente de canalización personalizado en la canalización de respuesta, y el otro método usa un personalizado bidireccional enrutamiento basado en la orquestación itinerario servicio que omite el requisito de una invocación de fuera de rampa para completar una llamada de solicitud/respuesta a un sitio Web servicio.  
  
 El método de componente de canalización personalizada utiliza el componente de canalización de reenvío. Este componente condicionalmente promociona propiedades para impedir que Microsoft BizTalk enrutar el mensaje a la canalización de envío de la pendiente hasta que se procesen todos los servicios de itinerarios.  
  
 El método de servicio personalizado basado en la orquestación utiliza la orquestación TwoWayRouting contenida en ESB. MultipleWebServices.Orchestrations el proyecto en el \Source\Samples\MultipleWebSerivces\Source\ESB. Carpeta MultipleWebServices.Orchestrations. Este servicio procesa un solucionador asociado para determinar la dirección del extremo de un servicio Web bidireccional. A continuación, configura un puerto de envío dinámico Solict respuesta denominado RoutingPort para enviar el mensaje al servicio Web y devolver el resultado a la orquestación. La orquestación, a continuación, hace avanzar el itinerario y devuelve el mensaje resultante en el cuadro de mensajes.  
  
 Los itinerarios incluidos con el ejemplo utilice uno o ambos de estos métodos para asegurarse de que se mantiene el flujo de mensajes siguiendo el itinerario. Para obtener más información, consulte [el ejemplo de itinerarios al servicios varias Web](../esb-toolkit/the-sample-multiple-web-services-itineraries.md).