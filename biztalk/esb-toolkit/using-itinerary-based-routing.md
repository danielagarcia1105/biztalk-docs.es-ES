---
title: Uso del enrutamiento basado en itinerarios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d5b5d13-cbf2-4f3c-8a1a-3bb852f048a0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4adcb32367a42403e769111f7b3d3d343c604671
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978693"
---
# <a name="using-itinerary-based-routing"></a>Uso del enrutamiento basado en itinerarios
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona enrutamiento de mensajes basado en itinerarios al implementar el patrón de lista de distribución para habilitar escenarios cuando los pasos de la secuencia de procesamiento para un mensaje determinado se desconoce en tiempo de diseño y puede variar para cada mensaje. La implementación de este patrón usa una lista de distribución para representar una colección de estos pasos en formato XML y determina los pasos que deben producirse durante el tiempo de ejecución. Un estado de la lista de distribución, con frecuencia se denomina "itinerarios ESB", es un conjunto ordenado de instrucciones declarativas que definen los pasos que se deben ejecutar para un mensaje mientras se procesa por [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes y el tiempo de ejecución de BizTalk Server. Una instrucción de procesamiento determinado especificada en itinerarios ESB está asociada con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componente, que también se conoce como el "servicio itinerario ESB". El propósito del servicio de itinerarios de ESB es ejecutar las instrucciones de procesamiento y para actualizar el estado de la lista de distribución para indicar el siguiente pendiente de la instrucción.  

 En esta sección se describe las características de procesamiento basado en itinerarios de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. Incluye los temas siguientes:  

- [Administración de itinerarios de ESB](../esb-toolkit/esb-itinerary-management.md)  

- [Con rampas y sin rampas](../esb-toolkit/on-ramps-and-off-ramps.md)  

- [Elegir entre mensajería y servicios de itinerario de orquestación](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  

- [Uso de un componente de canalización para seleccionar un itinerario existente](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  

- [Uso de un componente de canalización para leer un itinerario](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  

- [Uso de un componente de canalización para almacenar en caché un itinerario para petición-respuesta](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  

- [Crear suscriptores de itinerarios](../esb-toolkit/creating-itinerary-subscribers.md)  

- [Ejecución de un servicio de itinerarios](../esb-toolkit/executing-an-itinerary-service.md)  

- HYPERLINK "<http://msdn.microsoft.com/library/ee236752(BTS.10).aspx>" [artefactos de enrutamiento basado en itinerarios](../esb-toolkit/itinerary-based-routing-artifacts.md)
