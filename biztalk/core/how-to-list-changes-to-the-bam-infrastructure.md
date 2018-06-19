---
title: Cómo enumerar los cambios en la infraestructura de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], listing infrastructure changes
- managing [BAM definitions], listing infrastructure changes
- Get-Changes command [BAM]
- infrastructure, listing changes [BAM]
ms.assetid: 3feacd7d-6f42-4626-835b-0dc3befc9fd6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d0ed240f156d853c18f28a52022eea585af513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253924"
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a>Cómo enumerar cambios en la estructura de BAM
Los administradores utilizan el **get-changes** comando de la utilidad de administración de BAM para enumerar información actual acerca de una definición de BAM implementada. También puede utilizar el comando get-changes para enumerar los artefactos de implementación en la base de datos de importación principal de BAM.  
  
 La información incluye implementaciones y anulaciones de implementaciones que se han llevado a cabo correctamente, el nombre del archivo de definición de BAM, el nombre del archivo de configuración de BAM, los nombres de todas las actividades y vistas asociadas al archivo de definición y la cuenta de usuario que aplicó el cambio. La lista get-changes muestra las implementaciones y las supresiones de definiciones con sus números de identificación asociados.  
  
### <a name="to-list-changes-to-the-bam-definition"></a>Para enumerar cambios en la definición de BAM  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Tipo **bm get-changes.**  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)