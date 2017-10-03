---
title: "Cómo actualizar artefactos de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Update-All command [BAM]
- managing [BAM definitions], updating artifacts
- updating, artifacts
- artifacts, updating
ms.assetid: bc28159e-df51-499b-bd51-7b682b849891
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e377a455089127c9dc219846ec3f66e3322924cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-bam-artifacts"></a>Cómo actualizar artefactos de BAM
Los administradores utilizan el **update-all** comando para actualizar artefactos implementados en la base de datos de importación principal de BAM. La definición de BAM proporcionada es un archivo XML o un libro de Excel con información relativa a los artefactos que deben actualizarse.  
  
### <a name="to-update-bam-artifacts"></a>Para actualizar artefactos de BAM  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Tipo de **bm update-all - DefinitionFile:\<archivo def >**.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)