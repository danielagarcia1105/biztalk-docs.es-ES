---
title: 'Inicio de sesión único: Evento 11014 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 138a580122beb34b82f642dfa4d60aa6d422b445
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276516"
---
# <a name="single-sign-on-event-11014"></a>Inicio de sesión único: Evento 11014
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11014|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_ACCESS_CHECK|  
|Texto del mensaje|Error al comprobar el acceso.%r<br /><br /> El usuario cliente: %1\\%2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Datos adicionales: %4 %r<br /><br /> Código de error: %5|  
  
## <a name="explanation"></a>Explicación  
 Se produjo un error al comprobar el acceso para el cliente y la aplicación enumerados.  
  
## <a name="user-action"></a>Acción del usuario  
 La información adicional debe permitirle solucionar el problema. Para evitar este error en el futuro, también puede reducir el nivel de auditoría.