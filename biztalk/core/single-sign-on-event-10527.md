---
title: "Inicio de sesión único: Evento 10527 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf1785361ad343b3da4c7dc07b6a73a362fa14d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10527"></a>Inicio de sesión único: Evento 10527
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10527|  
|Origen del evento|ENTSSO|  
|Componente|0|  
|Nombre simbólico|SSO_ERROR_GET_SECRET_FAILED|  
|Texto del mensaje|Error de solicitud de obtención de secreto principal.%r<br /><br /> Número secreto: %1 %r<br /><br /> El usuario cliente: %2 %r<br /><br /> Equipo cliente: %3 %r<br /><br /> Id. de seguimiento: %4 %r<br /><br /> Código de error: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que la solicitud de obtención del secreto principal generó un error. En estos casos, debería haber mensajes relacionados en el registro de eventos de la aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  
  
-   [Administrar el secreto principal](../core/managing-the-master-secret.md)