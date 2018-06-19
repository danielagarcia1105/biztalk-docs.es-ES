---
title: Las agregaciones en el Portal de BAM página | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], alerts
- aggregations [BAM], viewing results
- alerts, aggregations
- Aggregations page [BAM portal]
- BAM portal, aggregations
ms.assetid: 6bc1a6f2-9e9a-4db6-aaa1-188ed2f2641f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a61df22bf5d07bd1b4d955f2baf884459de52998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230068"
---
# <a name="aggregations-on-the-bam-portal-page"></a>Agregaciones en la página del portal de BAM
Los usuarios empresariales finales y los analistas empresariales utilizan la página del portal de BAM cuando necesitan presentar datos agregados, que son resúmenes precalculados de conjuntos de datos que contienen características representativas de ese conjunto de datos. La página Agregaciones del portal de BAM le permite mostrar datos agregados en forma de diagrama gráfico e informe de tabla dinámica existente.  
  
## <a name="the-aggregations-page"></a>Agregaciones (página)  
 La página Agregaciones muestra los resultados de una actividad que expresa de forma conjunta el estado del proceso o del negocio en general. Por ejemplo, puede que un usuario desee ver un gráfico circular básico que muestre un desglose de 1.000 facturas recibidas en lo que respecta a la fase de procesamiento que se ha alcanzado con cada factura (400 en “evaluación”, 400 rechazadas, 100 pagadas y 100 en “asignación de recursos”).  
  
### <a name="creating-alerts-for-aggregations"></a>Crear alertas para agregaciones  
 Puede crear agregaciones como base para crear una alerta (“Notifíqueme si alguna vez hay más de 500 facturas en la fase de "evaluación" del proceso”). Para ello, haga clic en cualquier celda de tabla dinámica y seleccione **establecer alerta**, o haga clic en una celda y haga clic en el **establecer alerta** situado a la derecha del informe de tabla dinámica. Para obtener más información acerca de cómo crear una alerta, consulte [cómo establecer una alerta](../core/how-to-set-an-alert.md).  
  
### <a name="viewing-individual-results-of-aggregations"></a>Ver resultados individuales de agregaciones  
 También puede seleccionar cualquier cantidad agregada (por ejemplo, 400 facturas que aún estén en “evaluación”) y ver los resultados individuales para la agregación. Acceso a los resultados individuales haciendo clic en cualquier celda de tabla dinámica y seleccione **mostrar resultados**. Como resultado, se le envía a la página Búsqueda de actividad económica, donde la propia búsqueda se genera automáticamente y se muestran los resultados (en este ejemplo, un registro para cada una de las 400 facturas).  
  
> [!NOTE]
>  Algunas vistas de BAM no tienen agregaciones asociadas, por lo que puede que no exista información a la que obtener acceso en función de cómo se creó la vista.  
  
## <a name="see-also"></a>Vea también  
 [Portal de BAM](../core/bam-portal.md)   
 [Búsqueda de actividad en el Portal de BAM página](../core/activity-search-on-the-bam-portal-page.md)   
 [Alert Manager en el Portal de BAM de página](../core/alert-manager-on-the-bam-portal-page.md)