---
title: "Inicio de sesión único: Evento 10808 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b891a8cb076c332eca8918ece713385c1bbccc3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10808"></a>Inicio de sesión único: Evento 10808
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10808|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED|  
|Texto del mensaje|El sistema SSO no está habilitado para Inicio de sesión único iniciado por host.|  
  
## <a name="explanation"></a>Explicación  
 El sistema SSO no está habilitado para Inicio de sesión único iniciado por host.  
  
## <a name="user-action"></a>Acción del usuario  
 Use las herramientas administrativas para configurar el inicio de sesión único iniciado por host. Esto establecerá el marcador  
  
 SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS en la información global.