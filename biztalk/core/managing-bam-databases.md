---
title: Administrar bases de datos BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], databases
- databases [BAM], managing
- databases, BAM
ms.assetid: ce3c472e-2da1-4d67-816a-befe4ded20d9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dbe8cdb2c7806ab62b67db80c4741d64560fba9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262580"
---
# <a name="managing-bam-databases"></a>Administrar bases de datos de BAM
Los administradores se sirven de la utilidad de administración de BAM (bm.exe) para instalar, administrar y actualizar las bases de datos de BAM. Esta sección muestra cómo usar la utilidad de administración de BAM para llevar a cabo estas tareas comunes de administración para las bases de datos de BAM, descritas en la tabla siguiente.  
  
 Para obtener información acerca de la copia de seguridad y restaurar las bases de datos BAM, consulte [copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md).  
  
|Base de datos|Nombre predeterminado de la base de datos|Description|  
|--------------|---------------------------|-----------------|  
|Base de datos de importación principal de BAM|BAMPrimaryImport|Donde BAM recopila los datos de seguimiento sin procesar.|  
|Base de datos de la aplicación de servicios de notificación de BAM|BAMAlertsApplication|Contiene información de alertas para las notificaciones de BAM. Por ejemplo, al crear una alerta utilizando el portal de BAM, las entradas se insertan en la base de datos especificando las condiciones y eventos a los que pertenece la alerta, así como otros datos complementarios relativos a ésta.|  
|Base de datos de instancia de servicios de notificación de BAM|BAMAlertsNSMain|Contiene información de la instancia que especifica el modo en que los servicios de notificación establecen una conexión con el sistema controlado por BAM.|  
|Base de datos de esquema de estrella de SAE|BAMStarSchema|Contiene la tabla provisional y las tablas de dimensiones y medidas.|  
|Base de datos de análisis de BAM|BAMAnalysis|Contiene cubos OLAP de BAM para el análisis en línea y sin conexión.|  
|Base de datos de archivo SAE|BAMArchive|Archiva datos antiguos de la actividad de negocio. Puede crear una base de datos de archivo de BAM para minimizar la acumulación de datos de la actividad de negocio en la base de datos de importación principal de BAM.|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Archivar los datos de la base de datos de importación principal](../core/archiving-primary-import-database-data.md)  
  
-   [Crear una vista con particiones en la base de datos de archivado](../core/creating-a-partitioned-view-in-the-archiving-database.md)  
  
-   [Paquetes de programación de SQL Server Integration Services](../core/scheduling-sql-server-integration-services-packages.md)  
  
-   [Cómo configurar las bases de datos BAM mediante la utilidad de administración de BAM](../core/how-to-set-up-the-bam-databases-using-the-bam-management-utility.md)  
  
-   [Cómo recuperar el archivo de configuración de BAM mediante la utilidad de administración de BAM](../core/how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility.md)  
  
-   [Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM](../core/how-to-update-the-bam-configuration-using-the-bam-management-utility.md)  
  
-   [Cómo hacer referencia a las bases de datos de importación principal de BAM adicionales](../core/how-to-reference-additional-bam-primary-import-databases.md)  
  
-   [Cómo deshabilitar una referencia de base de datos de importación principal de BAM](../core/how-to-disable-a-bam-primary-import-database-reference.md)  
  
-   [Cómo enumerar todas hace referencia a las bases de datos](../core/how-to-list-all-referenced-databases.md)  
  
-   [Cómo quitar instancias de actividad incompletas](../core/how-to-remove-incomplete-activity-instances.md)  
  
-   [Cómo actualizar la configuración de utilidad de administración de BAM después de una copia de seguridad y restauración](../core/update-the-bam-management-utility-configuration-after-a-backup-and-restore.md)  
  
-   [Cómo integrar BAM con SQL Server Reporting Services](../core/how-to-integrate-bam-with-sql-server-reporting-services.md)  
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)