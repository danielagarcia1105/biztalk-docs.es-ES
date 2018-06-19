---
title: 'Inicio de sesión único: Evento 11026 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e39b252d-2ed0-4006-aac2-4dce6504afb2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecee6d3c3e6dcf01b8489c4041f4aab717eba585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278284"
---
# <a name="single-sign-on-event-11026"></a>Inicio de sesión único: Evento 11026
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11026|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_EXISTING_GROUP_MAPPING|  
|Texto del mensaje|No se pudo crear la asignación de grupo nueva debido a un conflicto con una asignación existente. Elimine la asignación existente y vuelva a intentarlo.%r<br /><br /> Asignación existente: %1 %r<br /><br /> Nueva asignación: %2 %r<br /><br /> Cuenta externa: %3 %r<br /><br /> Nombre de la aplicación: %4|  
  
## <a name="explanation"></a>Explicación  
 La causa más probable es que el sistema está usando una versión anterior de Inicio de sesión único empresarial y aplicaciones de grupo antiguas.  
  
## <a name="user-action"></a>Acción del usuario  
 Elimine la asignación y vuelva a crearla según se recomienda en la advertencia. Si esto no funciona, es posible que deba actualizar a una versión más reciente de Inicio de sesión único empresarial.