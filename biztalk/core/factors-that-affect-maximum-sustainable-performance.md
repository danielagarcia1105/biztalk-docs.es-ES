---
title: "Factores que influyen en el rendimiento máximo sostenible | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST), maintenance
- monitoring, maximum sustainable thoughput (MST)
- maintaining, maximum sustainable thoughput (MST)
- maximum sustainable throughput (MST), monitoring
- maximum sustainable throughput (MST), load patterns
- maximum sustainable throughput (MST), sustainable load test
- sustainable performance
ms.assetid: 99b99655-bc77-425c-a133-204781d7c430
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be96ad552abef66e2a401e334da1c27ee0e08cd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="factors-that-affect-maximum-sustainable-performance"></a>Factores que afectan al rendimiento sostenible máximo
Una amplia gama de factores afecta al rendimiento sostenible máximo entre los que se incluyen los recursos de servidor disponibles, el tipo de características utilizadas en la solución, el tamaño de los mensajes y la carga global de mensajes. Existen otros factores que se deben tener en cuanto aunque no sean tan evidentes. A la hora de estimar el rendimiento sostenible máximo, también deben tenerse en cuenta los siguientes factores:  
  
## <a name="load-patterns"></a>Patrones de carga  
 Los mensajes no suelen fluir en un entorno de producción de BizTalk Server a una velocidad homogénea y predecible. Es más habitual que las necesidades empresariales dicten que BizTalk Server procese los mensajes a una velocidad variable que tenga valores máximos y mínimos. Cuando se producen valores máximos, los requisitos de procesamiento de BizTalk Server pueden pasar de ser mínimos a condiciones de sobrecarga en las que los mensajes se reciben a mayor velocidad que se procesan. En este escenario, los mensajes publicados se acumulan en la base de datos de cuadro de mensajes hasta que BizTalk entregue los mensajes atrasados a los suscriptores adecuados. Siempre y cuando BizTalk Server pueda procesar los mensajes acumulados entre los períodos de carga máxima, esto no supone un problema.  
  
 Debido al patrón variable habitual del flujo de mensajes en un entorno de BizTalk Server, deben ejecutarse los escenarios de prueba durante un período de tiempo ampliado para garantizar que la solución pueda mantener el rendimiento deseado de forma indefinida, recuperándose de todos los períodos de carga máxima.  
  
## <a name="monitoring-and-maintenance-activities"></a>Actividades de supervisión y mantenimiento  
 Durante la duración de una solución de producción, existe un host de actividades de supervisión y mantenimiento que puede afectar al rendimiento de BizTalk y, por lo tanto, debería tenerse en cuenta en cualquier escenario de prueba. Entre estas actividades se incluyen:  
  
-   **Consultas de la consola de administración de BizTalk** estas consultas consumen recursos y afectar al rendimiento global en función del tipo y la frecuencia de la consulta.  
  
-   **Copia de seguridad, archivo y depuración actividades** estas actividades también consumen recursos y deben tenerse en cuenta en cualquier escenario de prueba. Deben realizarse copias de seguridad periódicas de las bases de datos de BizTalk Server y truncarse sus registros de transacción. De no hacerlo, el registro de transacciones podría crecer sin control y consumir todo el espacio en disco disponible para la base de datos de transacciones. Si se utiliza seguimiento, debe depurarse y opcionalmente archivarse periódicamente la base de datos de seguimiento para evitar que crezca demasiado. Para obtener más información acerca del mantenimiento de bases de datos de BizTalk Server, vea [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server-databases.md).  
  
## <a name="see-also"></a>Vea también  
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)