---
title: "Con los componentes de compatibilidad de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df0346ea-15d4-49c5-98d8-f9ec06f4e036
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6313a337e8527f3fb275f7c15745a5a7f6552151
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-pipeline-support-components"></a>Uso de los componentes de compatibilidad de canalización
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye los siguientes componentes de canalización:  
  
-   **Selector de itinerarios de ESB**. Puede usar este componente en el lado de recepción (en una canalización de recepción) para seleccionar un itinerario de servidor a seguir un mensaje. Para obtener más información, consulte [el componente de Selector de itinerario ESB](../esb-toolkit/the-esb-itinerary-selector-component.md).  
  
-   **Itinerario ESB**. Puede utilizar este componente en el lado de recepción (en una canalización de recepción) para promocionar las propiedades de metadatos ESB de encabezados SOAP en el contexto del mensaje. Para obtener más información, consulte [el componente de itinerario ESB](../esb-toolkit/the-esb-itinerary-component.md).  
  
-   **Reenviador itinerario de ESB**. Para obtener más información, consulte [el componente de reenviador de itinerario ESB](../esb-toolkit/the-esb-itinerary-forwarder-component.md).  
  
-   **Caché de itinerarios de ESB**. Puede usar este componente para itinerarios de caché y volver a aplicarlos a los mensajes de respuesta recibidos en puertos de envío de petición-respuesta. Para obtener más información, consulte [el componente de itinerario ESB](../esb-toolkit/the-esb-itinerary-component.md).  
  
-   **Descodificador de ESB JMS**. Puede usar este componente en el lado de recepción (en una ubicación de recepción) de una orquestación o un puerto de envío para analizar los encabezados de JMS de IBM (MQRFH2) y mantenerlos como propiedades de contexto. A continuación, puede tener acceso a estas propiedades de contexto y modificarlas en la misma manera que otras propiedades de contexto de BizTalk. Para obtener más información, consulte [el ESB JMS codificador y descodificador componentes](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md).  
  
-   **Codificador de ESB JMS**. Puede usar este componente en un puerto de envío para escribir encabezados JMS de IBM (MQRFH2) a los mensajes. Para obtener más información, consulte [el ESB JMS codificador y descodificador componentes](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md).  
  
-   **ESB agregar Namespace**. Puede usar este componente en una ubicación de recepción o un puerto de envío para agregar espacios de nombres a los documentos XML. Para obtener más información, consulte [el Namespace de ESB agregar y quitar componentes de Namespace](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md).  
  
-   **ESB quitar Namespace**. Puede usar este componente en una ubicación de recepción o un puerto de envío para quitar los espacios de nombres de documentos XML. Para obtener más información, consulte [el Namespace de ESB agregar y quitar componentes de Namespace](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md).  
  
-   **Codificador de excepción de ESB**. Puede utilizar este componente para enviar mensajes de error en el sistema de archivos, Microsoft InfoPath o Microsoft SharePoint. Este componente es parte de la excepción de ESB mecanismo de control, y lo normaliza y enriquece todas las excepciones que se procesan por un puerto de envío. El componente serializa información de excepción (incluida mensajes persistentes incrustados y las propiedades de contexto) en un formato canónico para que todos los contenidos de mensajes y la propia excepción están disponibles.  
  
-   **Transformación ESB**. Puede utilizar este componente para transformar el mensaje de un formato a otro mediante la especificación de asignación de BizTalk.  
  
-   **Herramienta de seguimiento de BAM de ESB**. Puede utilizar este componente para interceptar el mensaje de error emitido desde el codificador de excepción de ESB e insertar los datos en el mensaje en la tabla de importación principal de BAM (mediante la secuencia de eventos BAM en la canalización). Este componente es parte de la excepción de ESB mecanismo de control.  
  
-   **Distribuidor ESB**. Puede usar este componente en una ubicación de recepción (canalización de entrada) para establecer propiedades de la ubicación de punto de conexión para los mensajes salientes de forma dinámica. También puede usar este componente en la canalización de envío para ejecutar servicios de mensajería itinerarios. Para obtener más información, consulte [el componente de distribuidor de ESB](../esb-toolkit/the-esb-dispatcher-component.md).  
  
-   **Distribuidor ESB desensamblar**. Puede usar este componente en una ubicación de recepción (canalización de entrada) para establecer propiedades de la ubicación de punto de conexión para los mensajes salientes de forma dinámica. El comportamiento de este componente es similar al componente de distribuidor de ESB, salvo que transforma el mensaje de resultado (si especifica un valor para el **Nombredemapa** propiedad). El mensaje pasa a través del desensamblador XML, lo que promueve propiedades y los tipos de mensaje. El componente de distribuidor de ESB desensamblar también admite el envío por lotes de varios mensajes a distintos extremos. Para obtener más información, consulte [el componente ESB distribuidor desensamblar](../esb-toolkit/the-esb-dispatcher-disassemble-component.md).