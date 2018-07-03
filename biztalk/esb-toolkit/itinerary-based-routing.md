---
title: Enrutamiento basado en itinerarios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28028721-798c-4302-a532-d863ed8ea88b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13be8ab9078a2c12e110c5d80b65b2930d805952
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970885"
---
# <a name="itinerary-based-routing"></a>Enrutamiento basado en itinerarios
Una de las características principales de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] es el aprovisionamiento del enrutamiento basado en itinerarios que simplifica el desarrollo de aplicaciones de mensajería de nivel empresarial y reduce los costos de mantenimiento de un gran número de estático puertos de envío y ubicaciones de recepción.  
  
 Un itinerario consta de la lista de servicios que se va a ejecutar (que puede contener servicios personalizados, transformación y enrutamiento) y la información de configuración necesarios para resolver los metadatos necesarios para ejecutar cada uno de estos servicios. Por ejemplo, una fase del itinerario puede ser un servicio de enrutamiento; las instrucciones de resolución asociadas a este servicio pueden indicar al servicio para realizar una búsqueda Universal Description, Discovery y Integration (UDDI) o motor de reglas de negocios (BRE) para obtener información sobre un punto de conexión de destino específico al que enrutará el mensaje.  
  
 Itinerarios pueden asociarse a un mensaje entrante de las maneras siguientes:  
  
- El mensaje enviado por un cliente no contiene los datos relacionados con el itinerario. La canalización de recepción se resuelve, recupera y adjunta el itinerario adecuado según el contexto o el contenido del mensaje.  
  
- El mensaje enviado por un cliente puede contener un encabezado SOAP que define los datos de itinerario de referencia, que contiene el nombre de itinerarios y versión, así como un identificador único para el seguimiento de la supervisión de la actividad económica (BAM). La canalización de recepción evalúa esta información y recupera el itinerario adecuado de la base de datos ESBItineraryDb.  
  
- El mensaje enviado por un cliente puede tener un encabezado SOAP itinerario, que contiene todo el contenido de los itinerarios. Este diseño no se recomienda y se debe usar solo para fines de prueba.  
  
  Después de un itinerario se resuelve para un mensaje entrante, la canalización de recepción promueve los datos del itinerario para el contexto del mensaje, por lo que las propiedades disponibles para tener acceso a cualquier componente de Microsoft BizTalk Server que se suscribe a este mensaje. Componentes de BizTalk Server pueden obtener los detalles del paso actual de itinerarios, completar el procesamiento necesario o pase el itinerario para el paso siguiente. Esto hace que el servicio siguiente en el itinerario para procesar el mensaje, según la publicación-suscribirse funcionalidad de BizTalk Server.  
  
  Para obtener información sobre el mecanismo de resolución dinámica ESB, transformaciones, procesamiento de itinerarios y creación de mensajes, vea [escenarios clave y las tareas de desarrollo](../esb-toolkit/key-scenarios-and-development-tasks.md).