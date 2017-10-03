---
title: "Inicio de sesión único: Evento 10658 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5bee12d-502b-4fee-bc84-25807eb0e48e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9594f2462422190c243d98c165ead37898e33f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10658"></a>Inicio de sesión único: Evento 10658
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10658|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED|  
|Texto del mensaje|No se pudo iniciar la sincronización para contraseñas de adaptadores externos.%r<br /><br /> Código de error: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que no se pudo iniciar la sincronización de contraseñas para adaptadores externos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Compruebe si en los registros de eventos del sistema y la aplicación existen eventos asociados.  
  
-   Compruebe las propiedades de configuración del adaptador.  

## <a name="more-info"></a>Más información  
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)  
  
-   **Ayuda UI de inicio de sesión único empresarial**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]