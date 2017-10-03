---
title: "Inicio de sesión único: Evento 10676 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec0e86fb-921d-4505-b458-51b565123ea7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3805e59e5e8984652ec40af9f93db793d5d3b5fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10676"></a>Inicio de sesión único: Evento 10676
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10676|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_REQUIRE_OLD_PASSWORD|  
|Texto del mensaje|Cambio de contraseña externa. Al cambiar la contraseña de una cuenta externa, el adaptador debe proporcionar la contraseña anterior.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que el adaptador de sincronización de contraseñas se configuró para esperar una contraseña anterior del sistema externo, pero no se proporcionó tal contraseña. El sistema externo (el adaptador de sincronización de contraseñas externas) no está configurado o no funciona como se previó o bien, la configuración del adaptador de sincronización de contraseñas es incorrecta. Este error también puede devolver el código de error con nombre simbólico ENTSSO_E_REQUIRE_OLD_PASSWORD.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Use las herramientas de administración de SSO para establecer la propiedad configurable de usuario **comprobar contraseña antigua** en la ficha de propiedades Opciones de adaptador de sincronización de contraseña. Esta propiedad también puede establecerse durante la creación de adaptadores a través de las herramientas de línea de comandos (ssops.exe) con el nombre de marcador `verifyOldPassword` y durante la creación de un nuevo adaptador de sincronización de contraseñas mediante el Asistente para adaptador de sincronización de contraseñas.  
  
## <a name="more-info"></a>Más información
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)  
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]