---
title: "Resolución dinámica e Introducción al enrutamiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 341b8389530ac85fdc459816f5691f3b814fbd56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-resolution-and-routing-overview"></a>Resolución dinámica e Introducción al enrutamiento
Las clases de resolución de ESB admiten la resolución de tiempo de ejecución de las acciones siguientes:  
  
-   Puntos de conexión de entrega de mensajes  
  
-   Mapas de transformación  
  
-   Configuración de extremo  
  
-   Metadatos de servicio personalizado  
  
-   Itinerarios de servidor  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] utiliza cadenas de conexión de resolución para tratar de resolución de asignaciones y los puntos de conexión cuando llegan los mensajes. Estas cadenas de conexiones que existan en el encabezado SOAP itinerario de mensajes cuando llegan, o se puede establecer en una canalización personalizada mediante uno de los siguientes componentes de canalización: Selector de itinerario de ESB, ESB distribuidor o distribuidor de ESB desensamblar. Se produce una resolución más adelante en el ciclo de vida de procesamiento mediante las capacidades de resolución de "just-in-time" (JIT) de la resolución de ESB y componentes del marco de proveedores de adaptador.  
  
 Por ejemplo, si el agente de transformación dinámica recibe un mensaje que debe asignar, pero aún no se ha determinado el nombre de asignación, intentará utilizar al Solucionador asociado para realizar la resolución. Si se produce un error en la resolución JIT, que se clasifican como un error, el sistema genera un mensaje de excepción.  
  
 La resolución y el marco de proveedores de adaptador pueden consultar los siguientes almacenes de datos o los mecanismos de resolución:  
  
-   Mapas codificados de forma rígida o puntos de conexión, en el que no producía mayúscula resolución dinámica  
  
-   Una directiva del motor de reglas de negocios (BRE)  
  
-   Un ensamblado personalizado que implementa la **IResolveProvider** (interfaz)  
  
-   Una consulta de XPath en el mensaje  
  
-   Una búsqueda de Universal Description, Discovery e Integration (UDDI)