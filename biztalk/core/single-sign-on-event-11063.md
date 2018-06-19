---
title: 'Inicio de sesión único: Evento 11063 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c84f91de-221d-43c4-8d23-3d1b7fd29cf7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82581dafd58a07ed217a5e9062aa91057a84aed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276956"
---
# <a name="single-sign-on-event-11063"></a>Inicio de sesión único: Evento 11063
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11063|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED|  
|Texto del mensaje|Acceso denegado al servidor de sincronización de contraseñas (para MIIS).%r|  
  
## <a name="explanation"></a>Explicación  
 Se denegó el acceso a la devolución de llamada de MIIS. La causa más probable de este error es que no se pudo usar la autenticación Kerberos entre el sistema ENTSSO y MIIS.  
  
## <a name="user-action"></a>Acción del usuario  
 Confirme si el sistema ENTSSO usa la autenticación Kerberos. Para obtener más información, consulte [recomendaciones de seguridad de SSO](../core/sso-security-recommendations.md).