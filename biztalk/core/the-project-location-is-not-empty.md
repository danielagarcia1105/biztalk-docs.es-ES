---
title: La ubicación del proyecto no está vacía | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db353050-3662-4ab6-8898-4e4d3bd78ac1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fc106b534973f13544b9bafa85f190d8ed2c255
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994293"
---
# <a name="the-project-location-is-not-empty"></a>La ubicación del proyecto no está vacía
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                 |
| Versión del producto |                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                             |
|    Identificador del evento     |                                                                                                                         0                                                                                                                          |
|  Origen del evento   |                                                                                                                         0                                                                                                                          |
|    Componente    |                                                                                                                         0                                                                                                                          |
|  Nombre simbólico  |                                                                                                                         0                                                                                                                          |
|  Texto del mensaje   | La ubicación del proyecto "{0}" no está vacío. Deberá hacer lo siguiente: 1. Elija una ubicación diferente para el nuevo proyecto, 2. Especificar sobrescribir para volver a usar la ubicación existente o 3. Elimine manualmente el contenido de la ubicación del proyecto. |
  
## <a name="explanation"></a>Explicación  
 Este error indica que el directorio virtual donde se intenta publicar el servicio no está vacío.  
  
## <a name="user-action"></a>Acción del usuario  
 Seleccione la ubicación de sobrescritura para volver a usar la misma ubicación. O bien especifique una nueva ubicación.  En el Asistente de publicación de servicio de WCF, seleccione **sobrescribir la ubicación existente** y haga clic en **siguiente**. Este paso sobrescribe la ubicación.