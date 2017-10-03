---
title: "Cómo crear un índice | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Create-Index command [BAM]
- indexes [BAM], creating
- indexes [BAM], aggregations
- creating, indexes [BAM]
- aggregations [BAM], indexes
ms.assetid: 456d94e6-2e84-4d12-ad38-49f9eeb103f3
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1427e8ee22e2012f759817350b0e3fa8ae49cf6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-index"></a>Cómo crear un índice
Los administradores utilizan el **índice crear** comando para crear un índice en la actividad especificada en los puntos de control especificados.  
  
### <a name="to-create-an-index-on-an-activity"></a>Para crear un índice en una actividad  
  
1.  Desde un símbolo del sistema, vaya al directorio siguiente: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]de seguimiento.  
  
2.  Tipo de **bm crear-index - IndexName:\<nombre de índice >-actividad:\<nombre de actividad >-punto de comprobación:\<punto de Control1 >**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
3.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Cómo eliminar un índice](../core/how-to-delete-an-index.md)   
 [Cómo obtener una lista de índices en una agregación](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)