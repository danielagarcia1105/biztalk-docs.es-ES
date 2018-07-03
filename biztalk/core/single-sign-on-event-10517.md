---
title: 'De sesión único: Evento 10517 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c1426b4a45d55985ace0548b8e33bb2637f09c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011405"
---
# <a name="single-sign-on-event-10517"></a>De sesión único: Evento 10517
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                                  Inicio de sesión único (SSO) empresarial                                                                                                                                                  |
| Versión del producto |                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                  |
|    Identificador del evento     |                                                                                                                                                            10517                                                                                                                                                            |
|  Origen del evento   |                                                                                                                                                           ENTSSO                                                                                                                                                            |
|    Componente    |                                                                                                                                                             N\D                                                                                                                                                             |
|  Nombre simbólico  |                                                                                                                                                   SSO_ERROR_BAD_SSO_ADMIN                                                                                                                                                   |
|  Texto del mensaje   | Cuenta de administradores de SSO no válida. Si se trata de una cuenta local, compruebe si existe en el servidor. Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio. Cuando la cuenta sea válida, habilite SSO.%r<br /><br /> Administradores de SSO: %1 %r<br /><br /> Cuentas no válidas: %2 %r<br /><br /> Código de error: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que la cuenta de administradores de SSO especificada para el inicio de sesión único empresarial no es una cuenta de Windows válida. La cuenta de servicio que ejecute el inicio de sesión único (SSO) empresarial deberá ser miembro de esta cuenta. La cuenta de administradores de SSO puede ser una cuenta de grupo de Windows o una cuenta individual. La cuenta de administradores de SSO también puede ser una cuenta de grupo local o de dominio. Si se utiliza una cuenta individual, no se podrá cambiar esta cuenta por otra cuenta individual.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si existe la cuenta de administradores de SSO.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Grupos de usuarios de SSO](../core/sso-user-groups.md)
