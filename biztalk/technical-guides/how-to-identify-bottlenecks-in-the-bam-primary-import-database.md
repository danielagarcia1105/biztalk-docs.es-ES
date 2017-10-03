---
title: "Cómo identificar cuellos de botella en la base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decf27009eea6aff0ff5ed9088ae49ef2014b1cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a>Cómo identificar cuellos de botella en la base de datos de importación principal de BAM
Para identificar cuellos de botella en la base de datos de supervisión de la actividad económica (BAM), realice los pasos siguientes:  
  
1.  Asegúrese de que el número de instancias activas no aumente.  
  
2.  Asegúrese de que servicio del Agente SQL está en ejecución.  
  
3.  Si está configurado el análisis OLAP, asegúrese de que el BAM_AN_\<activityname > trabajo se ejecuta a intervalos periódicos.  
  
4.  Asegúrese de que BAM_DM_\<activityname > trabajo (Mantenimiento de datos) está programado para ejecutarse a intervalos periódicos.  
  
    > [!NOTE]  
    >  En la actividad de base de datos BAM de escenarios de uso elevado puede afectar al rendimiento de otras bases de datos de BizTalk Server, lo que afectará al rendimiento general de BizTalk Server. En este caso, tenga en cuenta las siguientes medidas:  
    >   
    >  -   Considere la posibilidad de reducir la duración de todas las actividades BAM desde el valor predeterminado (6 meses) a 1 mes o menos. Esto reducirá el período de tiempo para que los datos BAM se mantienen en la base de datos BAMPrimaryImport antes de archivarse. Use la utilidad de administración de BAM `set-activitywindow` comando para modificar la duración de las actividades de BAM. Para obtener más información sobre la administración de actividades de la utilidad de administración de BAM vea comandos [comandos de administración de la actividad](http://go.microsoft.com/fwlink/?LinkId=210417) (http://go.microsoft.com/fwlink/?LinkId=210417).  
    > -   Mover la base de datos de archivo de BAM a una instancia de SQL Server que no aloja las bases de datos de BizTalk MessageBox. Esto impedirá que compiten por recursos estas bases de datos y mejorar el rendimiento general.  
  
5.  Use un host dedicado para realizar un seguimiento y medir el contador de rendimiento de longitud de la cola de Host en la carga.  
  
6.  Compruebe el contador de rendimiento de tamaño de tabla de cola de impresión para una tendencia creciente con el tiempo.  
  
7.  Compruebe la duración de ejecución del trabajo de archivo y purga de largos tiempos de ejecución.  
  
8.  Compruebe la capacidad de respuesta de disco (disco en segundos por lectura/escritura) en el disco que aloja la base de datos de seguimiento de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Cuellos de botella en el nivel de base de datos](../technical-guides/bottlenecks-in-the-database-tier.md)