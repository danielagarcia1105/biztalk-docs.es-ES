---
title: "Inicio de sesión único: Evento 10705 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81456bdd-dfd8-4483-aa76-5ec72350cc70
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41db0b3aeba4e3c71da3193af807f881bb4ae586
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10705"></a>Inicio de sesión único: Evento 10705
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10705|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PS_NOT_ADAPTER|  
|Texto del mensaje|El adaptador especificado no es una aplicación de adaptador. Compruebe el tipo de aplicación.%r<br /><br /> Adaptador: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que el adaptador especificado no es una aplicación de adaptador.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Use el complemento MMC de administración de SSO, haga clic con el botón secundario en el adaptador especificado y, a continuación, haga clic en Propiedades para determinar el tipo de aplicación o bien, use las herramientas de línea de comandos "ssops -list" y "ssops -display" para determinarlo.  
  
-   Use el complemento MMC de administración de SSO o "ssops -addapp" para establecer la aplicación de adaptador.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)