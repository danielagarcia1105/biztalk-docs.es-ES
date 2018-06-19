---
title: 'Inicio de sesión único: Evento 10544 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c79e2186-1c75-4e7b-8bf5-f582e5c2aac7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1a01cda4272e2851f929c35fd2b767c321a9dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270580"
---
# <a name="single-sign-on-event-10544"></a>Inicio de sesión único: Evento 10544
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10544|  
|Origen del evento|ENTSSO|  
|Componente|CO|  
|Nombre simbólico|SSO_WARN_TICKET_EXPIRED|  
|Texto del mensaje|Vale caducado.%r<br /><br /> Nombre de la aplicación: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que el tiempo de espera de vale de aplicación ha caducado. El tiempo de espera de vale se puede especificar tanto en el nivel de sistema como en el de aplicación. Si se especifica el tiempo de espera de ambos niveles, se usa el tiempo de espera del nivel de aplicación para determinar el tiempo de caducidad.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Determine por qué caducó el vale antes de su validación.  
  
-   Asegúrese de que el valor de tiempo de espera de vale es lo suficientemente largo para que finalice entre la hora de emisión del vale y la hora de su canje.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Vales de SSO](../core/sso-tickets.md)  
  
-   [Cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md)