---
title: "Inicio de sesión único: Evento 10843 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd86a39d515858e1cda09317ba6139bc67c95ed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10843"></a>Inicio de sesión único: Evento 10843
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10843|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_NO_SECRET2|  
|Texto del mensaje|No se puede realizar la tarea de cifrado o descifrado porque el secreto no está disponible en el servidor secreto principal. Consulte el registro de eventos (en el equipo "%1") para ver los errores relacionados.|  
  
## <a name="explanation"></a>Explicación  
 Acceso denegado.  
  
## <a name="user-action"></a>Acción del usuario  
 El servidor secreto principal está desconectado o le falta el secreto principal necesario. Consulte el registro de eventos en el equipo especificado para ver los errores relacionados.