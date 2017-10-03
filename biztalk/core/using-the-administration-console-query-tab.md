---
title: "Mediante la pestaña de consulta de la consola de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], Query tab
- Query tab [Administration Console]
ms.assetid: 7655f0b6-9217-46c4-88e0-ca2e661ce7a6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20046580913ee8ea3ccb4a742ab693bcaa08d38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-administration-console-query-tab"></a>Usar la ficha Consulta de la consola de administración
Utilice la ficha Consulta de la página Concentrador de grupo de la consola de administración de BizTalk Server para buscar instancias de servicio, suscripciones o mensajes específicos en ejecución o en suspensión. Las consultas realizadas con la consola de administración buscan elementos activos, que se almacenan en la base de datos de cuadro de mensajes. Cada vez que se ejecuta una nueva consulta, aparece una ficha Consulta nueva.  
  
 Para buscar instancias de servicio o mensajes archivados supervisados, use el seguimiento de eventos de mensaje e instancias de servicio. Para obtener más información, consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md).  
  
> [!NOTE]
>  Cuando se ejecuta una consulta de instancias de servicio, el conjunto de resultados que se devuelve mostrará el valor de  **\<nombre no está disponible >** para el **ServiceName** campo de un servicio de instancia si el puerto de envío correspondiente ubicación de recepción, o se ha eliminado la orquestación.  El **ServiceName** campo de una instancia de servicio se rellena mediante una búsqueda en la base de datos de administración de BizTalk para el nombre descriptivo del puerto de envío, ubicación de recepción, u orquestación.  Si el puerto de envío, ubicación de recepción, o se elimina la orquestación, a continuación, se produce un error en la búsqueda para el nombre descriptivo y  **\<nombre no está disponible >** se muestra.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo abrir una consulta guardada](../core/how-to-open-a-saved-query.md)  
  
-   [Cómo buscar todas las instancias de servicio](../core/how-to-search-for-all-service-instances.md)  
  
-   [Búsqueda de instancias de servicio en ejecución](../core/how-to-search-for-running-service-instances.md)  
  
-   [Cómo buscar instancias de servicio suspendidas](../core/how-to-search-for-suspended-service-instances.md)  
  
-   [Cómo buscar mensajes](../core/how-to-search-for-messages.md)  
  
-   [Cómo buscar suscripciones](../core/how-to-search-for-subscriptions.md)  
  
-   [Cómo guardar una consulta](../core/how-to-save-a-query.md)  
  
-   [Búsqueda de eventos de seguimiento de mensajes](../core/how-to-search-for-tracked-message-events.md)  
  
-   [Búsqueda de instancias de servicio controladas](../core/how-to-search-for-tracked-service-instances.md)