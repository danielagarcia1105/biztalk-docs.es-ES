---
title: Agregaciones programadas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- scheduling, aggregations [BAM]
- aggregations [BAM], scheduling
ms.assetid: 4e2da2eb-b1fc-4b27-98d6-564e6df719e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04aaf0a3eefb018dbe23f3e05e7e684b595820d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998479"
---
# <a name="scheduled-aggregations"></a>Agregaciones programadas
BAM basa las agregaciones programadas en cubos OLAP generados dinámicamente y paquetes de Servicios de transformación de datos (DTS). Los datos de las agregaciones programadas representan una instantánea de sus actividades de negocio en el momento de iniciar su paquete DTS. Para lograr esto, el primer paso del paquete DTS para el análisis es una llamada al procedimiento almacenado **bam_Metadata_BeginAnalysis** que recuperará una instantánea que consta de:  
  
- Una copia instantánea de todas las instancias de actividad en ejecución.  
  
- Una vista que representa una ventana incremental de las instancias de actividad completadas desde el momento en que ejecutó el paquete DTS por última vez hasta el momento de la instantánea.  
  
  BAM la archiva mediante un bloqueo exclusivo en el almacenamiento de la actividad durante poco tiempo, lo que impide que se escriba cualquier dato a la misma vez. Una vez que BAM ha realizado la instantánea, puede que el paquete DTS tarde en ejecutarse, pero BAM omitirá cualquier dato nuevo que se reciba durante el procesamiento. En la siguiente ilustración se muestra esta actividad:  
  
  ![](../core/media/ebiz-prog-bam-data-maint-fig9.gif "ebiz_prog_bam_data_maint_fig9")  
  Agregaciones programadas de BAM  
  
  En la ilustración, BAM transporta datos sobre las instancias de actividad completadas al cubo OLAP de instancias completas. BAM procesa este cubo de forma incremental.  
  
  A la misma vez, BAM transporta los datos sobre las actividades que todavía están en ejecución al cubo de instancias activas, que procesará por completo el paquete DTS. Se puede aceptar porque BAM asume que solo un número relativamente pequeño de actividades están en ejecución en un momento en concreto.  
  
  Los datos de las agregaciones programadas están disponibles en el cubo virtual que oculta la diferencia entre las actividades actuales y completas. Para obtener más información, consulte [consultar datos agregados programados](../core/querying-scheduled-aggregated-data.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es una agregación?](../core/what-is-an-aggregation.md)