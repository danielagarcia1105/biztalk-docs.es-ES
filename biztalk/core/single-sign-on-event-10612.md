---
title: 'Inicio de sesión único: Evento 10612 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a85361bf9946efc283683d41ed0d08187e4d8754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271276"
---
# <a name="single-sign-on-event-10612"></a>Inicio de sesión único: Evento 10612
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10612|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_TRANSACTION_TIMEOUT|  
|Texto del mensaje|El tiempo de espera de transacción supera el máximo recomendado para la operación. Consulte la documentación de details.%r<br /><br /> Id. de transacción: %1 %r<br /><br /> Tiempo de espera de transacción: minutos %2 (cero indica un tiempo de espera infinito) %r<br /><br /> El tamaño máximo recomendado: %3 minutos|  
  
## <a name="explanation"></a>Explicación  
 El sistema recibió una transacción con un valor de tiempo de espera extremadamente grande. Si el sistema ENTSSO sondea la base de datos de SSO mientras está bloqueada por una transacción de larga duración, el sistema finalmente se desconectará.  
  
## <a name="user-action"></a>Acción del usuario  
 No se requiere ninguna acción del usuario.