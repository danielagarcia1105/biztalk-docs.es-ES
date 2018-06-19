---
title: El componente de reenviador itinerarios de ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 607cc8a0-4964-4751-baca-c3329983c98b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61643423021701186745ab4275520cb14d3ceca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295340"
---
# <a name="the-esb-itinerary-forwarder-component"></a>El componente de reenviador itinerarios de ESB
El componente de reenviador de itinerario ESB se utiliza cuando un itinerario debe invocar secuencialmente varios servicios Web. El componente puede utilizarse en canalizaciones que están asociadas con el lado de la respuesta de un bidireccional fuera de rampa de recepción.  
  
## <a name="installation"></a>Installation  
 Al instalar el núcleo de ESB automáticamente se instala el **itinerario reenviador** componente en la carpeta de componentes de canalización de BizTalk Server.  
  
## <a name="how-it-works"></a>Funcionamiento  
 Cuando Microsoft BizTalk recibe un mensaje a través de dos sentidos puerto de recepción como el mensaje se publica en la base de datos de cuadro de mensaje, se crea una suscripción de instancia. Esta suscripción está formada por el **EpmRRCorrelationToken** propiedad promocionada y un **RouteDirectToTP** propiedad promocionada. Cuando el suscriptor (orquestación o puerto de envío bidireccional) devuelve el mensaje de respuesta, estas propiedades promocionadas coincide con la suscripción y la respuesta se devuelve inmediatamente a través de la canalización de envío del puerto de recepción.  
  
 El reenviador de itinerario ESB debe usarse en la canalización de respuesta para una bidireccional fuera de rampa donde fuera de rampa es llamar a un servicio Web de solicitud-respuesta. El componente interfiere con el proceso típico de BizTalk cambiando el **RouteDirectToTP** puerto de recepción de la propiedad promocionada en False, lo que garantiza que no se devolverá la respuesta para el inicio. Cuando se alcanza el último paso en el itinerario, el **RouteDirectToTP** propiedad se vuelve a cambiar **True**, por tanto, se devuelve el resultado para el iniciador en rampa.  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a>Mediante el componente de reenviador itinerarios de ESB  
 Agregue el componente de ESB ItineraryForwarder a una canalización de recepción y, a continuación, usar la canalización con la parte de la respuesta de una bidireccional fuera de rampa. Crear un itinerario que se encadena Web varios servicios, con o sin servicios de transformación de itinerarios, antes de o entre los servicios. Para obtener un ejemplo de cómo usar el componente de reenviador de itinerario de ESB, consulte el [instalar y ejecutar el ejemplo de servicios Web varios](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).