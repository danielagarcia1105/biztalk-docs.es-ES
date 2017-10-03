---
title: "Inicio de sesión único: Evento 10728 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f579189c-c9a5-4d2c-a3d5-f0ba03c5a3ef
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5052d03713808754abf04e8c2ba1590800e6cf9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10728"></a>Inicio de sesión único: Evento 10728
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10728|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_VERSION|  
|Texto del mensaje|Esta versión de servidor de SSO no es compatible con la base de datos de SSO. Actualice el servidor secreto principal.%r<br /><br /> Nombre SQL Server: %1 %r<br /><br /> Nombre de la base de datos SSO: %2 %r<br /><br /> Versión de la base de datos SSO: %3 %r<br /><br /> Versión requerida: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que la versión de servidor de SSO es más reciente que la base de datos de SSO (versión que la creó originalmente).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Actualice el servidor secreto principal de SSO para que coincida con la versión actual de este servidor de SSO. De este modo, se actualizará la base de datos de SSO a la versión actual.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Administrar el secreto principal](../core/managing-the-master-secret.md)