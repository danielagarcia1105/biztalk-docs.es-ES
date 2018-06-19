---
title: 'Inicio de sesión único: Evento 10733 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1387d7c853bba91bea429470d9a615e065a6e8dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271532"
---
# <a name="single-sign-on-event-10733"></a>Inicio de sesión único: Evento 10733
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10733|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PS_SET_WINDOWS_PASSWORD|  
|Texto del mensaje|No se pudo actualizar la contraseña de Windows en la base de datos de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2\\%3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que Sincronización de contraseñas no pudo actualizar la contraseña de cuenta de Windows especificada en la base de datos de SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.  
  
-   Compruebe si la contraseña de la cuenta especificada es una contraseña de Windows válida.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)