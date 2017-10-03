---
title: Enrutamiento basado en itinerario | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28028721-798c-4302-a532-d863ed8ea88b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fbfe8877202a2f691bd30fd2b56fc3032240ee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="itinerary-based-routing"></a>Enrutamiento basado en itinerario
Una de las características principales de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] es la disposición de enrutamiento basado en itinerario que simplifica el desarrollo de aplicaciones de mensajería de nivel empresarial y reduce los costos de mantenimiento de un gran número de estático puertos de envío y ubicaciones de recepción.  
  
 Un itinerario consta de la lista de servicios que se va a ejecutar (que puede contener enrutamiento, transformación y servicios personalizados) y la información de configuración necesaria para resolver los metadatos necesarios para ejecutar cada uno de estos servicios. Por ejemplo, una de las fases de la itinerario puede ser un servicio de enrutamiento; las instrucciones de resolución asociadas a este servicio pueden indicar al servicio para realizar una búsqueda de Universal Description, Discovery y Integration (UDDI) o motor de reglas de negocios (BRE) para obtener información sobre un punto de conexión de destino específico al que enrutará el mensaje.  
  
 Itinerarios pueden adjuntarse a un mensaje entrante de las maneras siguientes:  
  
-   El mensaje enviado por un cliente no contiene los datos relacionados con el itinerario. La canalización de recepción resuelve, se recupera y adjunta el itinerario adecuado según el contenido del mensaje o contexto.  
  
-   El mensaje enviado por un cliente puede contener un encabezado SOAP que define los datos de referencia itinerarios, que contiene el nombre itinerario y versión, así como un identificador único para el seguimiento de supervisión de la actividad económica (BAM). La canalización de recepción evalúa esta información y recupera el itinerario adecuado de la base de datos de ESBItineraryDb.  
  
-   El mensaje enviado por un cliente puede tener un encabezado SOAP itinerario, que contiene todo el contenido de la itinerario. Este diseño no se recomienda y debe utilizarse solo con fines de prueba.  
  
 Después de un itinerario se resuelve para un mensaje entrante, la canalización de recepción promociona los datos de itinerario para el contexto del mensaje, por lo que las propiedades disponibles para tener acceso a cualquier componente de Microsoft BizTalk Server que se suscribe a este mensaje. Componentes de BizTalk Server pueden obtener detalles del paso actual itinerario, complete el procesamiento necesario o adelantar el itinerario hasta el paso siguiente. Esto hace que el servicio siguiente en el itinerario para procesar el mensaje, según la publicación-suscribirse funcionalidad de BizTalk Server.  
  
 Para obtener información sobre el mecanismo de resolución dinámica ESB, transformaciones, procesamiento itinerario y creación de mensajes, vea [escenarios clave y las tareas de desarrollo](../esb-toolkit/key-scenarios-and-development-tasks.md).