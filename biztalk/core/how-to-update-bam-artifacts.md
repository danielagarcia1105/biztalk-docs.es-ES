---
title: Cómo actualizar los artefactos de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update-All command [BAM]
- managing [BAM definitions], updating artifacts
- updating, artifacts
- artifacts, updating
ms.assetid: bc28159e-df51-499b-bd51-7b682b849891
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 083940baf4d6e51e15bc91f4ee7e867d50750c83
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011773"
---
# <a name="how-to-update-bam-artifacts"></a>Cómo actualizar artefactos de BAM
Los administradores utilizan el **update-all** comando para actualizar artefactos implementados en la base de datos de importación principal de BAM. La definición de BAM proporcionada es un archivo XML o un libro de Excel con información relativa a los artefactos que deben actualizarse.  
  
### <a name="to-update-bam-artifacts"></a>Para actualizar artefactos de BAM  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3. Tipo **bm update-all - DefinitionFile:\<archivo def\>**.  
  
4. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)