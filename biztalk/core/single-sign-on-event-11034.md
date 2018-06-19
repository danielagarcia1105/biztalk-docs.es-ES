---
title: 'Inicio de sesión único: Evento 11034 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 828bc5fb-12ab-4eea-94f2-2434ad0ee033
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c66245fe478dddeb539344503d8658719a604ed5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278220"
---
# <a name="single-sign-on-event-11034"></a>Inicio de sesión único: Evento 11034
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11034|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_INFO_PS_WIN_CHANGE_APP_INCORRECT_TYPE|  
|Texto del mensaje|Cambio de contraseña de Windows. Se detectó una asignación para esta cuenta de Windows pero se la ignoró porque la aplicación no tiene el tipo correcto. Sólo las aplicación del tipo "Individual" o "Grupo" admiten sincronización de contraseñas de Windows.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Aplicación: %3 %r<br /><br /> Cuenta externa: %4 %r<br /><br /> Usuario cliente: %5|  
  
## <a name="explanation"></a>Explicación  
 Sólo las aplicación del tipo "Individual" o "Grupo" admiten sincronización de contraseñas de Windows.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener más información, consulte [Password Synchronization](../core/password-synchronization2.md).