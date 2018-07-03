---
title: 'De sesión único: Evento 10725 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89218d73-bda0-4e98-a578-cd244af79041
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 206173f45d6702290eef7cd8e203c2439ce44cc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016142"
---
# <a name="single-sign-on-event-10725"></a>De sesión único: Evento 10725
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                        Inicio de sesión único (SSO) empresarial                                                                                        |
| Versión del producto |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    Identificador del evento     |                                                                                                  10725                                                                                                  |
|  Origen del evento   |                                                                                                 ENTSSO                                                                                                  |
|    Componente    |                                                                                                   N\D                                                                                                   |
|  Nombre simbólico  |                                                                                       SSO_ERROR_REPLAY_SECURITY_3                                                                                       |
|  Texto del mensaje   | La seguridad del directorio de archivos de reproducción no coincide con la seguridad del archivo de reproducción o progreso.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> Seguridad del archivo: %2 %r<br /><br /> Seguridad de directorios: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que la seguridad del directorio de archivos de reproducción no coincide con la seguridad del archivo de reproducción o progreso.  

 Los archivos de reproducción se almacenan en el directorio de archivos de reproducción. De forma predeterminada, la cuenta de servicio SSO se usa para crear tanto archivos de reproducción como el directorio de archivos de reproducción. SSO verifica que no se hayan realizado cambios en la configuración de seguridad de los archivos de reproducción y del directorio de archivos de reproducción desde su creación. Si el directorio de archivos de reproducción se creó con una cuenta diferente, puede aparecer este error cuando la sincronización de contraseñas intenta crear un archivo de reproducción en ese directorio. Se recomienda que los usuarios no cambien la configuración de seguridad de los archivos de reproducción ni del directorio de archivos de reproducción.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe las cuentas que se usan para crear el directorio de archivos de reproducción. Si el directorio está vacío, intente ejecutar nuevamente la sincronización de contraseñas. Es posible que se sea necesario volver a crear el directorio mediante la misma cuenta de servicio que el servicio SSO. Si no puede volver a crear el directorio de archivos de reproducción mediante la misma cuenta que el servicio SSO, compruebe los permisos de esa cuenta.  

  Para obtener más información, vea los recursos siguientes:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
