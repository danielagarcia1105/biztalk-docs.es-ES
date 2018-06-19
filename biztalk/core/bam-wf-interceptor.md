---
title: Interceptor de WF de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e459084-cb72-4a75-9f5f-f1fd5fd80d17
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de770da5ee0f5d3270b0ee649b6bda61dc6d156e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231372"
---
# <a name="bam-wf-interceptor"></a>Interceptor de WF de BAM
El interceptor de WF de BAM proporciona compatibilidad completa para los datos de seguimiento en su aplicación WF.  
  
 Puede utilizar el interceptor de WF de BAM base para:  
  
-   Enviar de forma transparente datos de aplicaciones de flujo de trabajo a BAM sin tener que volver a compilar su aplicación WF.  
  
-   Dirigir actividades específicas dentro de un flujo de trabajo con el fin de enviar de forma selectiva datos de aplicaciones de flujo de trabajo a BAM.  
  
-   Cumplir con la semántica de transacciones del flujo de trabajo. Los datos se enviarán a BAM sólo si se confirma la transacción a la que pertenecen.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo configurar una aplicación de Workflow Foundation de intercepción](../core/how-to-configure-a-workflow-foundation-application-for-interception.md)  
  
-   [Esquema de Windows Workflow Foundation](../core/windows-workflow-foundation-schema.md)  
  
-   [Patrones de filtro de evento comunes](../core/common-event-filter-patterns.md)  
  
-   [Operaciones de Windows Workflow Foundation](../core/operations-in-windows-workflow-foundation.md)