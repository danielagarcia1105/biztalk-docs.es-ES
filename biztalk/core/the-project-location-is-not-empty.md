---
title: "La ubicación del proyecto no está vacía | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db353050-3662-4ab6-8898-4e4d3bd78ac1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de1e1dd381a75f596b4980430ddcc5d6d8982b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-project-location-is-not-empty"></a>La ubicación del proyecto no está vacía
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|La ubicación del proyecto "{0}" no está vacía. Debe llevar a cabo una de las siguientes acciones: 1. Elija una ubicación diferente para el nuevo proyecto, 2. Especificar sobrescribir para volver a usar la ubicación existente, o 3. Elimine manualmente el contenido de la ubicación del proyecto.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el directorio virtual donde se intenta publicar el servicio no está vacío.  
  
## <a name="user-action"></a>Acción del usuario  
 Seleccione la ubicación de sobrescritura para volver a usar la misma ubicación. O bien especifique una nueva ubicación.  En el Asistente de publicación de servicio de WCF, seleccione **sobrescribir la ubicación existente** y haga clic en **siguiente**. Este paso sobrescribe la ubicación.