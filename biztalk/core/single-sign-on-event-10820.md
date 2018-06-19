---
title: 'Inicio de sesión único: Evento 10820 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a3ae1be84ca0b936fe38463e51e6385071f7a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276692"
---
# <a name="single-sign-on-event-10820"></a>Inicio de sesión único: Evento 10820
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10820|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_REQUIRE_OLD_PASSWORD|  
|Texto del mensaje|Al cambiar la contraseña de una cuenta externa, el adaptador debe proporcionar la contraseña anterior.|  
  
## <a name="explanation"></a>Explicación  
 Esta aplicación está configurada para que el adaptador de sincronización de contraseñas deba proporcionar la contraseña anterior.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la configuración del adaptador de sincronización de contraseñas.