---
title: "Inicio de sesión único: Evento 10807 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 882c01c6-70db-4986-9f4b-f08335424250
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e269b22bc8ea2fec013123d515ac04bd3f60d46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10807"></a>Inicio de sesión único: Evento 10807
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10807|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS|  
|Texto del mensaje|Demasiadas notificaciones sin confirmar.|  
  
## <a name="explanation"></a>Explicación  
 Cada vez que se envía una notificación de cambio de contraseña, se recibe un mensaje de confirmación. En este caso, se ha superado el límite de notificaciones sin confirmación.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe el adaptador de sincronización de contraseñas.