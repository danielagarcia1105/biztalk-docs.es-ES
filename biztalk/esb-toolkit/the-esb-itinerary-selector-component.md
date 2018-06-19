---
title: El componente de Selector itinerarios de ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2cd8a85-e036-4817-9541-3fd720ca04ef
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83cdd0b2022eb7dc4ad78e5702f5c21e4c4f432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295156"
---
# <a name="the-esb-itinerary-selector-component"></a>El componente de Selector itinerarios de ESB
El componente de ESB itinerario Selector permite los mensajes entrantes que no tiene el encabezado SOAP para pasar a través de ESB seleccionando un itinerario de servidor adecuado para el mensaje con la Ayuda de un solucionador de itinerario. El componente se utiliza también para los mensajes que usan un encabezado SOAP para definir el nombre y la versión de un itinerario, como se solicitó el cliente.  
  
## <a name="installation"></a>Installation  
 Al instalar el núcleo de ESB automáticamente se instala el **ItinerarySelector** componente en la carpeta de componentes de canalización de BizTalk Server.  
  
## <a name="how-it-works"></a>Funcionamiento  
 El componente de ESB itinerario Selector es un componente de canalización de BizTalk de Microsoft que sólo puede residir en una canalización de recepción. El componente selecciona un itinerario del lado servidor para su uso en el procesamiento de un mensaje. A medida que el mensaje pasa a través del componente en una canalización de recepción, el componente lee su configuración y usa el **ResolverConnectionString** propiedad que se va a llamar a la resolución correcta que se buscará el itinerario adecuado que se utiliza al procesar el mensaje. El componente de Selector de itinerario, a continuación, realiza los mismos pasos que el componente de canalización de itinerario para validar el mensaje y promocionar las propiedades necesarias para asegurarse de que el mensaje sigue a la siguiente fase de procesamiento.  
  
## <a name="using-the-esb-itinerary-selector-component"></a>Mediante el componente de Selector itinerarios de ESB  
 Puede agregar el componente de ESB itinerario a una canalización de recepción y, a continuación, usar la canalización en una ubicación de recepción. Cuando este componente está configurado con la resolución estática de itinerario en WCF en rampa, el nombre y la versión de la itinerario solicitado por el cliente (como se representa en el encabezado SOAP) se recupera del contexto del mensaje y se utiliza para seleccionar el adecuado itinerario.  
  
## <a name="component-properties"></a>Propiedades de componente  
 El componente de Selector de itinerario ESB expone tres propiedades públicas:  
  
-   **IgnoreErrorKey**. Esta propiedad define si, si se devuelve un error por la resolución, se debe procesar el mensaje sin el itinerario (cuando se establece en **True**) o en suspensión.  
  
-   **ItineraryFactKey**. Esto representa la clave del diccionario devuelto por la resolución que contiene el XML real el itinerario seleccionado. Por lo general, **Resolver.Itinerary**, a menos que se utiliza una resolución personalizada.  
  
-   **ResolverConnectionString**. Se trata de una cadena de conexión de resolución que contiene pares de nombre / valor que se puede utilizar un solucionador para seleccionar o búsqueda un itinerario.