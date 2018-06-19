---
title: 'Inicio de sesión único: Evento 11016 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3963b706-168d-438d-a068-637f8a6b7b0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f84bfef5dcef8e28bb3616ce30f1addc77f240c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276532"
---
# <a name="single-sign-on-event-11016"></a>Inicio de sesión único: Evento 11016
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11016|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|INFORMACIÓN AMPLIADA DE ERRORES DE RPC%r|  
|Texto del mensaje|%1%r<br /><br /> Código de error: %2<br /><br /> Error en la función AuthzInitializeContextFromSid con ERROR_ACCESS_DENIED. Esto significa que la cuenta de servicio en la que se ejecuta el servidor de SSO no tiene permisos suficientes para comprobar la pertenencia a grupos en Active Directory. Consulte la documentación para obtener información detallada sobre el procedimiento para solucionar este problema.%r|  
  
## <a name="explanation"></a>Explicación  
 La cuenta de servicio en la que se ejecuta el servidor de SSO no tiene permisos suficientes para comprobar la pertenencia a grupos en Active Directory.  
  
## <a name="user-action"></a>Acción del usuario  
 Vea [servidor de SSO](../core/sso-server.md) en la documentación de SSO.