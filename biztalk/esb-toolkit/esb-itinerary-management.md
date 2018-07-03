---
title: Administración de itinerarios de ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f78240de-34da-4751-aceb-b69d81403124
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a17da64d784d433d18720ca9a0c35c359fffb7b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966109"
---
# <a name="esb-itinerary-management"></a>Administración de itinerarios de ESB
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ofrece dos opciones distintas para la administración de itinerarios de ESB: centralizadas y descentralizadas. Esta sección describen las ventajas y riesgos para cada una de estas opciones.  
  
## <a name="decentralized-esb-policy-management"></a>Administración de directivas de ESB descentralizada  
 En este escenario, la aplicación de cliente ESB proporciona el contenido de los itinerarios ESB como datos adjuntos para cada mensaje enviado a ESB. El mensaje contiene un encabezado SOAP con el contenido de itinerarios; Cuando un componente de canalización recibe el mensaje, descodifica el mensaje y, a continuación, promueve el itinerario para el contexto del mensaje para continuar con el enrutamiento. Aunque este diseño proporciona la oportunidad de implementar fácilmente un patrón de lista de distribución, completamente lo que permite controlar el flujo de un mensaje al cliente presenta los siguientes problemas:  
  
- Por lo que permite al cliente determinar qué procesos se deben aplicar a un mensaje, los detalles de los procesos disponibles para elegir son transparentes para la aplicación de cliente ESB. Esta práctica podría exponer información confidencial de itinerarios ESB al cliente.  
  
- Además de los posibles problemas de seguridad, que permite al cliente administrar los itinerarios para que se envía con cada mensaje no exige itinerarios ESB como directiva a menos que se implementa para un cliente específico. Por lo tanto, los costos de administración de cambios para aplicar una nueva versión del itinerario son extremadamente altos y aumentarán para cada nuevo tipo específico de una aplicación cliente de confianza.  
  
- Por lo que permite al cliente que pase el itinerario completo con el mensaje enviado, el cliente siempre debe estar ubicado en el subsistema de confianza; en caso contrario, los itinerarios ESB potencialmente podrían especificar las instrucciones de procesamiento malintencionado que ya no son válidas.  
  
  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite el procesamiento de itinerarios enviados por el cliente; Sin embargo, esta opción solo debe usarse para fines de prueba y la compatibilidad con versiones anteriores.  
  
  Para obtener más información acerca de cómo habilitar los itinerarios del lado cliente, consulte [mediante un componente de canalización para leer un itinerario](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md).  
  
## <a name="centralized-esb-policy-management"></a>Administración de directivas centralizada de ESB  
 Existen problemas de sincronización y de seguridad posibles inherentes con lo que permite a un cliente enviar mensajes con itinerarios asociados, por lo que es el procedimiento recomendado administrar los itinerarios ESB en un repositorio central que se implementa como una base de datos SQL y se incluye en [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] para este propósito. Mediante la implementación de itinerarios en una ubicación central, pueden administrarse fácilmente las directivas de itinerarios de ESB y modificar sin necesidad de implementar cambios drásticos de lado cliente, y la organización puede controlar el procesamiento de mensajes sin exponer potencialmente información confidencial al cliente.  
  
 Se proporcionan los componentes de canalización especializado para determinar el itinerarios ESB adecuado para adjuntar a un mensaje entrante. Este enfoque ofrece dos opciones distintas para enviar un mensaje para el enrutamiento basado en itinerarios:  
  
-   Con la primera opción, la aplicación cliente todavía puede indicar un distintos itinerarios ESB proporcionando información de referencia de itinerarios de ESB en el encabezado SOAP, junto con el mensaje de solicitud, en lugar de enviar un itinerario completo. Esta información incluye el nombre de itinerarios de ESB y la versión opcional. En este escenario, los clientes todavía pueden especificar cómo se puede enrutar el mensaje, pero no hay ningún riesgo de comprometer la seguridad o de errores de sincronización de la directiva mediante la exposición de contenido de los itinerarios ESB a las aplicaciones cliente.  
  
-   La segunda opción consiste en configurar la rampa de ESB para determinar automáticamente los itinerarios ESB adecuado, según el contenido o el contexto del mensaje, sin requerir ninguna información de encabezado desde el cliente envío. Este escenario permite que la organización controlar el flujo de un mensaje enviado y elimina la necesidad de tener en cuenta cómo se está enrutando el mensaje al cliente.