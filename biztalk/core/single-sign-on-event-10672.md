---
title: 'Inicio de sesión único: Evento 10672 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2422c7d-51bc-4f12-8830-193d71d2bce9
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03eb6a72be53f928c8c173ac84556f709df0723c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271596"
---
# <a name="single-sign-on-event-10672"></a>Inicio de sesión único: Evento 10672
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10672|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED|  
|Texto del mensaje|El cambio de contraseña de Windows provocaría cambios en varias cuentas en el mismo sistema externo.%r<br /><br /> El cambio se impidió porque el adaptador de este sistema externo está configurado para no permitir conflictos de asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 %r<br /><br /> Cuenta externa 1: %4 %r<br /><br /> Cuenta externa 2: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que el cambio de contraseña de Windows provocaría cambios en varias cuentas en el mismo sistema externo. El cambio se impidió porque la configuración del adaptador no lo permitiría.  
  
## <a name="user-action"></a>Acción del usuario  
  
-   Use las herramientas de administración de SSO para configurar el **Permitir conflictos de asignación** propiedad para el adaptador de sincronización de contraseña.  
  
## <a name="more-info"></a>Más información
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)