---
title: "Cómo cambiar la frecuencia con las alertas que se evalúan | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68f326ed-2017-4853-89b9-146cb0785554
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a686c7de8057fdf843ff855da109e77e8ba7b8ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-frequency-with-which-alerts-are-evaluated"></a>Cómo cambiar la frecuencia con la que se evalúan las alertas
Hay casos en los que el generador de SQL Server Notification Services no puede seguir los eventos generados por el proveedor de eventos de BAM cuando se implementa con la configuración predeterminada. Se puede aumentar la frecuencia (la duración del cuanto) con la que se evalúan los eventos con respecto a las alertas mediante la modificación del archivo adf.xml de Notification Services.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro de un grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que disponga de permisos para leer y escribir en la base de datos de importación principal. Generalmente, será un grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-modify-the-notification-services-generator-quantum-duration"></a>Para modificar la duración del cuanto del generador de Notification Services  
  
1.  Abra el símbolo del sistema de Notification Services. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2005**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **Símbolo del sistema de notification Services**.  
  
2.  Obtenga el archivo de configuración de Notification Services. En el símbolo del sistema, escriba: **cscript ProcessBamNSFiles.vbs-Get config.xml adf.xml \<PimaryImport servidor de base de datos > \< PimaryImport nombre de base de datos >**.  
  
3.  Modificar o agregar el \<QuantumDuration > elemento bajo el \<ApplicationExecutionSettings > nodo en el en el archivo adf.xml. Para obtener más información sobre elemento QuantumDuration, vea [http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803).  
  
4.  En el símbolo del sistema, escriba: **cscript ProcessBamNSFiles.vbs-actualizar config.xml adf.xml \<PimaryImport servidor de base de datos > \< PimaryImport nombre de base de datos >.**  
  
## <a name="see-also"></a>Vea también  
 [Archivos de configuración de servicios de Script de línea de comandos de BAM para la notificación](../core/bam-command-line-script-for-notification-services-configuration-files.md)