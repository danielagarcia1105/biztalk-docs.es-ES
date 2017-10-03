---
title: "Inicio de sesión único: Evento 11069 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1accfe68-000c-4b5e-909c-244e18eba110
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66f89a1d273b0ed621cd3b59526714d9cb167bfb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11069"></a>Inicio de sesión único: Evento 11069
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11069|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_PS_PCNS_NOT_ALLOWED|  
|Texto del mensaje|Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde PCNS. Use 'ssoconfig -allowPS PCNS yes' o la MMC de administración de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Usuario cliente: %2|  
  
## <a name="explanation"></a>Explicación  
 Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde PCNS.  
  
## <a name="user-action"></a>Acción del usuario  
 Para permitir cambios de contraseña de Windows desde PCNS, en la **complemento de servidores**, **propiedades de sincronización de contraseña** ficha, seleccione **Permitir sincronización de contraseñas desde PCNS.**  
  
 Para obtener más información, consulte [cómo utilizar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).