---
title: 'Inicio de sesión único: Evento 10818 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be2c40fa5da46f5045b55c815be9f6f8048cda67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277372"
---
# <a name="single-sign-on-event-10818"></a>Inicio de sesión único: Evento 10818
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10818|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_AMBIGUOUS_SYNC_FIELDS|  
|Texto del mensaje|La aplicación debe tener dos campo o se debe marcar un solo campo para sincronización.|  
  
## <a name="explanation"></a>Explicación  
 Si existen dos campos, sólo uno de ellos debe marcarse para sincronización de contraseñas.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este problema, debe eliminar la aplicación y crearla nuevamente para que respete estas pautas.