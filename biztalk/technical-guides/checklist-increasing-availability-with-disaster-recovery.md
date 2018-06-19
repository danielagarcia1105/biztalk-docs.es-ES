---
title: 'Lista de comprobación: Aumentar la disponibilidad con recuperación ante desastres | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b315110-206a-4fa7-9bde-abab1429c83b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8790d82e3e5830e8145a8af2614413936f3e4b55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300204"
---
# <a name="checklist-increasing-availability-with-disaster-recovery"></a>Lista de comprobación: Aumentar la disponibilidad con recuperación ante desastres
En este tema se describe los pasos que debe seguir para aumentar la disponibilidad de una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la recuperación ante desastres. Recuperación ante desastres se suele implementar después de proporcionar alta disponibilidad con tolerancia a errores y equilibrio de carga.  
  
## <a name="backing-up-biztalk-server"></a>Realizar una copia de seguridad de BizTalk Server  
  
|Paso|Referencia|  
|----------|---------------|  
|Mantener un registro escrito de todos los cambios en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.||  
|Asegúrese de que tiene los permisos adecuados para la copia de seguridad y restaurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|Vea [derechos de usuario mínimos de seguridad](http://go.microsoft.com/fwlink/?LinkId=154374) (http://go.microsoft.com/fwlink/?LinkId=154374)|  
|Crear un recurso compartido de archivos de alta disponibilidad para almacenar el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] registros. Configurar un recurso compartido de archivos de alta disponibilidad en el nivel de hardware con una SAN o en el nivel de servidor de Windows mediante el uso de clústeres de Windows.|Vea [cómo crear recursos compartidos de archivos en un clúster de](http://support.microsoft.com/kb/224967) (http://support.microsoft.com/kb/224967)|  
|Instalar y poner a disposición en espera de uno o varios [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias como el destino de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros. El hardware y el número de destino [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias deben coincidir con el hardware y el número de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias en el entorno de producción. Esto garantizará que el destino [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias pueden controlar la misma carga de producción [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.|Vea [instalar SQL Server 2008](http://go.microsoft.com/fwlink/?LinkId=154377) (http://go.microsoft.com/fwlink/?LinkId=154377)|  
|Preparar el sitio de recuperación ante desastres.|[Preparar el sitio de recuperación ante desastres](../technical-guides/prepare-the-disaster-recovery-site.md)|  
|Copia de seguridad y restaurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos|-   [Prácticas recomendadas para realizar copias de seguridad y restaurar bases de datos](http://go.microsoft.com/fwlink/?LinkId=157758) (http://go.microsoft.com/fwlink/?LinkId=157758)<br />-   [Copia de seguridad y restaurar bases de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=157757) (http://go.microsoft.com/fwlink/?LinkId=157757)|  
|Configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros.|[Trasvase de registros de configuración de BizTalk Server](../technical-guides/configuring-biztalk-server-log-shipping.md)|  
|Configurar la copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo.|[Cómo configurar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154072) (http://go.microsoft.com/fwlink/?LinkID=154072)|  
|Configure el servidor en el que se almacenarán las copias de seguridad.|[Cómo configurar el sistema de destino de trasvase de registros](http://go.microsoft.com/fwlink/?LinkID=151402) (http://go.microsoft.com/fwlink/?LinkID=151402)|  
|Si está utilizando Supervisión de la actividad económica (SAE), realice una copia de seguridad de la base de datos de SAE.|[Copia de seguridad el análisis BAM y las bases de datos del servidor de análisis de seguimiento](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)|  
|Si está utilizando BAM, realizar una copia de los grupos de aplicaciones de portal de BAM y la información de configuración de directorios virtuales. No necesita realizar este paso si no usa BAM.|[Cómo realizar copias de seguridad del Portal de BAM](http://go.microsoft.com/fwlink/?LinkId=154378) (http://go.microsoft.com/fwlink/?LinkId=154378)|  
|Copia de seguridad la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo de configuración.|[Cómo hacer copia de seguridad la configuración de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154379) (http://go.microsoft.com/fwlink/?LinkId=154379)|  
|Si usas el inicio de sesión único empresarial, respaldar el servidor secreto principal.|[Cómo realizar copias de seguridad del secreto principal](http://go.microsoft.com/fwlink/?LinkID=151395) (http://go.microsoft.com/fwlink/?LinkID=151395)|  
  
## <a name="restoring-biztalk-server"></a>Restaurar BizTalk Server  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Restaurar el grupo de BizTalk.|[Restaurar el grupo de BizTalk](../technical-guides/restoring-the-biztalk-group.md)|  
|Recuperar los equipos de tiempo de ejecución que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|[Recuperación de los equipos en tiempo de ejecución](../technical-guides/recovering-the-runtime-computers.md)|  
|Recuperar las alertas de BAM.|[Cómo recuperar las alertas de BAM](http://go.microsoft.com/fwlink/?LinkId=154380) (http://go.microsoft.com/fwlink/?LinkId=154380)|  
|Recuperar el portal de BAM.|[Cómo recuperar el Portal de BAM](http://go.microsoft.com/fwlink/?LinkId=154381) (http://go.microsoft.com/fwlink/?LinkId=154381)|  
|Restaurar el servidor secreto principal.|[Cómo restaurar el secreto principal](http://go.microsoft.com/fwlink/?LinkId=151394) (http://go.microsoft.com/fwlink/?LinkId=151394)|  
|Restaurar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.|[Cómo restaurar las bases de datos](http://go.microsoft.com/fwlink/?LinkId=151406) (http://go.microsoft.com/fwlink/?LinkId=151406)|  
|Actualice las referencias a los nombres de base de datos de SAE.|-   [Actualizar las referencias a la nueva base de datos de importación principal de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)<br />-   [Actualizar las referencias a la nueva base de datos de archivo BAM](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)<br />-   [Actualizar las referencias a la nueva base de datos de esquema de estrella de BAM](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)<br />-   [Actualizar las referencias a la nueva base de datos de análisis BAM](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)<br />-   [Actualizar las referencias a la nueva notificación de BAM de servicios de bases de datos](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)<br />-   [Cómo resolver instancias de actividad incompletas](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475)|  
  
## <a name="see-also"></a>Vea también  
 [Recuperación ante desastres](../technical-guides/disaster-recovery.md)