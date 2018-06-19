---
title: 'Inicio de sesión único: Evento 11022 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c65ca12b-dda8-408b-9512-39df6f8e035b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccae36e9beef672e6c5fb7917c88341ce4bb3c08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276996"
---
# <a name="single-sign-on-event-11022"></a>Inicio de sesión único: Evento 11022
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11022|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED|  
|Texto del mensaje|El cambio de contraseña externa habría provocado el cambio de una cuenta externa diferente.%r<br /><br /> El cambio se impidió porque el adaptador de este sistema externo está configurado para no permitir conflictos de asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 %r<br /><br /> Cuenta externa 1: %4 %r<br /><br /> Cuenta externa 2: %5|  
  
## <a name="explanation"></a>Explicación  
 Este mensaje de información notifica el error de cambio de contraseña externa que habría provocado el cambio de una cuenta externa diferente.  
  
## <a name="user-action"></a>Acción del usuario  
 Si bien el cambio no se llevó a cabo (porque el sistema está configurado para no permitir conflictos de asignación), debe confirmar de inmediato que este intento se realizó con su conocimiento y autorización. Si es así, no se necesitan acciones. De lo contrario, averigüe dónde se inició el cambio y confirme que se trata de una ubicación segura del sistema.