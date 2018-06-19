---
title: 'Inicio de sesión único: Evento 10746 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc2bc096211d8a90089b3b5fdd31b4dbb82f2b14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270492"
---
# <a name="single-sign-on-event-10746"></a>Inicio de sesión único: Evento 10746
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10746|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PASSWORD_EXPIRED|  
|Texto del mensaje|La contraseña de la cuenta externa caducó.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que caducó la contraseña de la cuenta externa.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, compruebe los registros de eventos de aplicación y del sistema si hay errores asociados.    

## <a name="more-info"></a>Más información
Para obtener más información, vea los recursos siguientes:  
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)