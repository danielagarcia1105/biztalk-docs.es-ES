---
title: Cómo realizar copias de seguridad el análisis de BAM y el análisis de seguimiento de las bases de datos del servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, DTS packages
- backing up [BAM], Tracking Analysis Server database
- backing up [BAM], OLAP cubes
- backing up [BAM], DTS packages
- purging, OLAP cubes
- Analysis database [BAM], backing up
- scheduling, BAM backups
- backing up [BAM], Analysis database
- OLAP cubes, purging
- backing up, BAM
- backing up [BAM], database order
- DTS packages, backing up
- backing up [BAM], Star Schema database
- backing up [BAM], scheduling
- Tracking Analysis Server database [BAM], backing up
- Star Schema database [BAM], backing up
ms.assetid: d39e3491-ab54-44f2-990a-7b8ee86f0501
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1b7dca60859d0dcda69d6c9110b4be08d90586b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983381"
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>Cómo realizar una copia de seguridad de las bases de datos de servidor de análisis de seguimiento y de análisis de SAE
La base de datos de análisis de Supervisión de la actividad económica (SAE) y la base de datos de servidor de análisis de seguimiento almacenan contenido en los cubos de los servicios de análisis de SQL Server. El trabajo de copia de seguridad de BizTalk Server no realiza ninguna copia de seguridad de estas bases de datos. Para ello, tendrá que utilizar Analysis Manager de SQL Server.  
  
 Después de realizar una copia de seguridad de estas bases de datos, es posible que desee purgar los cubos OLAP. Al purgar los cubos OLAP, también debe llevar a cabo los pasos siguientes:  
  
1. Antes de purgar los cubos OLAP, en la base de datos BAMStarSchema, trunque las tablas de hechos del cubo que desee purgar. La convención de nomenclatura de la tabla es "bam_*\<CubeName\>*_Facts".  
  
2. Tras purgar los cubos OLAP, debe procesar completamente los cubos virtuales, completados y activos.  
  
   Para obtener instrucciones acerca de la copia de seguridad de las bases de datos de análisis, vea la sección que trata acerca del proceso de archivo de una base de datos de servicios de análisis de los Libros en pantalla de SQL Server.  
  
   **Programar copias de seguridad para las bases de datos BAM**  
  
   Si utiliza SAE, compruebe que los paquetes de Servicios de transformación de datos (DTS) de mantenimiento de datos o procesos de cubo de SAE no estén en ejecución cuando el paquete de copia de seguridad está programado para ejecutarse.  
  
   Para garantizar la consistencia del esquema en todas las bases de datos de SAE, realice una copia de seguridad de las bases de datos de SAE y de los paquetes DTS siempre vez que implemente una actividad de SAE o anule la implementación de ésta.  
  
   Realice una copia de seguridad de la base de datos de análisis de BAM y de la base de datos BAMStarSchema siempre que implemente una vista de SAE o anule la implementación de ésta.  
  
   Realice una copia de seguridad de las bases de datos de SAE de acuerdo con el orden que se especifica a continuación:  
  
3. Ejecute el trabajo de copia de seguridad de BizTalk Server para realizar una copia de seguridad de la base de datos BAMPrimaryImport y de las otras bases de datos de BizTalk Server.  
  
4. Ejecute el paquete DTS de mantenimiento de datos de SAE para todas las actividades.  
  
    Integre estos pasos a un paquete DTS y programe este último para que se ejecute de forma regular. Para garantizar la integridad de los datos, asegúrese de que ningún otro paquete DTS de mantenimiento de datos o elaboración de cubos de SAE se ejecuta cuando el paquete de copia de seguridad tenga programada su ejecución.  
  
    Para garantizar la posibilidad de recuperación de un conjunto completo de datos archivados en el caso de que se produzca un error de la base de datos BAMArchive, realice una copia de seguridad de esta última tras copiar en ella la partición, pero antes de eliminar la partición de la base de datos BAMPrimaryImport. Para ello, modifique el paquete DTS de mantenimiento de datos para cada una de las actividades con el fin de insertar un paso para realizar una copia de seguridad de la base de datos BAMArchive antes del último paso del paquete DTS, "Finalizar archivo".  
  
5. Realice una copia de seguridad de la base de datos BAMAnalysis y, a continuación, de la base de datos BAMStarSchema.  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad y restaurar las bases de datos de BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md)