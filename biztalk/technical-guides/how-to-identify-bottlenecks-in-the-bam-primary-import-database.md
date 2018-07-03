---
title: Cómo identificar cuellos de botella en la base de datos de importación principal de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 613bfa623110a4792894da71365c1a40d7856c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003629"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a>Cómo identificar cuellos de botella en la base de datos de importación principal de BAM
Para identificar cuellos de botella en la base de datos de supervisión de la actividad económica (BAM), realice los pasos siguientes:  
  
1. Asegúrese de que el número de instancias activas no aumente.  
  
2. Asegúrese de que servicio del Agente SQL está en ejecución.  
  
3. Si está configurado el análisis OLAP, asegúrese de que el BAM_AN_\<activityname\> trabajo se ejecute a intervalos periódicos.  
  
4. Asegúrese de que BAM_DM_\<activityname\> trabajo (Mantenimiento de datos) está programado para ejecutarse a intervalos periódicos.  
  
   > [!NOTE]
   >  En la actividad de base de datos BAM de escenarios de uso elevado puede afectar al rendimiento de otras bases de datos de BizTalk Server, lo que afectará el rendimiento general de BizTalk Server. En este caso, tenga en cuenta las siguientes acciones:  
   > 
   > - Considere la posibilidad de reducir la duración de todas las actividades BAM desde el valor predeterminado (6 meses) a 1 mes o menos. Esto reducirá el período de tiempo para que los datos BAM se mantienen en la base de datos BAMPrimaryImport antes de archivarse. Use la utilidad de administración de BAM `set-activitywindow` comando para modificar la duración de las actividades de BAM. Para obtener más información sobre la administración de actividades de la utilidad de administración de BAM Consulte comandos [comandos de administración de la actividad](http://go.microsoft.com/fwlink/?LinkId=210417) (http://go.microsoft.com/fwlink/?LinkId=210417).  
   >   -   Mover la base de datos de archivo de BAM a una instancia de SQL Server que no hospeda las bases de datos de BizTalk MessageBox. Esto impedirá que estas bases de datos de la competencia por los recursos y mejorar el rendimiento general.  
  
5. Usar un host dedicado para el seguimiento y medir el contador de rendimiento de longitud de cola de Host con la carga.  
  
6. Compruebe el contador de rendimiento de tamaño de tabla de cola de impresión para una tendencia en aumento con el tiempo.  
  
7. Comprobación de la duración de ejecución del trabajo de archivo y purga de largos tiempos de ejecución.  
  
8. Compruebe la capacidad de respuesta del disco (disco en segundos por contador de rendimiento de lectura/escritura) en el disco que hospeda la base de datos de seguimiento de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Cuellos de botella en el nivel de base de datos](../technical-guides/bottlenecks-in-the-database-tier.md)