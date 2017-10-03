---
title: Contadores de rendimiento del Interceptor de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9b64ae1-4d94-4c3c-add1-fa020713be5c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 989316edff34463905c7547db815b3daaf4d4a46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-interceptor-performance-counters"></a>Contadores de rendimiento del interceptor de BAM
Los contadores de rendimiento permiten controlar aspectos específicos del trabajo llevado a cabo por los interceptores de BAM. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 La tabla siguiente enumera los contadores de rendimiento disponibles para los interceptores de BAM. La categoría de los contadores de rendimiento es “Interceptor de BAM”.  
  
|Contador|Description|  
|-------------|-----------------|  
|Promedio de Promedio de eventos de BAM con error por vaciado|Promedio de eventos BAM con errores que se han producido durante un vaciado de datos en la base de datos de importación principal.|  
|Promedio de eventos BAM correctos por vaciado|Promedio de eventos BAM correctos que se han producido durante un vaciado de datos en la base de datos de importación principal. Es posible que los eventos no se almacenen en la base de datos si se revierte la transacción.|  
|Promedio de Segundos de extracción por evento de BAM|Promedio de tiempo empleado en la extracción de eventos BAM.|  
|Promedio de Segundos de vaciado por evento de BAM|Promedio de tiempo empleado en el vaciado de eventos BAM.|  
|Total de eventos BAM con errores durante el vaciado|Número total de eventos BAM con errores que se han producido durante el vaciado de los datos.|  
|Total de eventos BAM correctos durante el vaciado|Número total de eventos BAM correctos que se han vaciado en la base de datos de importación principal. Es posible que los eventos no se almacenen en la base de datos si se revierte la transacción.|  
  
## <a name="see-also"></a>Vea también  
 [Contadores de rendimiento de BAM](../core/bam-performance-counters.md)