---
title: No se puede combinar operaciones debido a una colisión de nombres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81ddb8b7-6f7e-420c-b7c3-921c0e305326
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f884b4eea6be64f1d1575b157805703d12cee3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231716"
---
# <a name="cannot-merge-operations-due-to-name-collision"></a>No se pueden combinar operaciones debido a una colisión de nombres
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se puede combinar la operación "{0}". Colisión de nombres. Todas las operaciones de un servicio web deben tener nombres únicos.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el nombre de puerto o el nombre de operación de dos puertos diferentes que se están combinando son iguales.  
  
## <a name="user-action"></a>Acción del usuario  
 Con el Asistente para configuración de puertos, asegúrese de que todos los puertos que se combinan tienen nombres de puerto y de operación diferentes.  
  
 Para obtener más información sobre la configuración de puertos, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md)