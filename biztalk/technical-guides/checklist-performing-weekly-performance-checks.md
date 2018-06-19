---
title: 'Lista de comprobación: Realización de comprobaciones de rendimiento semanal | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c36fe78d-1be8-49f2-97ce-b6d0cadffab8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7898702e42253ab1155b0a6e32af3008800db1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300300"
---
# <a name="checklist-performing-weekly-performance-checks"></a>Lista de comprobación: Realización de comprobaciones de rendimiento semanal
Este tema enumeran las prácticas recomendadas que debería seguir semanalmente al evitar el rendimiento emite con un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Establezca el crecimiento automático de base de datos en un número fijo|-Crecimiento automático base de datos debe establecerse en un número fijo de megabytes en lugar de un porcentaje, especialmente para las bases de datos de cuadro de mensaje y seguimiento (DTA). En función de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación y el rendimiento, el cuadro de mensajes y las bases de datos de seguimiento pueden ser bastante grandes. Si el crecimiento automático está establecido en un porcentaje, a continuación, el crecimiento automático puede ser sustancial así.<br />-Si el sistema es nuevo y los tamaños estáticos no se han establecido definitivamente, configurar archivos con la opción de habilitar crecimiento automático y especificar el crecimiento del archivo en Megabytes. El incremento de crecimiento por lo general debe ser no superior a 100 MB (para archivos de gran tamaño), 10 MB (para archivos de tamaño medio) o 1 MB (para archivos pequeños). Consulte la **Apéndice B – recomendado de configuración de base de datos de BizTalk Server** sección de la [notas del producto BizTalk Server Database Optimization](http://go.microsoft.com/fwlink/p/?LinkID=153594) (http://go.microsoft.com/fwlink/p/? LinkID = 153594) para una tabla con el tamaño de archivo sugerido para cada uno de los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.|  
|Limitar los eventos que desea supervisar con SQL Server Profiler|Usar a SQL Server Profiler para supervisar sólo los eventos en el que esté interesado. Si seguimientos son demasiado grandes, puede filtrar según la información que desee, por lo que se recopila sólo un subconjunto de los datos del evento. Si se supervisan demasiados eventos, aumentará la sobrecarga del servidor y el proceso de supervisión, y podría hacer que el archivo o la tabla de seguimiento crezcan demasiado, especialmente cuando el proceso de supervisión se realiza durante un período prolongado de tiempo.|  
|Configurar el procesamiento por lotes de mensajes para aumentar el rendimiento de adaptador|-Minimizar el número de transacciones realizadas por un adaptador mediante la combinación de más de una operación en un único lote.<br />-Limitar el tamaño del lote en función del número total de bytes en el lote, además de recuento de mensajes. Para obtener más información acerca de cómo limitar el tamaño del lote, consulte [configuración de procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md).|  
|Ajustar el umbral de mensajes de gran tamaño|Para mejorar el rendimiento, aumentar el umbral de mensajes de gran tamaño, lo que reduce el número de mensajes de gran tamaño que se almacenan en búfer en el disco durante la asignación.|  
|Investigar fugas de memoria y excepciones de memoria insuficiente en el proceso de BizTalk Server|Pérdidas de memoria en procesos de BizTalk pueden deberse a diversos motivos. Consulte 918643 de artículo de Microsoft Knowledge Base, [cómo solucionar problemas de pérdidas de memoria o una excepción de memoria insuficiente en el proceso de BizTalk Server](http://go.microsoft.com/fwlink/p/?LinkId=157212) (http://go.microsoft.com/fwlink/p/? LinkId = 157212) para obtener información acerca de los escenarios en los que puede producirse una pérdida de memoria y cómo corregirlo.|  
  
## <a name="see-also"></a>Vea también  
 [Listas de comprobación rutinaria del rendimiento](../technical-guides/routine-performance-checklists.md)   
 [Lista de comprobación: Realización de comprobaciones de rendimiento mensual](../technical-guides/checklist-performing-monthly-performance-checks.md)