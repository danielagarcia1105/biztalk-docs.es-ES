---
title: Limitaciones de la infraestructura BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e33d2f6c-8d26-4a76-810e-85d810cfdbee
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e42b2a6af04c2ff5d76d8ffb9489dfc2b92b6689
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="bam-infrastructure-limitations"></a>Limitaciones de la infraestructura de BAM
La infraestructura de BAM tiene las siguientes limitaciones de diseño para esta versión de BizTalk Server:  
  
-   Las agregaciones en tiempo real (ATR) no admiten las funciones MIN o MAX.  
  
-   No se puede hacer referencia a un alias de un solo nivel mediante más de una dimensión de datos en una vista ATR.  
  
-   Ni los cubos normales ni las ATR admiten medidas de recuento distintivas. La utilidad de administración de BAM crea una medida de recuento predeterminada para los cubos normales y las ATR. El recuento predeterminado es el recuento total de datos (al que también se conoce como "instancias de actividad"), y no el recuento distintivo.  
  
-   No defina varias ATR que usan la misma actividad de BAM . Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.  
  
## <a name="bam-maximum-number-of-objects"></a>Número máximo de objetos de BAM  
 En la tabla siguiente se enumera el número máximo de objetos de la infraestructura de BAM.  
  
|Object|Límite de implementación|Reason|  
|------------|--------------------------|------------|  
|Puntos de control en Actividad|1,000|SQL Server admite 1.024 argumentos de procedimientos almacenados y BizTalk Server usa tres de los procedimientos del sistema.|  
|Índices en Actividad|245|El servidor SQL Server admite 245 índices no agrupados por tabla. BizTalk Server crea siempre un índice en ActivityID.|  
|DataLength|4.000 caracteres Unicode|Se utilizan variables SQL de tipo NVARCHAR.|  
|ActivityRef|128|Puede obtener la vista uniendo la base de datos de importación principal y las tablas de relación (dos por actividad). El servidor SQL Server admite 256 tablas en la instrucción SELECT.|  
|Columnas de Vista<br /><br /> (Alias, duraciones y niveles de dimensión)|150|El servidor SQL Server tiene un límite de 1.024 columnas en la tabla provisional, de las cuales BAM reserva 24 como columnas del sistema.|  
|Dimensiones en el cubo OLAP|128|Limitación de OLAP: 128 dimensiones por cubo|  
|Medidas de OLAP|1,024|Limitación de OLAP: 1.024 medidas por cubo La medida Número siempre se crea.|  
|Niveles de dimensión de OLAP|64|Limitación de OLAP con un límite adicional de 256 niveles por cubo.|  
|Niveles de dimensión en la vista ATR|14 niveles de dimensión|BAM crea un índice en todos los niveles de dimensión. Se puede crear un índice del servidor SQL Server en un máximo de 16 columnas, y BAM reserva dos para columnas del sistema.|  
|Medidas, medidas ocultas (número predeterminado, medidas SUM ocultas para AVG) y niveles de dimensión en la vista ATR|1,024|Máximo de 1.024 columnas en tabla o vista SQL|  
|ActivityViews|63|Al configurar una alerta, estará limitado a 63 ActivityViews bajo SQL Server.|  
  
## <a name="bam-object-names"></a>Nombres de objeto de BAM  
 En la tabla siguiente se enumeran las limitaciones de nombres de objeto del esquema de definiciones de BAM y de la hoja de cálculo de Microsoft Excel.  
  
|Nombres de objeto|Limitación en XSD|Límite en Excel|  
|------------------|--------------------|----------------------|  
|Nombre de punto de control|50 caracteres|50 caracteres|  
|Nombre del índice|100 caracteres|100 caracteres|  
|Nombre de duración|100 caracteres|100 caracteres|  
|Nombre de alias|50 caracteres|50 caracteres|  
|Nombre de la actividad|48 caracteres|20 caracteres|  
|Nombre de la vista|18 caracteres|18 caracteres|  
|Nombre de ActivityView|52 caracteres (el nombre consta del sufijo "View" más los 48 caracteres del nombre de la vista).|N/D (derivado de Nombre de actividad)|  
|Nombre del cubo|20 caracteres|N/D (derivado de Nombre de vista)|  
|Nombre de RealTimeAggregation|48 caracteres|N/D (derivado de Nombre del cubo)|  
|Nombre de la dimensión|20 caracteres|20 caracteres|  
|Nombre del nivel|20 caracteres|20 caracteres|  
|Nombre de medida|20 caracteres|20 caracteres|  
|Nombre de alerta|128 caracteres|N/D|  
|Mensaje de alerta|1024 caracteres.|N/D|  
|Nombre de regla de evento|255 caracteres|N/D|  
|Nombre del proveedor de eventos|255 caracteres|N/D|  
  
## <a name="see-also"></a>Vea también  
 [Esquema de configuración de BAM](../core/bam-configuration-schema.md)   
 [Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md)