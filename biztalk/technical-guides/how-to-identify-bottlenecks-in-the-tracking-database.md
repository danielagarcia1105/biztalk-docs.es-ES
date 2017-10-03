---
title: "Cómo identificar cuellos de botella en la base de datos de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b72e726-6225-47a0-8e1d-0f5a9cf745d3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16cd05b6c399d250d8a411f41f56406f19afc9e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-tracking-database"></a>Cómo identificar cuellos de botella en la base de datos de seguimiento
Para identificar cuellos de botella en la base de datos de seguimiento de BizTalk (BizTalkDTADb), realice los pasos siguientes:  
  
1.  Asegúrese de que servicio del Agente SQL está en ejecución.  
  
2.  Asegúrese de que el trabajo de archivo y purga esté en ejecución y que se esté realizando correctamente.  
  
3.  Asegúrese de que se ejecuta el trabajo TrackedMessages_Copy_BizTalkMsgBoxDB y se complete correctamente.  
  
4.  Compruebe que hay suficiente espacio disponible en disco para los archivos DTADb y para el crecimiento de la base de datos.  
  
5.  Use un host dedicado para realizar un seguimiento y medir el contador de rendimiento de longitud de la cola de Host en la carga.  
  
6.  Compruebe el contador de rendimiento de tamaño de tabla de cola de impresión para una tendencia creciente con el tiempo.  
  
7.  Compruebe la duración de ejecución del trabajo de archivo y purga de largos tiempos de ejecución.  
  
8.  Compruebe la capacidad de respuesta de disco (disco en segundos por lectura/escritura) en el disco que aloja la base de datos de seguimiento de BizTalk.  
  
 Se recomienda para la optimización hacia abajo el valor de los parámetros siguientes del dtasp_PurgeTrackingDatabase invocado por el trabajo DTA Purge and Archive o dtasp_backupandpurgetrackingdatabase por:  
  
-   @nLiveHourstinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados. Valor predeterminado es 0 horas.  
  
-   @nLiveDaystinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados. El intervalo predeterminado es 1 día.  
  
-   @nHardDeleteDaystinyint, todos los datos (aunque incompletos) anteriores a éste se eliminará. El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos. La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb). Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga. Valor predeterminado es 30 días.  
  
 Estos parámetros se deben establecer con arreglo a las directivas de retención de datos en un entorno de producción, mientras que en una prueba de laboratorio de rendimiento se recomienda que use valores como se indica a continuación:  
  
 declarar @dtLastBackup conjunto de fecha y hora @dtLastBackup = GetUTCDate()  
 exec dtasp_PurgeTrackingDatabase 1, 0, 1,@dtLastBackup  
  
## <a name="see-also"></a>Vea también  
 [Cuellos de botella en el nivel de base de datos](../technical-guides/bottlenecks-in-the-database-tier.md)