---
title: 'De sesión único: Evento 10536 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d493a45b-c4ed-40fc-8803-b3ca12f9795b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49687739fced504c9dccc06969c9eb3e10d9aae4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016134"
---
# <a name="single-sign-on-event-10536"></a>De sesión único: Evento 10536
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                     Inicio de sesión único (SSO) empresarial                                                                                      |
| Versión del producto |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    Identificador del evento     |                                                                                               10536                                                                                                |
|  Origen del evento   |                                                                                               ENTSSO                                                                                               |
|    Componente    |                                                                                                 CO                                                                                                 |
|  Nombre simbólico  |                                                                                         SSO_WARN_API_AUDIT                                                                                         |
|  Texto del mensaje   | AUDITORÍA DE SSO%r<br /><br /> Función: %1 %r<br /><br /> Id. de seguimiento: %2 %r<br /><br /> Equipo cliente: %3 %r<br /><br /> Usuario cliente: %4 %r<br /><br /> Nombre de la aplicación: %5 %r<br /><br /> Código de error: %6 |

## <a name="explanation"></a>Explicación  
 Este evento de auditoría de advertencia indica que se produjo un evento que cumple con el nivel de auditoría definido por el usuario. Este mensaje de evento incluye:  

 **Función:** realizando (función)  

 **Id. de seguimiento:** GUID único generado de la primera vez que una API de inicio de sesión único se denomina.  

 **Equipo cliente:** equipo cliente donde se originó la función.  

 **Usuario del cliente:** el nombre de la cuenta de usuario que invocó la función.  

 **Nombre de la aplicación:** nombre de SSO afiliadas aplicación asociada a esta función.  

 **Código de error:** identificador único de error.  

 Este tipo de evento se usa para diagnosticar problemas durante el desarrollo, la solución de problemas o la ejecución de una aplicación. La información proporcionada se puede usar para determinar la llamada de API de SSO que se realiza.  

 El nivel de auditoría se puede establecer en 0/1/2/3, donde 0 significa "ninguno", 1 significa "bajo" (muestra errores solamente), 2 significa "medio" (muestra errores y advertencias) y 3 significa "alto" (muestra todos los mensajes de auditoría).  

## <a name="user-action"></a>Acción del usuario  

- Compruebe si el registro de eventos contiene mensajes de evento asociados.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo auditar el inicio de sesión único](../core/how-to-audit-sso.md)  

- [Uso de SSO](../core/using-sso.md)
