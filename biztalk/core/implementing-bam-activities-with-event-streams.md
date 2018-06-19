---
title: Implementar actividades BAM con secuencias de eventos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], about activities
- activities [BAM]
- BAM, activities
ms.assetid: 94e6d9dd-93c3-4ab0-9de7-a860dd1e3406
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63594b956affc0f5b94f26ccdcb10d904ef171cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257348"
---
# <a name="implementing-bam-activities-with-event-streams"></a>Implementar actividades de BAM con secuencias de eventos
Una actividad de BAM representa una unidad de trabajo en el negocio, como un pedido o una aplicación de préstamo. La actividad muestra el historial (hitos) y los datos sobre esta unidad de trabajo a los usuarios finales empresariales o al trabajador de la información. Por ejemplo, una actividad de aplicaciones de préstamo podría contener hitos como "Préstamo aprobado" y datos como" Nombre del candidato" e "Importe del préstamo". Las actividades de BAM a menudo se asignan directamente a un proceso empresarial, aunque como una abstracción de alto nivel, una actividad es independiente de la implementación actual de la infraestructura de TI.  
  
 Su trabajo como programador consiste en mantener esta abstracción exponiendo los hitos relevantes y los datos de la implementación en el contexto de una actividad específica. Para obtener un ejemplo de código que muestra el uso de una actividad, consulte [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Por qué escribir código para BAM?](../core/why-write-code-for-bam.md)  
  
-   [Conceptos de BAM para el desarrollador](../core/bam-concepts-for-the-developer.md)  
  
-   [Información general sobre el proceso de desarrollo de BAM](../core/overview-of-the-bam-development-process.md)  
  
-   [Clases EventStream](../core/eventstream-classes.md)  
  
-   [Uso de una actividad](../core/using-an-activity.md)  
  
-   [Relaciones de actividad](../core/activity-relationships.md)  
  
-   [Continuación de actividad](../core/activity-continuation.md)  
  
-   [Las actividades en bucle](../core/looping-activities.md)  
  
-   [Instrumentar una solución: uso de la API de paso a paso](../core/instrumenting-a-solution-step-by-step-api-usage.md)