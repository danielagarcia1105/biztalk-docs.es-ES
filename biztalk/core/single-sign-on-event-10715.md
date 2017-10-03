---
title: "Inicio de sesión único: Evento 10715 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f63c98d2-988e-466f-be40-171b13a34732
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24bf65f00d9ef915d585c91aa06900b96d4b44d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10715"></a>Inicio de sesión único: Evento 10715
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10715|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_NO_CREATE_ADAPTER|  
|Texto del mensaje|Para crear adaptadores, el usuario del cliente debe ser miembro de la cuenta de administradores de SSO.%r<br /><br /> El usuario cliente: %1 %r<br /><br /> Administradores de SSO: %2 %r<br /><br /> Adaptador: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que el usuario del cliente debe ser miembro de la cuenta de administradores de SSO para crear cuentas.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Inicie sesión con una cuenta que pertenezca al grupo de administradores de SSO.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Grupos de usuarios SSO](../core/sso-user-groups.md)