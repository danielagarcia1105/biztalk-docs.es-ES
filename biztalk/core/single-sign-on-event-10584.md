---
title: 'Inicio de sesión único: Evento 10584 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9377d-b4fd-48a6-961a-3629b3db644a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d08be0100d53f081eb7d8f4faa27d1e7f46f6f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270372"
---
# <a name="single-sign-on-event-10584"></a>Inicio de sesión único: Evento 10584
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10584|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_NO_IMPERSONATION|  
|Texto del mensaje|No se pudo suplantar al cliente.%r<br /><br /> Código de error: %1|  
  
## <a name="explanation"></a>Explicación  
 El sistema ENTSSO no verifica la identidad del cliente durante su suplantación. Si el sistema no puede suplantar un cliente, puede deberse a una de las tres causas siguientes: el cliente puede estar intentando realizar una actividad habitual, el cliente puede estar intentando infiltrarse en la seguridad del sistema o la aplicación cliente pude estar diseñada para bloquear la suplantación.  
  
## <a name="user-action"></a>Acción del usuario  
 Busque la aplicación cliente, determine qué está intentando realizar y si está o no bloqueando la suplantación.