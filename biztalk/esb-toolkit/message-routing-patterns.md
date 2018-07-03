---
title: Patrones de enrutamientos de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d95c5ba0-122f-4793-bfce-a95830dfe094
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7233c5d5f5a3669cf23931afc29dfaac8548dc3d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022090"
---
# <a name="message-routing-patterns"></a>Patrones de enrutamiento de mensajes
Patrones de enrutamiento de mensajes definen directrices probadas para enrutar un mensaje a sus puntos de conexión de destino. El enrutamiento puede ser el resultado de una configuración estática, o pueden configurarse dinámicamente según una serie de criterios y mediante una serie de métodos.  
  
## <a name="message-router"></a>Enrutador de mensajes  
 El patrón de enrutador de mensajes determina al destinatario del mensaje en función de un conjunto de condiciones. Para obtener una descripción detallada de este patrón, vea [enrutador de mensajes](http://go.microsoft.com/fwlink/?LinkId=186844) ([http://go.microsoft.com/fwlink/?LinkId=186844](http://go.microsoft.com/fwlink/?LinkId=186844)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón en el Diseñador de itinerarios es una combinación de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario servicio de enrutamiento y una resolución basada en contenido única. El servicio de enrutamiento itinerario es responsable para promocionar las propiedades de enrutamiento de mensajes en el contexto del mensaje de BizTalk de Microsoft o de enrutamiento explícita de un mensaje.  
  
 Puede elegir el servicio de enrutamiento itinerario proporcionado por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] como sigue:  
  
- Definir el servicio de enrutamiento itinerario con un extensor de mensajería para ejecutar en una canalización de BizTalk mediante el Diseñador de itinerario.  
  
- Definir el servicio de enrutamiento itinerario con un extensor de orquestación que se ejecutarán como una orquestación mediante el Diseñador de itinerario que realiza el enrutamiento mediante los puertos de envío de BizTalk.  
  
  La resolución asociada con el servicio de enrutamiento itinerario determina al destinatario del mensaje, según el contenido del mensaje. Puede elegir entre las resoluciones que compatibilidad con enrutamiento por contenidos proporcionados por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], o puede implementar su propia resolución.  
  
  Para obtener un ejemplo de la implementación de este patrón en el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], consulte los siguientes recursos:  
  
- [Cómo: Resolver un punto de conexión de servicio mediante una búsqueda de claves de enlace de UDDI](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
- [Cómo: Resolver un punto de conexión de servicio mediante una búsqueda de categorías de UDDI](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
## <a name="content-based-router"></a>Enrutador basado en contenido  
 El patrón de enrutador basado en contenido determina al destinatario de un mensaje en función del contenido del mensaje. Para obtener una descripción detallada de este patrón, vea [enrutador basado en contenido](http://go.microsoft.com/fwlink/?LinkId=186839) ([http://go.microsoft.com/fwlink/?LinkId=186839](http://go.microsoft.com/fwlink/?LinkId=186839)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón en el Diseñador de itinerarios es una combinación de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario servicio de enrutamiento y una resolución basada en contenido única. El servicio de enrutamiento itinerario es responsable de promocionar las propiedades de enrutamiento de mensajes en el contexto del mensaje de BizTalk o para enrutar un mensaje de forma explícita.  
  
 Puede elegir el servicio de enrutamiento itinerario proporcionado por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] como sigue:  
  
- Definir un servicio de enrutamiento itinerarios con un extensor de mensajería para ejecutar en una canalización de BizTalk mediante el Diseñador de itinerario.  
  
- Definir un servicio de enrutamiento itinerarios con un extensor de orquestación que se ejecutarán como una orquestación mediante el Diseñador de itinerario, que lleva a cabo el enrutamiento mediante los puertos de envío de BizTalk.  
  
- Definir un servicio de itinerarios de agente con un extensor de mensajería de agente para ejecutarse en una canalización de BizTalk mediante el Diseñador de itinerario.  
  
  La resolución asociada con el servicio de enrutamiento de itinerarios determina al destinatario del mensaje según el contenido del mensaje. Puede elegir entre las resoluciones siguientes esa compatibilidad con enrutamiento por contenidos proporcionados por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
- **Resolución XPATH**. Al usar a esta resolución, puede enrutar el contenido del mensaje mediante consultas XPATH.  
  
- **Resolución BRE**. Al usar a esta resolución, puede recuperar información de enrutamiento de contenido del mensaje mediante el motor de reglas de BizTalk.  
  
- **Solucionador de contexto del mensaje**. Mediante esta resolución, puede recuperar el contenido de un mensaje del contexto del mensaje de BizTalk al que está asociada con un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] de service broker de itinerarios.  
  
  > [!NOTE]
  >  Además de los escenarios de implementación anterior, puede desarrollar un solucionador personalizado basado en contenido y la solución de enrutamiento de itinerarios como un servicio basado en mensajería o basado en la orquestación. En este caso, es posible que deba implementar los objetos Extender para el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario y la resolución de servicio para interoperar con el Diseñador de itinerario.  
  
  Por ejemplo, de esta implementación, consulte los siguientes recursos:  
  
- [Instalación y ejecución del ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
- [Cómo: Implementar el enrutamiento basado en contenido mediante una directiva de reglas de negocio para un tipo de mensaje conocido](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
- [Cómo: Enrutar dinámicamente un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocio](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
## <a name="routing-slip"></a>Lista de distribución  
 El patrón de lista de distribución describe un escenario en el que un mensaje debe enrutarse a través de una serie de componentes en un orden predefinido, que es posible que no se conoce en el tiempo de diseño. Para obtener una descripción detallada de este patrón, vea [lista de distribución](http://go.microsoft.com/fwlink/?LinkId=186840) ([http://go.microsoft.com/fwlink/?LinkId=186840](http://go.microsoft.com/fwlink/?LinkId=186840)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón proporciona el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]; su implementación depende del tipo de aplicación cliente que envía un mensaje para el procesamiento basado en itinerarios:  
  
- **Proxy de servicio**. Con este tipo de aplicación, configurar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] vía rápida con el componente de canalización de Selector de itinerarios y asociar un solucionador de itinerarios para seleccionar la apropiada [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario. Se pueden configurar las propiedades de itinerarios como propiedades estáticas mediante la resolución de itinerario, o se pueden configurar como propiedades dinámicas mediante la resolución de motor de reglas de BizTalk y BRI.  
  
- **Cliente avanzado**. Con este tipo de aplicación, configurar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] vía rápida con el componente de canalización de Selector de itinerario y la resolución de itinerario estático. La aplicación cliente envía un mensaje con un encabezado de itinerarios de referencia, que contiene el nombre de itinerarios, la versión y el identificador de seguimiento.  
  
- **Cliente adaptable**. Con este tipo de aplicación, la aplicación cliente invoca el servicio de resolución, que, a su vez, identifica la referencia de itinerarios pasando el estado del cliente como un mensaje de solicitud. Si se resuelve el itinerario, la aplicación cliente envía un mensaje con referencias de itinerarios en la misma manera que en el escenario anterior del cliente avanzado.  
  
  Para obtener más información acerca de cómo implementar este patrón, vea los siguientes recursos:  
  
- [Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
- [Cómo: Transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución de itinerarios](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
  > [!NOTE]
  >  Además de los escenarios anteriores, puede desarrollar un solucionador personalizado de itinerarios y servicios de enrutamiento de itinerarios. Es posible que considere la posibilidad de crear extensores de diseñador para los servicios de itinerarios personalizados para su uso en el Diseñador de itinerario.  
  
## <a name="scatter-gather"></a>Dispersión y recopilación  
 El patrón de dispersión y recopilación permite que los mensajes se envíen a varios destinatarios y agregar sus respuestas; Esto da como resultado un único mensaje. Para obtener una descripción detallada de este patrón, vea [dispersión y recopilación](http://go.microsoft.com/fwlink/?LinkId=186841) ([http://go.microsoft.com/fwlink/?LinkId=186841](http://go.microsoft.com/fwlink/?LinkId=186841)) en el sitio de patrones de integración empresarial.  
  
 Para obtener un ejemplo de implementar este patrón, vea el [instalar y ejecutar el ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md) ejemplo.  
  
## <a name="recipient-list"></a>Lista de destinatarios  
 El patrón de lista de destinatarios aborda la solución de escenario en el que se enruta un mensaje a uno o más destinatarios. La lista de destinatarios puede ser definido estáticamente (lo que significa que tiene una lista fija de destinatarios) o dinámicamente. Para obtener una descripción detallada de este patrón, vea [lista de destinatarios](http://go.microsoft.com/fwlink/?LinkId=186842) ([http://go.microsoft.com/fwlink/?LinkId=186842](http://go.microsoft.com/fwlink/?LinkId=186842)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón en el Diseñador de itinerarios es una combinación de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario servicio de enrutamiento y varias resoluciones. El servicio de enrutamiento itinerario es responsable de la clonación de un mensaje y, a continuación, utilizar sus propiedades de contexto de mensaje de BizTalk para enrutar un mensaje de forma explícita.  
  
 Puede elegir el servicio de enrutamiento itinerario proporcionado por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] como sigue:  
  
- Definir el servicio de enrutamiento itinerario con un extensor de mensajería para ejecutar en la canalización de BizTalk con el Diseñador de itinerario.  
  
- Definir el servicio de enrutamiento itinerario con un extensor de mensajería que se ejecutarán como una orquestación mediante el Diseñador de itinerario, que lleva a cabo el enrutamiento mediante los puertos de envío de BizTalk.  
  
  La resolución asociada con el servicio de enrutamiento de itinerarios determina al destinatario del mensaje según el contenido del mensaje. Puede elegir el conjunto de resoluciones proporcionadas por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] para implementar este escenario. Para obtener más información acerca de cómo implementar este patrón, vea el siguiente recurso:  
  
- [Cómo: Enrutar un solo mensaje a varios destinatarios mediante una lista de distribución de itinerarios](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
## <a name="splitter"></a>Divisor  
 El patrón divisor aborda el problema cuando un mensaje único debe dividirse en varios mensajes. Para obtener una descripción detallada de este patrón, vea [divisor](http://go.microsoft.com/fwlink/?LinkId=186843) ([http://go.microsoft.com/fwlink/?LinkId=186843](http://go.microsoft.com/fwlink/?LinkId=186843)) en el sitio de patrones de integración empresarial. Para obtener más información acerca de cómo implementar este patrón, vea el siguiente recurso:  
  
-   [Cómo: Dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos mediante distintos itinerarios](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)