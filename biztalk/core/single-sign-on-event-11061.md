---
title: "Inicio de sesión único: Evento 11061 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52fb18e2-4482-4cdb-b8ed-d579a95acd7c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e86ad25248952697e27fc732ddead6732065acf7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11061"></a>Inicio de sesión único: Evento 11061
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11061|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_BAD_PASSWORD_FILTER|  
|Texto del mensaje|Cadena de filtro de contraseña no válida. No se usará filtro de contraseña.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Cadena de filtro de contraseña: %2 %r<br /><br /> Número de Tokens procesados: %3 %r<br /><br /> Datos adicionales: %4 %r<br /><br /> Código de error: %5|  
  
## <a name="explanation"></a>Explicación  
 Se creó manualmente un filtro de contraseña no válido. En algún momento de este proceso se generó un error (consulte la cadena de filtro de contraseña en el texto de la advertencia para conocer la ubicación del error).  
  
## <a name="user-action"></a>Acción del usuario  
 Para crear el filtro de contraseñas mediante el Asistente para crear un filtro de contraseña, consulte [cómo usar filtros de contraseña](../core/how-to-use-password-filters.md).