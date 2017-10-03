---
title: "Inicio de sesión único: Evento 10804 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b65c59ce736804215cd7c70428905d776d8e0e4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10804"></a>Inicio de sesión único: Evento 10804
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10804|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_INCORRECT_COMPUTER|  
|Texto del mensaje|El adaptador no está configurado para este equipo.|  
  
## <a name="explanation"></a>Explicación  
 Cada adoptador se configura para ejecutarse en un equipo específico, que se identifica mediante su nombre largo. El nombre es incorrecto o se está intentando ejecutar el adaptador en otro equipo.  
  
## <a name="user-action"></a>Acción del usuario  
 Consulte la configuración del adaptador para determinar el nombre correcto del equipo correspondiente.