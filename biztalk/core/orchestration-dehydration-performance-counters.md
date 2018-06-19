---
title: Contadores de rendimiento de deshidratación de orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ab92e0e-6a33-4aaa-ab14-0c82322b04d5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e81052f0061ff4ad802a084536c09d48cb6cb55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263788"
---
# <a name="orchestration-dehydration-performance-counters"></a>Contadores de rendimiento de deshidratación de orquestaciones
En la tabla siguiente se incluyen los nombres de los contadores de rendimiento del motor de orquestaciones que son específicos para la supervisión del comportamiento de deshidratación. Use el monitor de rendimiento para observar estos contadores mientras ajusta los parámetros de deshidratación.  
  
|Contador de rendimiento de deshidratación|Description|  
|-------------------------------------|-----------------|  
|Orquestaciones deshidratables|Número de instancias de orquestación que se pueden deshidratar y que están actualmente alojadas por la instancia de host.|  
|Deshidratando orquestaciones|Número de orquestaciones que se están deshidratando.|  
|Ciclo de deshidratación en curso|Indica si es actualmente hay un ciclo de deshidratación en curso.|  
|Ciclos de deshidratación|Número de ciclos de deshidratación completados.|  
|Umbral de deshidratación|Número en milisegundos que determina la forma agresiva en que se deshidratan orquestaciones. Si el motor de orquestaciones predice que una instancia será deshidratable durante un período superior a este umbral, deshidratará la instancia.|  
|Orquestaciones deshidratadas|Número de instancias de orquestación deshidratadas desde que se inició la instancia de host.|  
|Orquestaciones deshidratadas/seg.|Número promedio deshidratado por segundo.|  
|Orquestaciones rehidratadas|Número de instancias de orquestación rehidratadas desde que se inició la instancia de host.|  
|Orquestaciones rehidratadas/seg.|Número promedio rehidratado por segundo|  
|Orquestaciones programadas para deshidratación|Número de orquestaciones deshidratables para las que existe una solicitud de deshidratación pendiente.|