---
title: 'Inicio de sesión único: Evento 10516 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d20df92f-c995-4cbc-a8f9-21cea30b82c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b74ca4a47bc62d28b25564bd5843729c56362
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269900"
---
# <a name="single-sign-on-event-10516"></a>Inicio de sesión único: Evento 10516
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10516|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_BAD_SSO_APP_ADMIN|  
|Texto del mensaje|Cuenta de administradores afiliados de SSO no válida. Si se trata de una cuenta local, compruebe si existe en el servidor. Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio. Cuando la cuenta sea válida, habilite SSO.%r<br /><br /> Administradores afiliados de SSO: %1 %r<br /><br /> Cuentas no válidas: %2 %r<br /><br /> Código de error: %3|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que el grupo o la cuenta de administradores afiliados de SSO creada por el inicio de sesión único empresarial no es una cuenta de Windows válida. La cuenta de administradores afiliados de SSO puede ser una cuenta de grupo de Windows o una cuenta individual. La cuenta de administradores afiliados de SSO también puede ser una cuenta de grupo local o de dominio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Compruebe si existe la cuenta de administradores afiliados de SSO.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Grupos de usuarios SSO](../core/sso-user-groups.md)  
  
-   [Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md)