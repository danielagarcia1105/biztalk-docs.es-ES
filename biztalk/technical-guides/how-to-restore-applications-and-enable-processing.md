---
title: "Cómo restaurar las aplicaciones y habilitar el procesamiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65ae913d45f45b13458294863714823a41ff4e44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-applications-and-enable-processing"></a>Cómo restaurar las aplicaciones y habilitar el procesamiento
Configurar las aplicaciones en el grupo de BizTalk y habilitar el procesamiento de la aplicación después de seguir los pasos descritos en el tema [cómo actualizar los equipos en tiempo de ejecución](../technical-guides/how-to-update-the-runtime-computers.md).  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a>Para habilitar la configuración de la aplicación y restaurar el procesamiento de la aplicación  
  
1.  Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de instalación de aplicación en cada servidor BizTalk server en el grupo.  
  
2.  Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de configuración de aplicación en un servidor en el grupo para configurar la aplicación para el sitio de recuperación ante desastres. Los nombres de las ubicaciones de recepción y envían puertos siguen siendo los mismos. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de configuración de aplicación actualiza los enlaces de modo que estos artefactos señalen a las ubicaciones correctas en el entorno de recuperación ante desastres.  
  
    > [!NOTE]  
    >  Si las ubicaciones de recepción y envío puertos no se ven afectados por la pérdida del sitio de producción, puede no ser necesario volver a configurar la aplicación con ubicaciones de específico sobre la recuperación ante desastres.  
  
3.  Procesamiento de la aplicación de restauración habilitando la aplicación de todas las ubicaciones de recepción, puertos de envío y las instancias de host.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de los equipos en tiempo de ejecución](../technical-guides/recovering-the-runtime-computers.md)