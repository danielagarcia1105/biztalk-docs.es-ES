---
title: Información general del enrutamiento y resolución dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab7ea6f4ddd37be8d8c2c6629d2449c2d9df5f81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018770"
---
# <a name="dynamic-resolution-and-routing-overview"></a>Información general del enrutamiento y resolución dinámica
Las clases de solucionador de ESB admiten la resolución de tiempo de ejecución de las acciones siguientes:  

- Puntos de conexión de entrega de mensajes  

- Mapas para transformación  

- Configuración de extremo  

- Metadatos del servicio personalizado  

- Itinerarios del lado servidor  

  El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] utiliza cadenas de conexión de resolución para tratar de resolución de asignaciones y los puntos de conexión cuando llegan los mensajes. Estas cadenas de conexiones puedan existir en el encabezado SOAP itinerario de mensajes cuando llegan, o se puede establecer en una canalización personalizada mediante uno de los siguientes componentes de canalización: Selector de itinerarios de ESB, distribuidor de ESB o desensamblar distribuidor de ESB. La resolución tiene lugar más adelante en el ciclo de vida de procesamiento mediante las funciones de resolución "just-in-time" (JIT) de los componentes de marco de proveedores de adaptador y resolución de ESB.  

  Por ejemplo, si el agente de la transformación dinámica recibe un mensaje que debe asignar, pero aún no se ha determinado el nombre del mapa, se intentará utilizar al Solucionador asociado para realizar la resolución. Si se produce un error en la resolución JIT, que se clasifica como un error, el sistema genera un mensaje de excepción.  

  El marco de proveedores de adaptador y la resolución pueden consultar los siguientes almacenes de datos o los mecanismos de resolución:  

- Mapas codificados de forma rígida o puntos de conexión, en el que no producen case resolución dinámica  

- Una directiva del motor de reglas de negocios (BRE)  

- Un ensamblado personalizado que implementa el **IResolveProvider** interfaz  

- Una consulta XPath en el mensaje  

- Una búsqueda Universal Description, Discovery and Integration (UDDI)
