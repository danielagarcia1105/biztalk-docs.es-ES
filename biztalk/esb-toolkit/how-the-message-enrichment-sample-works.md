---
title: "Cómo funciona el ejemplo de enriquecimiento de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1188c1c9-b133-4438-b41c-ea6cffcf40fd
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ef516b992acbcee2936edb6341cbf1434ba4c79
ms.sourcegitcommit: 7497f6f23d7aadfa8535d0530493f8b4a2a50a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2017
---
# <a name="how-the-message-enrichment-sample-works"></a>Cómo funciona el ejemplo de enriquecimiento de mensajes
 El ejemplo Message Enrichment muestra que es posible encapsular un patrón de integración como un servicio genérico reutilizable. En este caso, el ejemplo implementa el modelo de contenido Enricher. El modelo de contenido Enricher normalmente implica el uso de una transformación para preparar un mensaje para su transmisión a un servicio externo con el fin de obtener información de búsqueda y, a continuación, otra transformación para incorporar la respuesta a un mensaje nuevo que también contiene los datos de la mensaje original. Para implementar el patrón de forma genérica, el ejemplo Message Enrichment proporciona un servicio de itinerarios basado en la orquestación que puede usar a hasta dos resoluciones para configurar el enriquecimiento de un mensaje con información de un origen externo.
  
 La primera resolución debe devolver información de enrutamiento; También puede devolver transformar la información junto a él. Si se especifica, la transformación se aplica al mensaje entrante antes de que se enrutan a la ubicación especificada por la resolución. En el itinerario de ejemplo proporcionado, el proveedor del adaptador de WCF-Custom se usa para ejecutar un procedimiento almacenado SQL dentro de la base de datos de GlobalBankESB denominado GetOrderDetails y devolver el resultado.  
  
 Si lo desea, puede incluirse un solucionador de segundo. Si se proporciona, la segunda resolución debe incluir información de transformación. Esta transformación se proporcionará el mensaje original y el resultado, devuelto por el origen de datos se puso en contacto con, como entrada. En el itinerario de ejemplo, un mapa que se hace referencia que utiliza una functoid de bucle de tabla para extraer información del mensaje original y el resultado del procedimiento almacenado e incluir dentro del mensaje InventoryOrder resultante.
