---
title: "Configuración de recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8c6a188255097f0a1c1e85086688252f9154b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-for-disaster-recovery"></a>Configuración de recuperación ante desastres
El [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] característica de trasvase de registros extiende la copia de seguridad existente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo. [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Elimina la necesidad de restaurar de forma manual una serie de conjuntos de copia de seguridad generados por el trabajo de copia de seguridad de trasvase de registros y reduce el tiempo de inactividad en caso de un error del sistema. [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Trasvase de registros es un componente esencial para ver los procedimientos de recuperación ante desastres de BizTalk.  
  
> [!NOTE]  
>  Cada equipo de la aplicación debe tener una copia de seguridad documentado y restaurar el plan de recuperación ante desastres que complementa los conceptos proporcionados en este tema. El plan general debería tratar todo el sistema, incluidas las aplicaciones y los componentes del sistema operativo.  
  
 Realizar una operación de recuperación ante desastres es muy similar a realizar manualmente una restauración de un grupo de BizTalk a un nuevo conjunto de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias de base de datos. La principal diferencia es que [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] registros continuamente en el sitio de recuperación ante desastres, guardar muchos pasos manuales aplica el trasvase de registros. Por lo tanto, solo el último conjunto de registros se debe restaurar manualmente cuando [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se implementa el trasvase de registros. En caso contrario, la última copia de seguridad completa seguida de todas las copias de seguridad del registro desde la última copia de seguridad que se restaura manualmente. [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]trasvase de registros reduce el esfuerzo necesario para hacerlo manualmente, lo que acelera la restauración del sitio de recuperación ante desastres.  
  
 Esta sección contiene recomendaciones de configuración de producción para facilitar el proceso de recuperación ante desastres.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Preparar el sitio de recuperación ante desastres](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [Roles y cuentas de usuario de trasvase de registros](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [Trasvase de registros de configuración de BizTalk Server](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a>Vea también  
 [Recuperación ante desastres](../technical-guides/disaster-recovery.md)