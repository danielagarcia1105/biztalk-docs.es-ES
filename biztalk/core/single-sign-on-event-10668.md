---
title: 'De sesión único: Evento 10668 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7a3efa9ba3e9ccae3cdc39c4549a4625e5d872
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974005"
---
# <a name="single-sign-on-event-10668"></a>De sesión único: Evento 10668
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                                   Inicio de sesión único (SSO) empresarial                                                                                                                                                   |
| Versión del producto |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    Identificador del evento     |                                                                                                                                                             10668                                                                                                                                                             |
|  Origen del evento   |                                                                                                                                                            ENTSSO                                                                                                                                                             |
|    Componente    |                                                                                                                                                              N\D                                                                                                                                                              |
|  Nombre simbólico  |                                                                                                                                               SSO_WARN_NO_OLD_WINDOWS_PASSWORD                                                                                                                                                |
|  Texto del mensaje   | No se puede cambiar la contraseña de Windows porque la contraseña anterior de Windows para esta cuenta no está disponible en la base de datos de SSO.%r<br /><br /> Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que Sincronización de contraseñas no puede cambiar la contraseña de Windows porque la contraseña anterior de Windows para esta cuenta no está disponible en la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

-   Determine qué aplicaciones se asignaron a este adaptador (nombre en el mensaje de registro de eventos) y, a continuación, use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows. Debe establecer la contraseña externa (para la cuenta de Windows especificada) en todas esas aplicaciones.  

## <a name="more-info"></a>Más información

- [Sincronización de contraseñas](../core/password-synchronization2.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
