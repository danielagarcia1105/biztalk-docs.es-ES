---
title: Cómo crear una tarea de análisis personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, DTS tasks
- DTS tasks
- DTS packages, tasks
- BAM, processing
ms.assetid: 6046c113-fb58-4e72-8f48-5470e52be9a8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8683e95373bbfa806cc9ac9ae27e90a661d006e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977589"
---
# <a name="how-to-create-a-custom-analysis-task"></a>Cómo crear una tarea de análisis personalizada
La manera más sencilla de crear una tarea DTS personalizada para procesar datos de BAM consiste en empezar por el paquete generado por BAM de forma automática y sustituir todo el procesamiento real de datos.  
  
### <a name="to-create-a-custom-dts-task"></a>Para crear una tarea DTS personalizada  
  
1. Cree una definición de BAM que requiera un cubo OLAP. Por ejemplo, utilice los asistentes de Excel y deje un informe de tabla dinámica® como vista no ATR.  
  
2. Abra el paquete DTS de procesamiento de cubos creado por BAM. BAM crea un paquete de este tipo para cada vista, conocida como BAM_AN_\<*nombre de la vista*\>.  
  
3. Abra el paquete en el Diseñador DTS y quite todos los pasos, excepto los dos primeros y el último. Puede que desee conservar también la conexión a la base de datos de importación principal.  
  
4. Edite las propiedades de la primera tarea ActiveX®. Quite todas las líneas que contengan DTSGlobalVariables.Parent.Steps, ya que se refieren a los pasos eliminados. La secuencia de comandos empieza con:  
  
   ```  
   serverName = "<your server here>"   
   databaseName = "<your analysis database here>"  
   cubeName = "<your cube name here>"  
   ```  
  
   > [!NOTE]
   >  La tarea "Comenzar análisis de datos" (la segunda tarea del paquete) es muy importante, puesto que aporta al paquete lo siguiente:  
   > 
   > - Una ventana móvil para el procesamiento incremental de las actividades finalizadas [la vista SQL dinámica denominada bam_(BamView)_View(Activity)_CompletedInstancesWindow]  
   >   -   Una instantánea de las actividades que están en curso: una tabla denominada bam\_(BamView) _View (Activity) _ActiveInstancesSnapshot.  
  
5. Obtenga la vista y la tabla en una transacción breve, durante la cual no debe insertar datos, de modo que los datos representen una instantánea real e inmediata de la base de datos de importación principal. Implemente uno o varios pasos para realizar las transformaciones de datos reales, basándose en la vista y en la tabla como datos de entrada. Si la tarea de análisis tiene una finalidad distinta a la de rellenar un cubo OLAP, recuerde conservar una marca de fecha y hora del momento en que se confirmó el trabajo por última vez, y de sustituir la primera tarea ActiveX por el código que asigna esta marca de fecha y hora a la variable global “CompletedCubeLastProcessTime”. La segunda tarea utiliza esta variable para asegurarse de que no se han perdido datos, y de que no hay datos que se hayan procesado dos veces en caso de un error y del posterior reinicio del paquete DTS.  
  
6. Por último, debe llamar a la última tarea, que es “Finalizar análisis de datos”. Esta tarea libera las actividades finalizadas que se han procesado, de modo que puedan archivarse y quitarse de la base de datos de importación principal una vez que estén fuera de la ventana en línea.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la actividad económica de supervisión](../core/using-business-activity-monitoring.md)