---
title: "Inicio de sesión único: Evento 10532 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a9d477ec54a3c959f2afdf4c687c65b88523ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10532"></a>Inicio de sesión único: Evento 10532
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10532|  
|Origen del evento|ENTSSO|  
|Componente|CO|  
|Nombre simbólico|SSO_WARN_LOST_SECRET_SERVER|  
|Texto del mensaje|No se pudieron recuperar los secretos principales. Compruebe si el nombre del servidor secreto principal es correcto y está disponible.%r<br /><br /> Nombre del servidor secreto: %1 %r<br /><br /> Código de error: %2|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que la solicitud de obtención del secreto principal generó un error. Es posible que esto se deba a que el servicio Inicio de sesión único empresarial no está en ejecución en el servidor.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.  
  
-   Compruebe si el nombre de servidor secreto principal es correcto.  
  
-   Compruebe si el servidor secreto principal está desconectado y si el servicio Inicio de sesión único empresarial está en ejecución.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  
  
-   [Administrar el secreto principal](../core/managing-the-master-secret.md)