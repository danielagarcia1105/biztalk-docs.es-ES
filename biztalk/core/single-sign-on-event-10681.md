---
title: "Inicio de sesión único: Evento 10681 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd0f1b6c27f3e77220d4615da1c0b5bb343344de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10681"></a>Inicio de sesión único: Evento 10681
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10681|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE|  
|Texto del mensaje|Cambio de contraseña externa. No se cambió la contraseña de Windows porque uno o varios cambios de cuenta externa tienen error.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se cambió la contraseña de Windows porque uno o varios cambios de cuenta externa tienen error.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Compruebe los registros de eventos de aplicación y sistema de eventos asociados.  
  
-   Compruebe la configuración del adaptador mediante las herramientas de administración de SSO.  
  
-   Compruebe los sistemas externos.  
  
## <a name="more-info"></a>Más información
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)  
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]