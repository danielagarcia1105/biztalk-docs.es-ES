---
title: 'Inicio de sesión único: Evento 11025 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df5a733b-3c95-409c-8485-bf3f7feb3c50
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1f717a62e74d69adcef248d47d886b7e8b4bfd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276708"
---
# <a name="single-sign-on-event-11025"></a>Inicio de sesión único: Evento 11025
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11025|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_INVALID_APP_TICKET_TIMEOUT|  
|Texto del mensaje|Valor de tiempo de espera de vale no válido para actualización de aplicación.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Tiempo de espera de vale: %2 minutos %r<br /><br /> Tiempo de espera máximo de vale: %3 minutos %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 El valor de tiempo de espera de vale no es válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener más información sobre los tiempos de espera de vale, consulte [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).