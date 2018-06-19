---
title: 'Inicio de sesión único: Evento 11036 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dad0427-83dd-42ac-b0bc-d113abdc8e89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63b11005248471c222f63c88439a0e60571b341e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277156"
---
# <a name="single-sign-on-event-11036"></a>Inicio de sesión único: Evento 11036
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11036|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC|  
|Texto del mensaje|Cambio de contraseña de Windows. Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque el adaptador configurado para esta aplicación no admite sincronización de contraseñas para sistemas externos.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Aplicación: %3 %r<br /><br /> Adaptador: %4 %r<br /><br /> Usuario cliente: %5|  
  
## <a name="explanation"></a>Explicación  
 Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque el adaptador configurado para esta aplicación no admite sincronización de contraseñas para sistemas externos.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la configuración del adaptador.  
  
 Para obtener información sobre la sincronización de contraseñas, consulte [Password Synchronization](../core/password-synchronization2.md).