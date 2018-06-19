---
title: Las actividades en bucle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], looping activities
- activities [BAM], orchestrations
- orchestrations, looping
- orchestrations, activities
ms.assetid: fb40fdd0-ac8f-486a-b3d0-9d2200a87cda
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f66382a27ed564da0c41257e8abe95accba5e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262084"
---
# <a name="looping-activities"></a>Actividades en bucle
Las actividades en bucle son acciones asociadas en bucle dentro de una orquestación. Existe la posibilidad de capturar los eventos de acciones asociadas en bucle dentro de una orquestación. Para hacerlo, se deberá crear otra actividad y asignar todos los hitos de actividad y datos nuevos del bucle. Este procedimiento es necesario porque el procesamiento de datos del bucle tendrá lugar más de una vez por cada ejecución programada. La siguiente ilustración muestra un ejemplo de esta situación.  
  
 ![](../core/media/handlingloops2.gif "handlingloops2")  
  
 Como se muestra en la ilustración, si tiene un pedido de compra con varios elementos de línea que se procesan en un bucle, preguntas como "qué pedidos tienen precios de $100?" son ambiguas. Las preguntas no ambiguas son:  
  
-   ¿Qué pedidos tienen elementos de línea con un precio de $100?  
  
-   ¿Qué pedidos tienen precios Total/Mín./Máx. de $100?  
  
 La creación de preguntas no ambiguas pasa por concebir los elementos de línea de pedido como elementos independientes del pedido. En el Editor de perfiles de seguimiento, la actividad raíz (por ejemplo, un pedido de compra) se asigna a todas las acciones externas al bucle. La actividad secundaria (por ejemplo, el elemento de línea) se asigna a las acciones dentro del bucle.  
  
 Deberá utilizar un elemento de carga como ActivityID para la actividad raíz. Tenga este elemento de carga disponible en algunos de los mensajes internos del bucle. Asigne la actividad al nodo Relación que se muestra bajo la actividad secundaria, y asígnele el mismo nombre que la actividad raíz.  
  
## <a name="see-also"></a>Vea también  
 [Implementar actividades BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md)