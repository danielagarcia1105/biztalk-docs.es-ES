---
title: Consultar datos agregados programados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, scheduled data
- queries [BAM], scheduled data
ms.assetid: fb785ec0-7862-4d83-bb6f-0ebd69a28ce6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aed1d63b1ebd1e54fd229236a94f3ac9a5f6837
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="querying-scheduled-aggregated-data"></a>Consultar datos agregados programados
Los datos de agregación programados están disponibles para consultas mediante cubos OLAP creados de forma dinámica en la base de datos de análisis de BAM.  
  
 El nombre de este cubo coincide con el atributo Nombre del elemento Vista del XML de definición de BAM, que coincide, a su vez, con el nombre de vista especificado en los asistentes de Excel. BAM actualiza este cubo al ejecutar el paquete de servicios de transformación de datos (DTS) BAM_AN_\<*ViewName*\>, donde el \< *ViewName* \> es que el nombre de la vista que se utilizan en los asistentes de Excel describe.  
  
 Es importante tener en cuenta las siguientes condiciones a la hora de consultar datos agregados programados:  
  
-   Éste es un cubo virtual que contiene una instantánea de la empresa en el momento exacto en que se inició la ejecución del paquete DTS. Contiene agregaciones tanto para las actividades completadas como para las que aún están en ejecución. Puede utilizar la dimensión de progreso para filtrar o agrupar las agregaciones según corresponda.  
  
-   Si está interesado en las actividades actuales (por ejemplo, si se completan rápidamente) puede consultar el cubo real correspondiente \< *ViewName*\>#Completed.  
  
-   Si tiene también agregaciones en tiempo real, programe el paquete DTS para actualizar el cubo con más frecuencia que la ventana en línea definida para las agregaciones en tiempo real. De lo contrario, habrá un intervalo de tiempo para el que no tendrá agregaciones.  
  
## <a name="see-also"></a>Vea también  
 [Consulta de datos de BAM](../core/querying-bam-data.md)