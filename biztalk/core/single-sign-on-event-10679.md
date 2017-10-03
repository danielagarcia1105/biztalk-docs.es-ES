---
title: "Inicio de sesión único: Evento 10679 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f612f3cf6540340124a3f11ed99fe736df65296b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10679"></a>Inicio de sesión único: Evento 10679
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10679|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PS_MAPPING_DISABLED|  
|Texto del mensaje|Cambio de contraseña externa. No se pudo cambiar la contraseña de la cuenta externa porque la asignación está deshabilitada.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Cuenta externa: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se cambió la contraseña de la cuenta externa porque la asignación está deshabilitada.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, haga lo siguiente:  
  
-   Use las herramientas de administración de SSO para habilitar la asignación para este adaptador.  
  
## <a name="more-info"></a>Más información
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)  
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]