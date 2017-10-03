---
title: "Inicio de sesión único: Evento 10524 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55e26da3-f67f-4f87-92e5-2f8765b19989
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c79da37aaa54f44daaa39048fcdf58e67064f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10524"></a>Inicio de sesión único: Evento 10524
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10524|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_RESTORE_SECRET_FAILED|  
|Texto del mensaje|No se pudieron restaurar los secretos principales.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> MSID actual: %2 %r<br /><br /> MSID anterior: %3 %r<br /><br /> El usuario cliente: %4 %r<br /><br /> Código de error: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que un usuario está intentando restaurar los secretos principales desde un archivo de copia de seguridad con error. Esto puede deberse a problemas de permisos (se debe ser un administrador de SSO para restaurar el secreto principal) o es posible que el archivo de copia de seguridad esté dañado. En estos casos, debería haber mensajes relacionados en el registro de eventos de la aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.  
  
-   Compruebe si dispone de los permisos de administrador de SSO correspondientes.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md)  
  
-   [Cómo realizar copias de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md)  
  
-   [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)