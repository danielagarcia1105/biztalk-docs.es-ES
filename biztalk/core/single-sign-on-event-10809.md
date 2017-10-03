---
title: "Inicio de sesión único: Evento 10809 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e010c6ee391e72ec270ddbdc767bed861836cb8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10809"></a>Inicio de sesión único: Evento 10809
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10809|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_HISSO_APP_NOT_ENABLED|  
|Texto del mensaje|La aplicación no está habilitada para Inicio de sesión único iniciado por host.|  
  
## <a name="explanation"></a>Explicación  
 La aplicación no está habilitada para Inicio de sesión único iniciado por host.  
  
## <a name="user-action"></a>Acción del usuario  
 Use las herramientas administrativas para configurar el inicio de sesión único iniciado por host. Esto establecerá el marcador  
  
 SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS en la aplicación.