---
title: 'Inicio de sesión único: Evento 10610 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e4edc579c18147ad34234fbf268ec8d867c60f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271340"
---
# <a name="single-sign-on-event-10610"></a>Inicio de sesión único: Evento 10610
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10610|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_CRED_CACHE_FAILED|  
|Texto del mensaje|La memoria caché de credenciales detectó un error inesperado y se cerró. Esto puede afectar el rendimiento.%r<br /><br /> Código de error: %1|  
  
## <a name="explanation"></a>Explicación  
 La memoria caché de credenciales detectó un error inesperado y se cerró. Si bien este error puede afectar el rendimiento, no afectará la funcionalidad.  
  
## <a name="user-action"></a>Acción del usuario  
 Reinicie el servicio SSO cuando lo considere conveniente.