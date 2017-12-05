---
title: "Cómo quitar artefactos implementados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1d3e395223840dd4caa534130061fac33e89b78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-remove-deployed-artifacts"></a>Cómo quitar artefactos implementados
Los administradores utilizan el **remove-all** comando para quitar artefactos implementados en la base de datos de importación principal de BAM. La definición de BAM proporcionada es un archivo XML o un libro de Excel con información relativa a los artefactos que deben quitarse.  
  
### <a name="to-remove-deployed-artifacts"></a>Para quitar artefactos implementados  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Tipo de **bm remove-all - DefinitionFile:\<archivo def\>**.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar un artefacto de BAM a una aplicación](../core/how-to-add-a-bam-artifact-to-an-application.md)   
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)