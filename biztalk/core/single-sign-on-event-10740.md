---
title: "Inicio de sesión único: Evento 10740 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928760bebef1119207ee6a3021cd39c22ceacad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10740"></a>Inicio de sesión único: Evento 10740
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10740|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_INVALID_WINDOWS_USER|  
|Texto del mensaje|Cuenta de Windows no válida para actualización de la aplicación.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Código de error: %3|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que la cuenta de Windows (especificada en el mensaje de evento) no es válida para la actualización de la aplicación. Esto puede ocurrir cuando se cambia la cuenta de Windows de una aplicación de grupo host. Las aplicaciones de grupo host se usan para inicio de sesión único desde sistemas externos en sistemas de Windows. Estas aplicaciones pueden asignar un conjunto de usuarios externos a una única cuenta de Windows. La cuenta de Windows a la que se asignan se define en el campo de usuarios de aplicación de la aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Compruebe si la cuenta de Windows que se usa es válida.  
  
-   Vuelva a crear la cuenta de Windows con las propiedades correctas de cuenta de Windows.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)