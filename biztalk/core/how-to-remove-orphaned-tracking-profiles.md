---
title: "Cómo quitar perfiles de seguimiento huérfanos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, orphans
- tracking profiles, activities
- tracking profiles, deleting
- activities, tracking profiles
ms.assetid: e8923dab-5d02-41a3-840b-104b20624e6c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33ddea8751a017db21306c06cdcca5929de641ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-orphaned-tracking-profiles"></a>Cómo quitar perfiles de seguimiento huérfanos
Los perfiles de seguimiento están asociados a una actividad. Cuando una actividad no está implementada, los perfiles de seguimiento pueden quedarse “huérfanos”, lo que significa que dejan de estar asociados a una actividad. Puede utilizar el procedimiento siguiente para quitar el perfil de seguimiento.  
  
### <a name="to-remove-an-orphaned-tracking-profile"></a>Para quitar un perfil de seguimiento huérfano  
  
1.  Vuelva a implementar la definición de BAM. Para obtener información acerca de cómo implementar definiciones de BAM, consulte [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).  
  
2.  Utilice el Editor de perfiles de seguimiento (TPE) para quitar el perfil de seguimiento. Para obtener información acerca de cómo quitar perfiles de seguimiento, vea [cómo aplicar y quitar un perfil de seguimiento](../core/how-to-apply-and-remove-a-tracking-profile.md).  
  
3.  Anule la implementación de la definición de BAM. Para obtener información acerca de cómo quitar definiciones de BAM, consulte [cómo quitar definiciones de BAM](../core/how-to-remove-bam-definitions.md).  
  
## <a name="see-also"></a>Vea también  
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)