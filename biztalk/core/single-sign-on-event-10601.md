---
title: 'Inicio de sesión único: Evento 10601 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34711cf02711ec0ee2a259cc7d8f8fca9c87b7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270708"
---
# <a name="single-sign-on-event-10601"></a>Inicio de sesión único: Evento 10601
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10601|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_INVALID_FLAGS|  
|Texto del mensaje|Marcadores no válidos para crear este tipo de aplicación.<br /><br /> Consulte la documentación de details.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Los indicadores especificados: %2 %r<br /><br /> Marcadores permitidos: %3 %r<br /><br /> Marcadores no permitidos: %4|  
  
## <a name="explanation"></a>Explicación  
 Marcadores no válidos para crear este tipo de aplicación. La advertencia enumera la aplicación específica, además de los marcadores permitidos y no permitidos.  
  
## <a name="user-action"></a>Acción del usuario  
 Vuelva a crear la aplicación respetando las pautas descritas en el mensaje de advertencia.