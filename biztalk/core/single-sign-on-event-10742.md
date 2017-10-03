---
title: "Inicio de sesión único: Evento 10742 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abb3acb03e60d1d7a7e705ac8b36aa5157616f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10742"></a>Inicio de sesión único: Evento 10742
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10742|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_NO_UPDATE_ADAPTER|  
|Texto del mensaje|Para actualizar el adaptador, el usuario del cliente debe ser miembro de la cuenta de administradores de SSO o de la cuenta de administradores de aplicación.%r<br /><br /> El usuario cliente: %1 %r<br /><br /> Administradores de SSO: %2 %r<br /><br /> Administradores de aplicación: %3 %r<br /><br /> Adaptador: %4 %r<br /><br /> Código de error: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se intentó actualizar el adaptador especificado, pero que no pudo completarse la actualización porque la cuenta de usuario que se usó no es miembro de la cuenta de administradores de SSO o de la cuenta de administradores de aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Agregue la cuenta de usuario a la cuenta de administradores de SSO o a la cuenta de administradores de aplicación.  
  
-   Vuelva a intentar la actualización.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)