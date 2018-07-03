---
title: 'De sesión único: Evento 10717 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7beabfc76ce1c5ab72ac577be2dfbe549b35a4a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004533"
---
# <a name="single-sign-on-event-10717"></a>De sesión único: Evento 10717
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                            Inicio de sesión único (SSO) empresarial                                                             |
| Versión del producto |                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                            |
|    Identificador del evento     |                                                                      10717                                                                       |
|  Origen del evento   |                                                                      ENTSSO                                                                      |
|    Componente    |                                                                       N\D                                                                        |
|  Nombre simbólico  |                                                         SSO_ERROR_NEW_REPLAY_DIR_FAILED                                                          |
|  Texto del mensaje   | No se pudo crear el directorio de archivos de reproducción.%r<br /><br /> Usuario cliente: %1 %r<br /><br /> Directorio de archivos de reproducción: %2 %r<br /><br /> Código de error: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que no se pudo crear el directorio de archivos de reproducción.  

 Cuando el servicio SSO recibe cambios de contraseña provenientes de un adaptador de sincronización de contraseñas, tales cambios se almacenan en la base de datos de SSO. Si esta base de datos no está disponible temporalmente, los cambios de contraseña se almacenan de forma local en archivos de reproducción. Los archivos de reproducción se almacenan en el directorio de archivos de reproducción.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe el directorio de archivos de reproducción. Si no existe uno, intente crearlo de forma manual mediante la misma cuenta de servicio que el servicio SSO. Si no puede crear un directorio de archivos de reproducción mediante la misma cuenta que el servicio SSO, compruebe los permisos de esa cuenta.  

  Para obtener más información, vea los recursos siguientes:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
