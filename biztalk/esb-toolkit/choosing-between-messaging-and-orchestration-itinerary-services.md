---
title: "Elegir entre mensajería y orquestación itinerarios servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 694f929a-c830-4906-8e97-4fbd50e70133
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 735d8411f2587e8e241773c4ebb8f98d29f3abed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="choosing-between-messaging-and-orchestration-itinerary-services"></a>Elegir entre mensajería y orquestación itinerarios servicios
Itinerarios servicios pueden configurarse para que se produzca en el subsistema de mensajería o el subsistema de orquestación de [!INCLUDE[prague](../includes/prague-md.md)]. Estos servicios de mensajería itinerarios de ESB están configurados para procesar el mensaje y se pueden ejecutar en una canalización de BizTalk Server (en rampa o fuera de rampa). Esta opción permite al programador definir exactamente donde en la canalización el servicio se ejecutará. Naturalmente, se ejecutarán los servicios configurados para el procesamiento en el subsistema de orquestación en una orquestación de BizTalk.  
  
## <a name="esb-itinerary-messaging-services"></a>Servicios de mensajería itinerarios de ESB  
 Cuando se procesa un mensaje en una canalización de BizTalk Server, utilizando los servicios de mensajería itinerarios de ESB reduce la latencia de mensajes. Mediante la implementación de servicios de extremo a extremo en una sola canalización, es posible transformar un mensaje varias veces y enrutar el mensaje a sus puntos de conexión con solo una persistencia única para la base de datos de cuadro de mensaje. Además, el procesamiento basado en mensajería elimina el costo de recursos adicionales de procesamiento de orquestación. Por lo general, procesamiento basado en mensajería consume menos recursos y proporciona un procesamiento más rápido que el procesamiento de orquestación. En las canalizaciones, el distribuidor de ESB y ESB distribuidor desensamblar componentes proporcionados por la canalización [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] actúe como interceptores de mensajes y ejecutar servicios itinerarios basado en mensajería, si se trata de una ruta, transformación o un servicio personalizado. Para obtener más información acerca de cómo configurar estos componentes, consulte [el componente de distribuidor de ESB](../esb-toolkit/the-esb-dispatcher-component.md) y [el componente ESB distribuidor desensamblar](../esb-toolkit/the-esb-dispatcher-disassemble-component.md).  
  
## <a name="esb-itinerary-orchestration-services"></a>Servicios de orquestación itinerarios de ESB  
 Si el enrutamiento dinámico debe tener lugar entre o después de los procesos de orquestación, utilice procesamiento basado en la orquestación para el servicio de itinerarios. De forma predeterminada, los servicios basados en la orquestación reciben el mensaje como un documento XML. La orquestación de enrutamiento usa el Administrador de resolución para intentar resolver los puntos de conexión identificados en el itinerario. El Administrador de adaptador usa la respuesta desde el Administrador de resolución para promocionar los detalles del extremo en el contexto del mensaje y el mensaje se publica en la base de datos de cuadro de mensaje con un puerto lógico de enlace directo. En este punto, se produce el enrutamiento de BizTalk regular y el puerto de envío dinámico se configura mediante las propiedades promocionadas del mensaje.  
  
 La orquestación de servicio de itinerario incluida proporciona un buen punto de partida para crear servicios itinerarios personalizados basados en la orquestación. Para obtener más información acerca de cómo crear servicios itinerarios personalizados, consulte [modificar y extender el Kit de herramientas de ESB de BizTalk](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).