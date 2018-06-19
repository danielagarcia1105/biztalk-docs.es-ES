---
title: Preparar las aplicaciones para la recuperación ante desastres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ef93099-aa6b-424a-a4ce-87d855c6afe3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7028b1386f71f653dfc41b9de2522cdbd8d02126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302340"
---
# <a name="preparing-applications-for-disaster-recovery"></a>Preparar las aplicaciones para la recuperación ante desastres
Las aplicaciones de BizTalk (archivos binarios y los artefactos de una configuración como ubicaciones de recepción y puertos de envío) se implementan en el grupo de BizTalk de producción cuando se restaura el grupo en el sitio de recuperación ante desastres. Esta configuración deba modificarse dependiendo de si hay ubicaciones de configuración como ubicaciones de recepción y puertos de envío que son específicas de producción.  
  
 Para acelerar la restauración de aplicaciones en el sitio de recuperación ante desastres, un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI que instala los archivos binarios en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución deben estar actualizados en la recuperación ante desastres [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución. Cuando se restaura el grupo de BizTalk de producción en el sitio de recuperación ante desastres, puede deben instalarse con el fin de configurar la aplicación para los artefactos de específico sobre la recuperación ante desastres, como un archivo de MSI de configuración de aplicación específico sobre la recuperación ante desastres ubicaciones de recepción y puertos de envío, según sea necesario.  
  
## <a name="see-also"></a>Vea también  
 [Implementar una aplicación](../technical-guides/deploying-an-application.md)