---
title: 'Inicio de sesión único: Evento 10674 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad0c0d9e-1e6d-4c3e-86e0-9e336a18f3d6
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d239353276657e85c7fbdcfa634c3c1268723724
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270932"
---
# <a name="single-sign-on-event-10674"></a>Inicio de sesión único: Evento 10674
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10674|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED|  
|Texto del mensaje|El cambio de contraseña externa habría provocado cambios en varias cuentas de Windows.%r<br /><br /> El cambio se impidió porque el adaptador de este sistema externo está configurado para no permitir conflictos de asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3 %r<br /><br /> Cuenta de Windows 1: %4 %r<br /><br /> Cuenta de Windows 2: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que el cambio de contraseña externa habría provocado cambios en varias cuentas de Windows. El cambio se impidió porque la configuración del adaptador no lo permitiría.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Si se espera conflictos de asignación y se permiten, use las herramientas de administración de SSO para configurar el **Permitir conflictos de asignación** propiedad para el adaptador de sincronización de contraseña.  
  
## <a name="more-info"></a>Más información
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)