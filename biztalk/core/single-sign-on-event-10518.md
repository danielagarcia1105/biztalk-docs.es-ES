---
title: "Inicio de sesión único: Evento 10518 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 274e29f9-1933-4e40-83c0-2e84c6708315
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27b82d7f0a6bbaf02400679add53851867d728c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10518"></a>Inicio de sesión único: Evento 10518
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10518|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_BAD_USER_GROUP|  
|Texto del mensaje|Cuenta de usuarios de aplicación no válida para esta aplicación. Si se trata de una cuenta local, compruebe si existe en el servidor. Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio. Habilite la aplicación cuando la cuenta sea válida. Puede ignorar este mensaje si no usará esta aplicación en este equipo.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Usuarios de aplicación: %2 %r<br /><br /> Cuentas no válidas: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que una cuenta de grupo de usuarios de aplicación no es una cuenta de Windows válida. Hay un grupo de cuentas de usuarios de la aplicación para cada aplicación afiliada.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Compruebe si existe la cuenta de usuarios de aplicación.  
  
-   Use la utilidad de administración de SSO para comprobar si la aplicación afiliada especificada está configurada para usar la cuenta de usuarios de aplicación adecuada.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Grupos de usuarios SSO](../core/sso-user-groups.md)  
  
-   [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)  
  
-   [Cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md)