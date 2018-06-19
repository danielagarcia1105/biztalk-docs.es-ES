---
title: Artefactos de enrutamientos basados en itinerario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff38ab7-5a16-42cc-9065-075e9db7acd3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ca01cc5313c8ca64418f65cec3fdf18fdbc85df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296828"
---
# <a name="itinerary-based-routing-artifacts"></a>Artefactos de enrutamientos basados en itinerario
Las capacidades de enrutamiento basado en itinerario el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluyen un conjunto de claves de los artefactos definidos en varios ensamblados. Las siguientes tablas enumeran estos artefactos por categoría para ayudar a los programadores al trabajar con y extender la implementación del enrutamiento basado en itinerario con implementaciones de servicio itinerarios de ESB adicionales.  
  
## <a name="esb-itinerary-classes"></a>Clases de itinerarios de ESB  
 En la tabla siguiente se enumera los ensamblados y los artefactos contenidos en ESB. Proyecto de itinerarios. El nombre del ensamblado que lo contiene es **Microsoft.Practices.ESB.Itinerary.dll**.  
  
|Artefacto de clave|Description|  
|------------------|-----------------|  
|**MessageHelper**|Contiene todas las funciones privadas llamadas a otros artefactos de proyecto.|  
|**IItineraryStep**|La clase pública devuelto desde el **GetItineraryStep** método.|  
|**ResolverCollection**|Implementa una colección de todas las resoluciones asociado a un servicio. Esta clase se expone mediante el **IItineraryStep** de interfaz y se rellena con el **GetItineraryStep** método.|  
|**IMessagingService**|Define la interfaz implementada por servicios itinerarios basado en mensajería.|  
|**IMessagingService**|Generador para crear **IMessagingService** objetos basados en un nombre configuradas en Esb.config.|  
  
## <a name="esb-itinerary-messaging-services"></a>Servicios de mensajería itinerarios de ESB  
 En la tabla siguiente se enumera las clases definidas en el **Microsoft.Practices.ESB.Itinerary.Services.dll** ensamblado en **Microsoft.Practices.ESB.Itinerary.Services** espacio de nombres.  
  
|Artefacto de clave|Description|  
|------------------|-----------------|  
|**Enrutamiento**|Implementación de ESB itinerarios mensajería enrutamiento: invocado por componentes de ESB distribuidor o desensamblar el distribuidor mediante el archivo Esb.config.|  
|**Transformar**|Implementación de la itinerario ESB servicios de transformación de mensajería: invocado por componentes de ESB distribuidor o desensamblar el distribuidor mediante el archivo Esb.config.|  
  
 En la tabla siguiente se enumera los artefactos contenidos en el **Microsoft.Practices.ESB.Itinerary.Services.Broker.dll** ensamblado.  
  
|Artefacto de clave|Description|  
|------------------|-----------------|  
|**MessagingBroker**|Implementación de la itinerario ESB servicio de enrutamiento mediante el contexto del mensaje de mensajería: invocado por componentes de ESB distribuidor o desensamblar el distribuidor mediante el archivo Esb.config.|  
  
 Estos servicios también se definen en el archivo de configuración de BizTalk ESB Toolkit, Esb.config.  
  
## <a name="esb-itinerary-orchestration-services"></a>Servicios de orquestación itinerarios de ESB  
 En la tabla siguiente se enumera los artefactos contenidos en el **Microsoft.Practices.ESB.Agents.dll** ensamblado.  
  
|Artefacto de clave|Description|  
|------------------|-----------------|  
|Delivery.odx|Un ejemplo de servicio de orquestación itinerarios identificado por el nombre del servicio de enrutamiento **Microsoft.Practices.ESB.Services.Routing**.|  
|Transform.odx|Un ejemplo transformación orquestación itinerarios servicio identificado por el nombre del servicio **Microsoft.Practices.ESB.Services.Transform**.|  
  
## <a name="esb-itinerary-pipeline-components"></a>Componentes de canalización itinerarios de ESB  
 En la tabla siguiente enumera los ensamblados y los artefactos contenidos en el **Microsoft.Practices.ESB.Itinerary.PipelineComponents.dll** ensamblado.  
  
|Artefacto de clave|Description|  
|------------------|-----------------|  
|**Itinerario**|El componente de canalización de procesamiento de itinerarios principal que procesa y valida el itinerario de mensajes entrantes.|  
|**ItineraryCache**|El componente canalización almacenamiento en caché itinerarios para su uso en puertos de envío de petición-respuesta.|  
|**ItinerarySelector**|El componente de canalización de selector itinerarios que resuelve itinerarios de servidor en pendientes genéricas.|  
  
## <a name="esb-itinerary-pipelines"></a>Canalizaciones de itinerarios de ESB  
 En la tabla siguiente enumera los ensamblados y los artefactos contenidos en el **Microsoft.Practices.ESB.Itinerary.Pipelines.dll** ensamblado.  
  
|Artefacto de clave|Description|  
|------------------|-----------------|  
|ItineraryReceive|La canalización itinerario utilizada en el servicio Web de itinerario en rampa. Utilizar como una operación de recepción para ubicaciones de recepción de canalización y contiene los siguientes componentes de canalización:<br /><br /> Distribuidor ESB de itinerario, desensamblador XML, de ESB|  
|ItineraryReceivePassthrough||  
|ItineraryReceiveXml|La canalización itinerario utilizada en el servicio Web de itinerario en rampa. Utilizar como una operación de recepción para que ubicaciones de recepción enrutar un mensaje entrante a varios puntos de conexión de canalización y contiene los siguientes componentes de canalización:<br /><br /> Itinerario ESB, Desensamblador de distribuidor ESB|  
|ItinerarySend|La canalización itinerario utilizada en el itinerario fuera de rampa. Utilizar como un envío de canalización para un puerto de envío y contiene los siguientes componentes de canalización:<br /><br /> Caché de itinerarios de ESB de distribuidor, el ensamblador XML, de ESB|  
|ItinerarySendPassthrough|La canalización itinerario utilizada en el itinerario fuera de rampa. Utilizar como un envío de canalización para un puerto de envío y contiene los siguientes componentes de canalización:<br /><br /> Distribuidor ESB, caché itinerario de ESB|  
|ItinerarySendReceive|La canalización itinerario utilizada en el itinerario fuera de rampa. Usar como puerto de envío de una canalización de recepción para una petición-respuesta y contiene los siguientes componentes de canalización:<br /><br /> Distribuidor ESB de ESB caché itinerarios, desensamblador XML,|  
|ItineraryForwarderSendReceive|La canalización itinerario utilizada en el itinerario fuera de rampa. Utilizar como una operación de recepción para un puerto de envío de canalización y contiene los siguientes componentes de canalización:<br /><br /> Distribuidor ESB de caché itinerarios, desensamblador XML, ESB, reenviador|  
|ItineraryForwarderSendReceiveXml|La canalización itinerario utilizada en el servicio Web de itinerario en rampa. Utilizar como una operación de recepción para un puerto de envío de canalización y contiene los siguientes componentes de canalización:<br /><br /> Memoria caché de itinerarios de ESB, distribuidor ESB desensamblar, reenviador|  
|ItinerarySelectReceive|La canalización itinerario utilizada en el servicio Web de itinerario en rampa. Utilizar como una operación de recepción para ubicaciones de recepción de canalización y contiene los siguientes componentes de canalización:<br /><br /> Distribuidor ESB de ESB Selector itinerarios, desensamblador XML,|  
|ItinerarySelectReceivePassthrough|La canalización itinerario utilizada en el servicio Web de itinerario en rampa. Utilizar como una operación de recepción para ubicaciones de recepción de canalización y contiene los siguientes componentes de canalización:<br /><br /> Selector de itinerarios de ESB, distribuidor ESB|  
|ItinerarySelectReceiveXml|La canalización itinerario utilizada en el servicio Web de itinerario en rampa. Utilizar como una operación de recepción para ubicaciones de recepción de canalización y contiene los siguientes componentes de canalización:<br /><br /> Distribuidor ESB de desensamblador, Selector de itinerarios de ESB, XML|  
|ItinerarySelectSendReceive|La canalización itinerario utilizada en el itinerario fuera de rampa. Utilizar como una operación de recepción para un puerto de envío de canalización y contiene los siguientes componentes de canalización:<br /><br /> Desensamblador XML de caché de itinerarios, Selector de itinerarios de ESB, ESB, distribuidor ESB|  
  
## <a name="esb-itinerary-schemas"></a>Esquemas de itinerarios de ESB  
 En la tabla siguiente enumera los ensamblados y los artefactos contenidos en el **Microsoft.Practices.ESB.Itinerary.Schemas.dll** ensamblado.  
  
|Artefacto de clave|Description|  
|------------------|-----------------|  
|Itinerary.xsd|Define los encabezados SOAP itinerarios de ESB utilizados en basados en SOAP o Windows Communication Foundation WCF basados en Web service en-pendientes.|  
|ItineraryDescription.xsd|Este scehma representa datos de referencia itinerarios y debe usarse para enviar el mensaje en pendientes basados en WCF.|  
|Sistema-Properties.xsd|Define las propiedades de contexto de BizTalk ESB relacionados con itinerario.|