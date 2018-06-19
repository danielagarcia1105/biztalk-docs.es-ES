---
title: 'Inicio de sesión único: Evento 11062 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c7c2ea-c671-4853-ac64-8cb80bba98b0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b695b98e556d9fa23f07ee7af6602bb1ad845eb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276468"
---
# <a name="single-sign-on-event-11062"></a>Inicio de sesión único: Evento 11062
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11062|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_PASSWORD_FILTER_FAILED|  
|Texto del mensaje|Error al filtrar la contraseña. No se usará filtro de contraseña.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Cadena de filtro de contraseña: %2 %r<br /><br /> Datos adicionales: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Se produjo un error al crear un filtro de contraseña y, por lo tanto, éste no se creó.  
  
## <a name="user-action"></a>Acción del usuario  
 Para crear el filtro de contraseñas mediante el Asistente para crear un filtro de contraseña, consulte [cómo usar filtros de contraseña](../core/how-to-use-password-filters.md).