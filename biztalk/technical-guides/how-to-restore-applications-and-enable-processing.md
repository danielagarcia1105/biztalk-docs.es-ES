---
title: Cómo restaurar las aplicaciones y habilitar el procesamiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aae2a6d9b4f3a35c55ffa731323547b1b54a4d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999413"
---
# <a name="how-to-restore-applications-and-enable-processing"></a>Cómo restaurar las aplicaciones y habilitar el procesamiento
Configurar las aplicaciones en el grupo de BizTalk y habilita el procesamiento de la aplicación después de seguir los pasos descritos en el tema [cómo actualizar los equipos en tiempo de ejecución](../technical-guides/how-to-update-the-runtime-computers.md).  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a>Para habilitar la configuración de la aplicación y restaurar el procesamiento de la aplicación  
  
1. Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de instalación de aplicación en cada servidor BizTalk server en el grupo.  
  
2. Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de la configuración de aplicación en un servidor en el grupo para configurar la aplicación para el sitio de recuperación ante desastres. Los nombres de las ubicaciones de recepción y envío puertos siguen siendo los mismos. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de la configuración de aplicación actualiza los enlaces de manera que hacen referencia estos artefactos a las ubicaciones correctas en el entorno de recuperación ante desastres.  
  
   > [!NOTE]  
   >  Si las ubicaciones de recepción y envío de los puertos no se ven afectados por la pérdida del sitio de producción, es posible que no sea necesario volver a configurar la aplicación con las ubicaciones de específicos de la recuperación ante desastres.  
  
3. Procesamiento de la aplicación de restauración habilitando la aplicación de todas las ubicaciones de recepción, puertos de envío y las instancias de host.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de los equipos en tiempo de ejecución](../technical-guides/recovering-the-runtime-computers.md)