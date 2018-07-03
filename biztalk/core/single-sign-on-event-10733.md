---
title: 'De sesión único: Evento 10733 | Microsoft Docs'
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
ms.openlocfilehash: bd392f2a00d3010039501b99f731f1d9c350cdda
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023490"
---
# <a name="single-sign-on-event-10733"></a>De sesión único: Evento 10733
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                  Inicio de sesión único (SSO) empresarial                                                                  |
| Versión del producto |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    Identificador del evento     |                                                                            10733                                                                            |
|  Origen del evento   |                                                                           ENTSSO                                                                            |
|    Componente    |                                                                             N\D                                                                             |
|  Nombre simbólico  |                                                              SSO_WARN_PS_SET_WINDOWS_PASSWORD                                                               |
|  Texto del mensaje   | No se pudo actualizar la contraseña de Windows en la base de datos de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2\\%3 %r<br /><br /> Código de error: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que Sincronización de contraseñas no pudo actualizar la contraseña de cuenta de Windows especificada en la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  

- Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.  

- Compruebe si la contraseña de la cuenta especificada es una contraseña de Windows válida.  

  Para obtener más información, vea los recursos siguientes:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
