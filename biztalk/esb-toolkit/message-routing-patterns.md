---
title: Patrones de enrutamientos de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d95c5ba0-122f-4793-bfce-a95830dfe094
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a332a8ab942363ff5224f34149b345c9c7d40698
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-routing-patterns"></a>Patrones de enrutamiento de mensajes
Patrones de enrutamiento de mensajes definen directrices comprobadas para enrutar un mensaje a su punto de conexión de destino. Enrutamiento puede ser el resultado de una configuración estática, o pueden configurarse dinámicamente en función de una serie de criterios y usando una serie de métodos.  
  
## <a name="message-router"></a>Enrutador de mensajes  
 El patrón de enrutador de mensajes determina al destinatario del mensaje en función de un conjunto de condiciones. Para obtener una descripción detallada de este patrón, vea [mensaje enrutador](http://go.microsoft.com/fwlink/?LinkId=186844) ([http://go.microsoft.com/fwlink/?LinkId=186844](http://go.microsoft.com/fwlink/?LinkId=186844)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón en el Diseñador de itinerario es una combinación de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario servicio de enrutamiento y un solucionador de contenido único. El servicio de enrutamiento itinerario es responsable para la promoción de propiedades de enrutamiento de mensajes en el contexto del mensaje de BizTalk de Microsoft o de enrutamiento explícita de un mensaje.  
  
 Puede elegir el servicio de enrutamiento itinerario proporcionado por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] como se indica a continuación:  
  
-   Defina el servicio de enrutamiento itinerario con un extensor de mensajería para ejecutar en una canalización de BizTalk mediante el Diseñador de itinerario.  
  
-   Defina el servicio de enrutamiento itinerario con un extensor de orquestación para ejecutarse como una orquestación mediante el Diseñador de itinerario que realiza el enrutamiento mediante puertos de envío de BizTalk.  
  
 La resolución asociada con el servicio de enrutamiento itinerario determina al destinatario del mensaje, en función del contenido del mensaje. Puede elegir entre las resoluciones esa compatibilidad con enrutamiento por contenidos proporcionada por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], o puede implementar su propia resolución.  
  
 Para obtener un ejemplo de la implementación de este patrón en el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], consulte los siguientes recursos:  
  
-   [Cómo: resolver un extremo de servicio mediante una búsqueda de la clave de enlace de UDDI](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [Cómo: resolver un extremo de servicio mediante una búsqueda de la categoría UDDI](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
## <a name="content-based-router"></a>Enrutador basado en contenido  
 El patrón de enrutador basado en contenido determina al destinatario de un mensaje basándose en el contenido del mensaje. Para obtener una descripción detallada de este patrón, vea [enrutador basado en contenido](http://go.microsoft.com/fwlink/?LinkId=186839) ([http://go.microsoft.com/fwlink/?LinkId=186839](http://go.microsoft.com/fwlink/?LinkId=186839)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón en el Diseñador de itinerario es una combinación de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario servicio de enrutamiento y un solucionador de contenido único. El servicio de enrutamiento itinerario es responsable para la promoción de propiedades de enrutamiento de mensajes en el contexto de mensaje de BizTalk ni para enrutar un mensaje de forma explícita.  
  
 Puede elegir el servicio de enrutamiento itinerario proporcionado por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] como se indica a continuación:  
  
-   Definir un servicio de enrutamiento itinerario con un extensor de mensajería para ejecutar en una canalización de BizTalk mediante el Diseñador de itinerario.  
  
-   Definir un servicio de enrutamiento itinerario con un extensor de orquestación para ejecutarse como una orquestación mediante el Diseñador de itinerario, que lleva a cabo el enrutamiento mediante puertos de envío de BizTalk.  
  
-   Definir un servicio de agente itinerarios con un extensor de mensajería de agente para ejecutar en una canalización de BizTalk mediante el Diseñador de itinerario.  
  
 La resolución asociada con el servicio de enrutamiento itinerario determina al destinatario del mensaje en función del contenido del mensaje. Puede elegir entre las siguientes resoluciones esa compatibilidad con enrutamiento por contenidos proporcionada por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
-   **Resolución XPATH**. Al usar a esta resolución, es posible distribuir contenido del mensaje mediante consultas XPATH.  
  
-   **Resolución BRE**. Al usar a esta resolución, puede recuperar la información de enrutamiento del contenido del mensaje utilizando el motor de reglas de BizTalk.  
  
-   **Resolución de contexto de mensaje**. Al usar esta resolución, puede recuperar el contenido de un mensaje desde el contexto del mensaje de BizTalk al que está asociado un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] de service broker itinerarios.  
  
    > [!NOTE]
    >  Además de los escenarios de implementación anterior, puede desarrollar una solución de enrutamiento itinerario y solucionador personalizado basado en contenido como un servicio basado en mensajería o basado en la orquestación. En este caso, debe implementar los extensores para el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] servicio de resolución e itinerario para interoperar con el Diseñador de itinerario.  
  
 Por ejemplo de esta implementación, vea los siguientes recursos:  
  
-   [Instalar y ejecutar el ejemplo en rampa itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [Cómo: implementar enrutamiento por contenidos mediante una empresa de reglas de directiva para un tipo de mensaje conocido](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [Cómo: dinámicamente enrutar un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocios](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
## <a name="routing-slip"></a>Lista de distribución  
 El patrón de lista de distribución describe un escenario en el que un mensaje debe enrutarse a través de una serie de componentes en un orden predefinido, que no puede conocerse en tiempo de diseño. Para obtener una descripción detallada de este patrón, vea [lista de distribución](http://go.microsoft.com/fwlink/?LinkId=186840) ([http://go.microsoft.com/fwlink/?LinkId=186840](http://go.microsoft.com/fwlink/?LinkId=186840)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón es proporcionada por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]; su implementación depende del tipo de aplicación cliente que envía un mensaje para el procesamiento de itinerario:  
  
-   **Proxy de servicio**. Con este tipo de aplicación, configurar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] en aumento con el componente de canalización de Selector de itinerario y asociar un solucionador itinerario para seleccionar la apropiada [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario. Las propiedades itinerarios se pueden configurar como propiedades estáticas mediante el Solucionador de itinerario o se pueden configurar como propiedades dinámicas mediante el motor de reglas de BizTalk y BRI solucionador.  
  
-   **Cliente avanzado**. Con este tipo de aplicación, configurar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] en aumento con el componente de canalización de itinerario Selector y la resolución de itinerario estático. La aplicación cliente envía un mensaje con un encabezado itinerarios de referencia, que contiene el nombre itinerario, la versión y el identificador de seguimiento.  
  
-   **Cliente adaptable**. Con este tipo de aplicación, la aplicación cliente invoca el servicio de resolución, que identifica a su vez, la referencia itinerario pasando el estado del cliente como un mensaje de solicitud. Si se resuelve el itinerario, la aplicación cliente envía un mensaje con referencias itinerarios en la misma manera que en el escenario de cliente avanzado anterior.  
  
 Para obtener más información acerca de cómo implementar este patrón, vea los siguientes recursos:  
  
-   [Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [Cómo: transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución itinerario](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
    > [!NOTE]
    >  Además de los escenarios anteriores, puede desarrollar un solucionador personalizado itinerario y servicios de enrutamiento itinerarios. Considere la creación de diseñadores extensores para servicios itinerarios personalizados para su uso en el Diseñador de itinerario.  
  
## <a name="scatter-gather"></a>Dispersión y recopilación  
 El patrón de dispersión y recopilación permite que los mensajes se envíen a varios destinatarios y agregar sus respuestas; Esto da como resultado un único mensaje. Para obtener una descripción detallada de este patrón, vea [dispersión y recopilación](http://go.microsoft.com/fwlink/?LinkId=186841) ([http://go.microsoft.com/fwlink/?LinkId=186841](http://go.microsoft.com/fwlink/?LinkId=186841)) en el sitio de patrones de integración empresarial.  
  
 Para obtener un ejemplo de la implementación de este patrón, vea el [instalar y ejecutar el ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md) ejemplo.  
  
## <a name="recipient-list"></a>Lista de destinatarios  
 El patrón de lista de destinatarios aborda la solución de escenario en el que se enruta un mensaje a uno o más destinatarios. La lista de destinatarios puede definir estáticamente (lo que significa que tiene una lista fija de destinatarios) o dinámicamente. Para obtener una descripción detallada de este patrón, vea [lista de destinatarios](http://go.microsoft.com/fwlink/?LinkId=186842) ([http://go.microsoft.com/fwlink/?LinkId=186842](http://go.microsoft.com/fwlink/?LinkId=186842)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón en el Diseñador de itinerario es una combinación de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario servicio de enrutamiento y varias resoluciones. El servicio de enrutamiento itinerario es responsable de la clonación de un mensaje y, a continuación, usar sus propiedades de contexto de mensaje de BizTalk para enrutar un mensaje de forma explícita.  
  
 Puede elegir el servicio de enrutamiento itinerario proporcionado por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] como se indica a continuación:  
  
-   Defina el servicio de enrutamiento itinerario con un extensor de mensajería para ejecutar en la canalización de BizTalk con el Diseñador de itinerario.  
  
-   Defina el servicio de enrutamiento itinerario con un extensor de mensajería para ejecutarse como una orquestación mediante el Diseñador de itinerario, que lleva a cabo el enrutamiento mediante puertos de envío de BizTalk.  
  
 La resolución asociada con el servicio de enrutamiento itinerario determina al destinatario del mensaje en función del contenido del mensaje. Puede elegir el conjunto de solucionadores proporcionados por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] para implementar este escenario. Para obtener más información acerca de cómo implementar este patrón, vea el siguiente recurso:  
  
-   [Cómo: enrutar un mensaje único a varios destinatarios mediante una lista de distribución itinerarios](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
## <a name="splitter"></a>Divisor  
 El patrón divisor corrige el problema cuando un único mensaje debe dividirse en varios mensajes. Para obtener una descripción detallada de este patrón, vea [divisor](http://go.microsoft.com/fwlink/?LinkId=186843) ([http://go.microsoft.com/fwlink/?LinkId=186843](http://go.microsoft.com/fwlink/?LinkId=186843)) en el sitio de patrones de integración empresarial. Para obtener más información acerca de cómo implementar este patrón, vea el siguiente recurso:  
  
-   [Cómo: dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos utilizando distintos itinerarios](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)