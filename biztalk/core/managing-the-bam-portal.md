---
title: Administrar el Portal de BAM en BizTalk Server | Documentos de Microsoft
Description: Información general de instalar y configurar el portal de BAM en BizTalk Server
ms.custom: ''
ms.date: 08/15/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a08aa85-3a45-4a8c-bdb5-5615ca097ce1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7908c9c7ce8e4b731e0b88569e3dc3fb228a1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262572"
---
# <a name="manage-the-bam-portal"></a>Administrar el portal de BAM

## <a name="set-up-bam-portal"></a>Configurar el portal de BAM
Los administradores configuran el portal de BAM al ejecutar la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Use la herramienta de configuración de BizTalk Server para determinar si BAM está habilitado y para determinar las cuentas de servicio web, los grupos de Windows que pueden ver el portal y el sitio web que hospedará el portal. Es necesario actualizar la configuración del portal de BAM una vez que lo haya configurado. Use la herramienta de configuración para actualizar los parámetros de configuración, tal como el grupo de usuarios del portal, la cuenta del grupo de aplicaciones y el usuario de los servicios web de administración.  
  
 Para obtener más información acerca de cómo instalar el portal de BAM, consulte [instalación y configuración de BAM en entornos de varios equipos](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx).  
  
 Para obtener más información acerca de cómo configurar el portal de BAM, consulte [configurar BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).
  
 El portal de BAM tiene muchos parámetros personalizables a los que se puede obtener acceso modificando el archivo webconfig.xml. Estos parámetros controlan el rendimiento y el funcionamiento del portal de BAM. El resto de esta sección describe la forma de personalizar la configuración de su portal de BAM.  
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Personalizar la configuración del Portal de BAM](../core/customizing-the-bam-portal-configuration.md)  
  
-   [Cómo configurar el Portal de BAM para trabajar en un clúster NLB](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)