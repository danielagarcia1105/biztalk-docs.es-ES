---
title: "Inicio de sesión único: Evento 10661 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3418f37-770d-4021-9341-5dbe99689da6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fdc655a87975a89387d84e2aefdd07a603c0ed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10661"></a>Inicio de sesión único: Evento 10661
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10661|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED|  
|Texto del mensaje|No se pudo iniciar la sincronización de contraseñas de Windows (desde PCNS).%r<br /><br /> Código de error: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que no se pudo iniciar la sincronización de contraseñas para Windows.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Compruebe si en los registros de eventos del sistema y la aplicación existen eventos asociados.  
  
-   Compruebe las propiedades de configuración del adaptador.  
  
## <a name="more-info"></a>Más información
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)  
  
-   **Ayuda UI de inicio de sesión único empresarial**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]