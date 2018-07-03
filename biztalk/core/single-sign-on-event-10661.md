---
title: 'De sesión único: Evento 10661 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3418f37-770d-4021-9341-5dbe99689da6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b52ec67069951bcda3dee54da96e33ca5145e9e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998861"
---
# <a name="single-sign-on-event-10661"></a>De sesión único: Evento 10661
## <a name="details"></a>Detalles  

|                 |                                                                                     |
|-----------------|-------------------------------------------------------------------------------------|
|  Nombre del producto   |                              Inicio de sesión único (SSO) empresarial                              |
| Versión del producto |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    Identificador del evento     |                                        10661                                        |
|  Origen del evento   |                                       ENTSSO                                        |
|    Componente    |                                         N\D                                         |
|  Nombre simbólico  |                    SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED                     |
|  Texto del mensaje   | No se pudo iniciar la sincronización de contraseñas de Windows (desde PCNS).%r<br /><br /> Código de error: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que no se pudo iniciar la sincronización de contraseñas para Windows.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  

-   Compruebe si en los registros de eventos del sistema y la aplicación existen eventos asociados.  

-   Compruebe las propiedades de configuración del adaptador.  

## <a name="more-info"></a>Más información

- [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)  

- **Ayuda de UI de inicio de sesión único empresarial** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
