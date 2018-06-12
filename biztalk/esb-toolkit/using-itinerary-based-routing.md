---
title: Mediante el enrutamiento basado en itinerario | Documentos de Microsoft
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
ms.openlocfilehash: 9a0e0dad0f49e07c0941614dd0130d0e77c459ab
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848988"
---
# <a name="using-itinerary-based-routing"></a>Usar el enrutamiento basado en itinerario
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona el enrutamiento de mensajes basado en itinerario al implementar el patrón de lista de distribución para habilitar escenarios cuando la secuencia de procesamiento de los pasos para un mensaje determinado no se conoce en tiempo de diseño y puede variar para cada mensaje. La implementación de este patrón utiliza una lista de distribución para representar una colección de estos pasos en formato XML y determina los pasos que se necesitan para que se produzca durante el tiempo de ejecución. Un estado de la lista de distribución, con frecuencia se denomina "itinerario ESB", es un conjunto ordenado de instrucciones declarativas que definen los pasos que se deben ejecutar para un mensaje, tal y como está siendo procesado por [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes y el tiempo de ejecución de BizTalk Server. Una instrucción de procesamiento determinado especificada en itinerario ESB está asociada con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componente, que también se conoce como el "servicio itinerario ESB". El propósito del servicio itinerario de ESB es que se va a ejecutar las instrucciones de procesamiento como actualizar el estado de la lista de distribución para indicar la próxima pendiente de instrucción.  
  
 Esta sección describen las características de procesamiento basado en itinerario de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. Incluye los temas siguientes:  
  
-   [Administración de itinerarios de ESB](../esb-toolkit/esb-itinerary-management.md)  
  
-   [Con rampas y sin rampas](../esb-toolkit/on-ramps-and-off-ramps.md)  
  
-   [Elegir entre mensajería y servicios de itinerario de orquestación](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  
  
-   [Uso de un componente de canalización para seleccionar un itinerario existente](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  
  
-   [Uso de un componente de canalización para leer un itinerario](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  
  
-   [Uso de un componente de canalización para almacenar en caché un itinerario para petición-respuesta](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  
  
-   [Crear suscriptores de itinerarios](../esb-toolkit/creating-itinerary-subscribers.md)  
  
-   [Ejecución de un servicio de itinerarios](../esb-toolkit/executing-an-itinerary-service.md)  
  
-   HYPERLINK "http://msdn.microsoft.com/library/ee236752(BTS.10).aspx" [artefactos de enrutamientos basados en itinerario](../esb-toolkit/itinerary-based-routing-artifacts.md)