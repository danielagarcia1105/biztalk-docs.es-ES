---
title: 'Resultados de pruebas: Indicadores clave de rendimiento de memoria | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 224c40e5-08a7-4d30-b03a-4b6add5cde1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4edf88023ee9e30e7fd0c808346b6231112f8ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301876"
---
# <a name="test-results-memory-key-performance-indicators"></a>Resultados de pruebas: Indicadores clave de rendimiento de memoria
En este tema se resume observado durante los escenarios de prueba la indicadores de rendimiento de clave de memoria (KPI). Estas pruebas evalúan la memoria disponible según lo medido por la **\Memory\Available Mbytes** contador del monitor de rendimiento.  
  
## <a name="summary-of-memory-key-performance-indicators"></a>Resumen de indicadores clave de rendimiento de memoria  
 **Comparación de indicadores de clave de rendimiento de memoria:** Total de memoria disponible para SQL Server y BizTalk Server según lo medido por la **\Memory\Available Mbytes** contador del monitor de rendimiento era bastante coherente en todas las probar los escenarios. La diferencia en el promedio de memoria disponible para los equipos físicos de BizTalk Server y el promedio de memoria disponible para los equipos de BizTalk Server que se ejecutan en máquinas virtuales es debido al hecho de que dos equipos físicos con BizTalk Server se utilizaron para probar mientras los tres equipos de BizTalk Server que se ejecutan en máquinas virtuales se utilizaron para probar.  
  
 El siguiente gráfico muestra el rendimiento de memoria en las diferentes plataformas de prueba:  
  
 ![Indicadores clave de rendimiento de memoria](../technical-guides/media/memorykpi.gif "MemoryKPI")  
  
 La siguiente tabla muestra el rendimiento relativo de recopilados de KPI para cada configuración. Cada conjunto de resultados se calcula como un porcentaje de la configuración de línea de base KPI  
  
|KPI|Virtual de BizTalk o física SQL|Virtual SQL de BizTalk y virtuales en Hosts independientes|Virtual de BizTalk/Virtual de SQL en el entorno consolidado|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|SQL Server disponible memoria (MB) por servidor|100.1%|97.1%|103.2%|  
|Memoria disponible de BizTalk total (MB)|88.3%|95.9%|96%|  
|Promedio por servidor / memoria disponible de BizTalk (MB)|58.9%|63.9%|64%|  
  
 Para obtener más información acerca de cómo evaluar el rendimiento de memoria, consulte el **medir el rendimiento de memoria** sección del tema [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).