---
title: 'Lista de comprobación: Copia de seguridad y restauración | Documentos de Microsoft'
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1d46a59-54f9-483e-9290-f4a9461006a7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97b872582cd0ad9f882dd04f641575bae9636bad
ms.sourcegitcommit: d0a1816a8dd8412906245d40c6479b08d7b3b20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
ms.locfileid: "28910100"
---
# <a name="checklist-backup-and-restore"></a>Lista de comprobación: Copia de seguridad y restauración
Realice los siguientes pasos antes de que se produzca un error de hardware, para asegurar que puede restaurar el sistema BizTalk Server.  
  
## <a name="back-up-biztalk-server"></a>Hacer copia de seguridad de BizTalk Server  
  
|Paso|Referencia|  
|----------|---------------|  
|Mantenga un registro escrito de todos los cambios realizados en el sistema BizTalk Server.||  
|Asegúrese de contar con los permisos apropiados para realizar una copia de seguridad de BizTalk Server y efectuar su restauración.|[Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)|  
|Aprenda cómo realizar una copia y restaurar las bases de datos de BizTalk Server.|[Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|Configure el trabajo de copia de seguridad de BizTalk Server para poder realizar una copia de seguridad de las bases de datos de BizTalk Server.|[Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|Configure el servidor en el que se almacenarán las copias de seguridad de la base de datos.|[Cómo configurar el sistema de destino de trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|Si está utilizando Supervisión de la actividad económica (SAE), realice una copia de seguridad de la base de datos de SAE.|[Realizar una copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)|  
|Si está utilizando Inicio de sesión único (SSO) empresarial, realice una copia de seguridad del secreto principal.|[Administración del secreto maestro](../core/managing-the-master-secret.md)|  
|Realice una copia de seguridad del archivo de configuración de BizTalk Server.|[Cómo hacer copia de seguridad de la configuración de servidor BizTalk Server](../core/how-to-back-up-the-biztalk-server-configuration.md)|  
|Realice una copia de seguridad del secreto principal de inicio de sesión único empresarial.|[Cómo realizar copias de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md)|  
|Realice una copia de seguridad de los grupos de aplicación del portal de SAE y de la información de configuración de directorios virtuales. No necesita realizar este paso si no usa BAM.|[Cómo realizar copias de seguridad del Portal de BAM](../core/how-to-back-up-the-bam-portal.md)|  
|Realice una copia de seguridad de las aplicaciones de BizTalk.|[Realizar una copia de seguridad de las aplicaciones de BizTalk Server](../core/backing-up-biztalk-server-applications.md)|  
  
## <a name="restore-biztalk-server"></a>Restaurar el servidor BizTalk Server  
  
|Paso|Referencia|  
|----------|---------------|  
|Restaure las bases de datos.|[Cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md)|  
|Actualice las referencias a los nombres de base de datos de SAE.|[Cómo realizar una copia del análisis de seguimiento y análisis de BAM bases de datos de servidor](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [Cómo actualizar referencias al servidor de análisis BAM y nombres de base de datos de esquema en estrella](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [Cómo actualizar referencias al nombre de base de datos de archivo BAM](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [Cómo actualizar referencias a la cadena de conexión y el nombre de base de datos de importación principal de BAM](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [Cómo actualizar referencias a la notificación de BAM de servicios de bases de datos](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [Cómo resolver instancias de actividad incompletas](../core/how-to-resolve-incomplete-activity-instances.md)|  
|Si está utilizando el inicio de sesión único empresarial, restaure el secreto principal.|[Administración del secreto maestro](../core/managing-the-master-secret.md)|  
|Si se produce un error en el equipo que ejecuta BizTalk Server, instale BizTalk Server en el equipo de sustitución.|[Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)|  
|Restaure el almacén de certificados.<br /><br /> Este paso es necesario para la edición estándar. No es necesario para otras ediciones, como por ejemplo Edición empresarial, ya que el proceso de configuración lo realiza automáticamente.|[Cómo restaurar el almacén de certificados](../core/how-to-restore-the-certificate-store.md)|  
|Restaure el inicio de sesión único empresarial|[Cómo recuperar el inicio de sesión único empresarial](../core/how-to-recover-enterprise-single-sign-on.md)|  
|Restaure el grupo de BizTalk|[Cómo recuperar el grupo de BizTalk](../core/how-to-recover-the-biztalk-group.md)<br /><br /> Si restaura Standard Edition, debe descargar un script que facilita la recuperación del servidor. Descargar [RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462).|  
|Restaure la configuración de BizTalk Server|[Cómo recuperar la configuración de BizTalk Server](../core/how-to-recover-the-biztalk-server-configuration.md)|  
|Si va a utilizar SAE, debe restaurar las alertas SAE.<br /><br /> No necesita realizar este paso si no usa BAM.|[Cómo recuperar las alertas de BAM](../core/how-to-recover-bam-alerts.md)|  
|Si va a utilizar SAE, debe restaurar el portal SAE.<br /><br /> No necesita realizar este paso si no usa BAM.|[Cómo recuperar el Portal de BAM](../core/how-to-recover-the-bam-portal.md)|  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad y una restauración de BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)
