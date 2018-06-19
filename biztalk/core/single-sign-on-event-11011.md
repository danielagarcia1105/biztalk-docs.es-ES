---
title: 'Inicio de sesión único: Evento 11011 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4ef430a-fb3b-4bf7-936f-a866262a6c3a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77d2cd649ed0aad513b1cab5aeba232f967f2736
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277804"
---
# <a name="single-sign-on-event-11011"></a>Inicio de sesión único: Evento 11011
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11011|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_NOT_APP_ADMIN|  
|Texto del mensaje|El usuario del cliente no es miembro de la cuenta de administradores de aplicación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> El usuario cliente: %2\\%3 %r<br /><br /> Nombre de la aplicación: %4 %r<br /><br /> Los administradores de aplicaciones: %5|  
  
## <a name="explanation"></a>Explicación  
 El usuario del cliente no es miembro de la cuenta de administradores de aplicación. Esta advertencia sólo se muestra cuando los niveles de auditoría se establecen en Alto.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar el problema, debe incluir al usuario del cliente como miembro de la cuenta de administradores de aplicación. Para que esta advertencia no vuelva a aparecer en el futuro, puede reducir los niveles de seguridad.