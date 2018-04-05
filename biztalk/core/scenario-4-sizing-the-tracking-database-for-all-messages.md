---
title: 'Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: db1126c7-0b86-4635-bfdc-3b69a82cc64b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 327953843b2d9b70f500796f43302320924a330c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a>Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes
Si tuviera los tres escenarios de mensajes presentes en una implementación de Microsoft® BizTalk Server® 2004, tendría que sumar los resultados de los tres escenarios para determinar el tamaño de la base de datos de seguimiento de BizTalk.  
  
 En los ejemplos anteriores:  
  
|Escenario|Espacio requerido por año en GB|  
|--------------|-------------------------------------|  
|Mensajes sencillos|4.78|  
|Mensajes de orquestaciones|7.18|  
|Mensajes de orquestaciones enviados a listas de distribución|10.8|  
|**Total**|22.04|  
  
 Además, si activamos el seguimiento del cuerpo de los mensajes para los tres escenarios, tendríamos los siguientes resultados:  
  
|Escenario|Espacio requerido por año en GB|  
|--------------|-------------------------------------|  
|Mensajes sencillos|50.1|  
|Mensajes de orquestaciones|50.1|  
|Mensajes de orquestaciones enviados a listas de distribución|83.45|  
|**Total**|183.65|  
  
 Esto supondría un aumento total de la base de datos de seguimiento de BizTalk de 205,69 GB al año. Esta cifra no incluye ninguna contingencia. Si decidiera agregar una contingencia del 10% a este total, como se recomienda, debería planear un crecimiento de la base de datos de seguimiento de BizTalk de 227,94 GB por año. Además, debe considerar la sobrecarga producida por los índices de SQL, almacenamiento, etcetera. Se debe basar el factor de multiplicación después de ejecutar los escenarios de prueba en pruebas si es posible.  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a>Otros factores que inciden en el tamaño de la base de datos de seguimiento de BizTalk  
 Hay otros elementos, como las formas utilizadas en una orquestación, que también afectan al tamaño de la base de datos de seguimiento de BizTalk.  
  
 Si la opción del depurador de orquestaciones está activada, que es la configuración predeterminada, el estado de cada forma de la orquestación se guarda en la base de datos de seguimiento de BizTalk.  
  
 La fórmula para determinar el tamaño necesario para mantener un seguimiento del estado de las formas es:  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 Por ejemplo, en la siguiente ilustración se utiliza la siguiente fórmula para determinar el tamaño del seguimiento de BizTalk:  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 ![Ejemplo de orquestación](../core/media/sample-orchestration.gif "Sample_orchestration")  
  
 Si asumimos que esta orquestación procesa 3,5 millones de mensajes, el espacio adicional necesario para mantener un seguimiento de esta orquestación sería:  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 Deberá tener en cuenta cada orquestación que tenga "activado" el depurador de orquestaciones para obtener un tamaño aproximado de la base de datos de seguimiento de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md)   
 [Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)