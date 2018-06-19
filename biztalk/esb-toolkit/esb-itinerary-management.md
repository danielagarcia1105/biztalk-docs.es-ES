---
title: Administración de itinerarios de ESB | Documentos de Microsoft
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
ms.openlocfilehash: 6fb7c2566cbd445ea305089033935427b82046bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294340"
---
# <a name="esb-itinerary-management"></a>Administración de itinerarios de ESB
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ofrece dos opciones diferentes para la administración de itinerarios de ESB: centralizada y descentralizada. Esta sección describen las ventajas y riesgos de cada una de estas opciones.  
  
## <a name="decentralized-esb-policy-management"></a>Administración de directivas ESB descentralizado  
 En este escenario, la aplicación de cliente ESB proporciona el contenido de la itinerario ESB como datos adjuntos para cada mensaje enviado a ESB. El mensaje contiene un encabezado SOAP con el contenido itinerario; Cuando un componente de canalización recibe el mensaje, descodifica el mensaje y, a continuación, promueve el itinerario en el contexto del mensaje para continuar con el enrutamiento. Aunque este diseño proporciona la oportunidad de implementar un patrón de lista de distribución, totalmente permitiendo al cliente controlar el flujo de un mensaje presenta los siguientes problemas:  
  
-   Si se permite al cliente determinar cuáles son los procesos que se deben aplicar a un mensaje, los detalles de los procesos disponibles desde el que se pueden elegir son transparentes para la aplicación de cliente ESB. Esta práctica podría exponer información confidencial de itinerario ESB al cliente.  
  
-   Además de los posibles problemas de seguridad, que permite al cliente administrar los itinerarios para que se envía con cada mensaje no exige itinerario ESB como directiva a menos que se implementa para un cliente específico. Por lo tanto, los costos de administración de cambios para aplicar una nueva versión de la itinerario son sumamente elevados y aumentarán para cada nuevo tipo específico de una aplicación de cliente de confianza.  
  
-   Al permitir que el cliente pasar el itinerario completo con el mensaje enviado, el cliente siempre debe estar ubicado en el subsistema de confianza; en caso contrario, el itinerario ESB potencialmente podría especificar las instrucciones de procesamiento malintencionado que ya no son válidas.  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]admite procesamiento itinerarios enviadas por el cliente; Sin embargo, esta opción solo debe usarse para la compatibilidad con versiones anteriores y con fines de prueba.  
  
 Para obtener más información acerca de cómo habilitar itinerarios de cliente, consulte [mediante un componente de canalización para leer un itinerario](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md).  
  
## <a name="centralized-esb-policy-management"></a>Administración de directivas ESB centralizada  
 Hay posible seguridad y problemas de sincronización inherente con lo que permite un cliente enviar mensajes con itinerarios conectados, por lo que el procedimiento recomendado consiste en administrar itinerarios de ESB en un repositorio central que se implementa como una base de datos SQL e incluido en [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] para este propósito. Mediante la implementación de itinerarios a una ubicación central, pueden administrarse fácilmente directivas itinerarios de ESB y modificar sin necesidad de implementar cambios importantes, y la organización puede controlar el procesamiento de mensajes sin exponer potencialmente información confidencial al cliente.  
  
 Se proporcionan los componentes de canalización especializadas para determinar el itinerario ESB adecuado para adjuntar a un mensaje entrante. Este enfoque proporciona dos opciones diferentes para el envío de un mensaje para el enrutamiento de itinerario:  
  
-   Con la primera opción, la aplicación cliente todavía puede indicar un itinerario ESB distinto al proporcionar información de referencia itinerarios de ESB en el encabezado SOAP junto con el mensaje de solicitud, en lugar de enviar un itinerario completo. Esta información incluye el nombre de itinerarios de ESB y versión opcional. En este escenario, los clientes todavía pueden especificar cómo se puede enrutar el mensaje, pero no hay ningún riesgo de comprometer la seguridad o de errores de sincronización de la directiva mediante la exposición de contenido de la itinerario ESB para las aplicaciones cliente.  
  
-   La segunda opción consiste en configurar el ESB rampa para determinar automáticamente el itinerario ESB adecuado, basándose en el contenido o el contexto del mensaje, sin requerir ninguna información de encabezado desde el cliente enviando. Este escenario permite a la organización controlar el flujo de un mensaje enviado y elimina la necesidad de tener en cuenta cómo se está enrutando el mensaje al cliente.