---
title: 'Inicio de sesión único: Evento 10535 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b570b0b-5c45-4be3-80c9-a2c50601b677
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3f96032c8176a251090453e493487a97d9cf0fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270084"
---
# <a name="single-sign-on-event-10535"></a>Inicio de sesión único: Evento 10535
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10535|  
|Origen del evento|ENTSSO|  
|Componente|CO|  
|Nombre simbólico|SSO_INFO_API_AUDIT|  
|Texto del mensaje|AUDITORÍA DE SSO%r<br /><br /> Función: %1 %r<br /><br /> Id. de seguimiento: %2 %r<br /><br /> Equipo cliente: %3 %r<br /><br /> El usuario cliente: %4 %r<br /><br /> Nombre de la aplicación: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de auditoría de información indica que se produjo un evento que cumple con el nivel de auditoría definido por el usuario. Este mensaje de evento incluye:  
  
 **Función:** que se está realizando (función)  
  
 **Id. de seguimiento:** llama GUID único generado cuando una API de SSO es el primera.  
  
 **Equipo cliente:** equipo cliente donde se originó la función.  
  
 **El usuario cliente:** el nombre de la cuenta de usuario que invoca la función.  
  
 **Nombre de la aplicación:** nombre de SSO afiliadas aplicación asociada a esta función.  
  
 Este tipo de evento se usa para diagnosticar problemas durante el desarrollo, la solución de problemas o la ejecución de una aplicación. La información proporcionada se puede usar para determinar la llamada de API de SSO que se realiza.  
  
 El nivel de auditoría se puede establecer en 0/1/2/3, donde 0 significa "ninguno", 1 significa "bajo" (muestra errores solamente), 2 significa "medio" (muestra errores y advertencias) y 3 significa "alto" (muestra todos los mensajes de auditoría).  
  
## <a name="user-action"></a>Acción del usuario  
  
-   Compruebe si el registro de eventos contiene mensajes de evento asociados.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo auditar SSO](../core/how-to-audit-sso.md)  
  
-   [Uso de SSO](../core/using-sso.md)