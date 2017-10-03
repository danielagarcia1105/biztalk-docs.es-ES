---
title: "Inicio de sesión único: Evento 11057 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca69661d1421433c44472e0572c5d4d4bf76a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11057"></a>Inicio de sesión único: Evento 11057
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11057|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS|  
|Texto del mensaje|Cambio directo de contraseña. Algunos campos de credenciales externas faltantes de esta asignación se han establecido en los valores predeterminados.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Nombre de la aplicación: %2 %r<br /><br /> Cuenta de Windows: %3 %r<br /><br /> Cuenta externa: %4|  
  
## <a name="explanation"></a>Explicación  
 Si bien es posible cambiar contraseñas mediante Sincronización directa de contraseñas, esta característica únicamente admite un solo campo de credencial externa. En este caso, el sistema ENTSSO ha detectado varios campos de credenciales externas y los ha establecido en los valores predeterminados (en blanco).  
  
## <a name="user-action"></a>Acción del usuario  
 No es necesario que el usuario realice ninguna acción.