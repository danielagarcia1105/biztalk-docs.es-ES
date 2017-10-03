---
title: "Inicio de sesión único: Evento 10603 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 139d1eb5-af88-4216-9604-c052f3db13c9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738d2939f4178fdfaa115b8dfcc2273935c37b85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10603"></a>Inicio de sesión único: Evento 10603
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10603|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_DB_ACCESS|  
|Texto del mensaje|No se pudo obtener acceso a la base de datos de SSO. Si esta condición persiste, el servicio SSO se desconectará.%r<br /><br /> %1.%r<br /><br /> Código de Error de SQL: %2|  
  
## <a name="explanation"></a>Explicación  
 La base de datos de SSO no está disponible.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe el código de error de SQL de la advertencia. Es posible que ésta ofrezca ayuda. De lo contrario, póngase en contacto con los Servicios de soporte técnico de Microsoft.