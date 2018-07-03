---
title: 'De sesión único: Evento 10669 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e88a583d-7385-42dd-841e-aa2d2215dd69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3006b8c861ac56effa504480f2645f22f9deae8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019272"
---
# <a name="single-sign-on-event-10669"></a>De sesión único: Evento 10669
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                   Inicio de sesión único (SSO) empresarial                                                                   |
| Versión del producto |                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    Identificador del evento     |                                                                             10669                                                                             |
|  Origen del evento   |                                                                            ENTSSO                                                                             |
|    Componente    |                                                                              N\D                                                                              |
|  Nombre simbólico  |                                                            SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED                                                            |
|  Texto del mensaje   | No se pudo cambiar la contraseña de Windows.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 %r<br /><br /> Código de error: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que SSO no pudo cambiar la contraseña de Windows. SSO llama a la función NetUserChangePassword de Win32 para que cambie la contraseña de Windows asociada con la asignación. Si la función genera error, se emite este mensaje de error. El código de error será el que devuelva la función NetUserChangePassword. Para obtener información detallada, consulte la documentación de esta función en MSDN. Las causas más probables del error son que la contraseña anterior era incorrecta o que la contraseña nueva no respeta la directiva de contraseñas de Windows.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  

- Compruebe la contraseña anterior. Si esta contraseña es incorrecta, se puede establecer manualmente en la base de datos de SSO a través de las herramientas de línea de comandos o MMC de administración.  

- Compruebe si la contraseña nueva respeta la directiva de contraseñas de Windows requerida. Si no es así, considere la posibilidad de usar filtros de contraseña.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
