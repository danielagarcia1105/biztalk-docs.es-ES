---
title: "Utilidad de administración de perfiles de cómo implementar perfiles de seguimiento con el seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dde3f351c583be9037127c060d02c98d12b2fcb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a>Cómo implementar perfiles de seguimiento con la utilidad de administración de perfiles de seguimiento
Un gestor empresarial pide a un programador de soluciones que cree un nuevo perfil de seguimiento o que modifique uno ya existente para administrar y supervisar mejor un proceso empresarial específico de la organización.  
  
 El programador de soluciones utiliza el Editor de perfiles de seguimiento (TPE) para definir los datos que necesita el analista de negocios.  
  
 Una vez que el programador de soluciones ha creado o modificado el perfil de seguimiento, el administrador usa la utilidad de línea de comandos bttdeploy.exe para implementarlo, para que los cambios se hagan efectivos y se recopilen los datos. El programador de soluciones puede implementar los perfiles de seguimiento con el TPE.  
  
> [!IMPORTANT]
>  Debe implementar los ensamblados asociados al perfil de seguimiento antes de implementar el perfil de seguimiento.  
  
> [!IMPORTANT]
>  Deberá disponer de privilegios de administrador de BizTalk® para utilizar esta herramienta.  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a>Para implementar el perfil de seguimiento desde la utilidad de línea de comandos  
  
1.  Desde un símbolo del sistema, desplácese hasta el directorio \<ruta de acceso de instalación\>\Program BizTalk Server \<versión\>\Tracking\\.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
2.  Tipo de **bttdeploy.exe \<nombre de perfil\>.btt**.  
  
3.  Presione ENTRAR.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Supervisión de la actividad económica (BAM)](../core/business-activity-monitoring-bam.md)