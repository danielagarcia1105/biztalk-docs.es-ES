---
title: 'Inicio de sesión único: Evento 10545 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64cb10ceef5827f9c0b0aab5d9810db061af8a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270652"
---
# <a name="single-sign-on-event-10545"></a>Inicio de sesión único: Evento 10545
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10545|  
|Origen del evento|ENTSSO|  
|Componente|CO|  
|Nombre simbólico|SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED|  
|Texto del mensaje|No se habilitaron vales para el sistema SSO.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se habilitaron vales para el sistema SSO. Si se deshabilita la concesión de vales en el nivel del sistema, tampoco se podrá usar en el nivel de aplicación afiliada. Es posible habilitar los vales en el nivel de sistema y deshabilitarlos en el nivel de aplicación afiliada.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Habilite los vales en el nivel de sistema SSO.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Vales de SSO](../core/sso-tickets.md)  
  
-   [Cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md)