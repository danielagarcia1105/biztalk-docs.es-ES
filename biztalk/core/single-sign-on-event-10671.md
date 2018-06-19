---
title: 'Inicio de sesión único: Evento 10671 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db44ecfd9980db445d3a611e4992f4b3961b3548
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270620"
---
# <a name="single-sign-on-event-10671"></a>Inicio de sesión único: Evento 10671
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10671|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED|  
|Texto del mensaje|El cambio de contraseña de Windows provocará cambios en varias cuentas en el mismo sistema externo.%r<br /><br /> Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 %r<br /><br /> Cuenta externa 1: %4 %r<br /><br /> Cuenta externa 2: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de información indica que el cambio de contraseña de Windows provocará cambios en varias cuentas en el mismo sistema externo.  
  
## <a name="user-action"></a>Acción del usuario  
  
-   No es necesario que el usuario realice ninguna acción.  
  
## <a name="more-info"></a>Más información
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)