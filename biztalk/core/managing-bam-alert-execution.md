---
title: Administrar la ejecución de alertas de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], executing alerts
- Notification Services, configuration files
- BAM Management utility
- alerts, executing
ms.assetid: 44bb738e-fa2c-4b32-9e8d-e756d6c3778e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5607bed785ee4f91a341b546dbe81ec39458c4e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262564"
---
# <a name="managing-bam-alert-execution"></a>Administrar la ejecución de alertas BAM
Se puede modificar la ejecución de alertas BAM mediante la acción de tres elementos, a saber, el portal de BAM, la utilidad de administración de BAM y la cadena ProcessBamNSFiles.vbs.  
  
## <a name="bam-portal"></a>Portal de BAM  
 Los administradores y trabajadores del conocimiento pueden modificar la forma en la que se entregan las alertas mediante el Administrador de alertas en el portal de BAM. Desde el portal de BAM se pueden habilitar o deshabilitar las alertas, modificar los niveles de umbral, modificar las ubicaciones de entrega y otros parámetros que afectan a la ejecución de la alerta.  
  
 Para obtener más información acerca de cómo modificar alertas, consulte [Alert Manager en la página de Portal de BAM](../core/alert-manager-on-the-bam-portal-page.md) y [alertas del Portal de BAM](../core/alerts-in-the-bam-portal.md).  
  
### <a name="bam-management-utility"></a>Utilidad de administración de BAM  
 Los administradores pueden usar la utilidad de administración de BAM para habilitar, deshabilitar y quitar alertas.  
  
 Para obtener información acerca de cómo usar la utilidad de administración de BAM para administrar alertas, consulte los temas siguientes:  
  
-   [Cómo habilitar las alertas](../core/how-to-enable-alerts.md) 
  
-   [Cómo deshabilitar las alertas](../core/how-to-disable-alerts.md)  
  
-   [Cómo quitar alertas BAM](../core/how-to-remove-bam-alerts.md)  
  
### <a name="modifying-notification-services-configuration-files"></a>Modificar los archivos de configuración de servicios de notificación  
 Los administradores pueden utilizar la secuencia de comandos ProcessBamNSFiles.vbs para cambiar la forma en la que los servicios de notificación entregan las alertas. Para obtener más información del archivo de definición de aplicación (ADF) para que Notification Services, vea [http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016).  
  
 Para modificar el ADF asociado a BAM, puede seguir estos pasos generales:  
  
1.  Ejecute la secuencia de comandos para obtener la configuración actual y los archivos ADF.  
  
2.  Modifique los archivos.  
  
3.  Ejecute la secuencia de comandos para aplicar los cambios.  
  
 Para obtener más información sobre la secuencia de comandos ProcessBamNSFiles.vbs, consulte [secuencia de comandos de línea de comandos de BAM para archivos de configuración de servicios de notificación](../core/bam-command-line-script-for-notification-services-configuration-files.md).  
  
## <a name="see-also"></a>Vea también  
 [Administración del Portal BAM](../core/managing-the-bam-portal.md)   
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)