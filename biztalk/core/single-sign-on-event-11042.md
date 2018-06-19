---
title: 'Inicio de sesión único: Evento 11042 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da20346fbf2f73ac2ab64db3c9137394aa5bd366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277060"
---
# <a name="single-sign-on-event-11042"></a>Inicio de sesión único: Evento 11042
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11042|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_ACCESS_DENIED_ACCOUNTS|  
|Texto del mensaje|Acceso denegado.<br /><br /> El usuario del cliente debe ser miembro de una de las siguientes cuentas para realizar esta función.%r<br /><br /> Administradores de SSO: %1 %r<br /><br /> Administradores afiliados de SSO: %2 %r<br /><br /> Administradores de aplicación: %3 %r<br /><br /> Usuarios de aplicación: %4 %r<br /><br /> Datos adicionales: %5|  
  
## <a name="explanation"></a>Explicación  
 Para realizar esta función, el usuario del cliente debe ser miembro de una de las cuentas enumeradas en la advertencia.  
  
## <a name="user-action"></a>Acción del usuario  
 Debe unirse a una de las cuentas para realizar esta función.