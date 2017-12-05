---
title: "Elemento raíz inesperado. | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecccf57e-9295-4a6d-95b6-efec662478cf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4ed8e39a05f81984dca21794eca3d829ba8f42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="unexpected-root-element"></a>Elemento raíz inesperado.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Elemento raíz inesperado.|  
  
## <a name="explanation"></a>Explicación  
 Propiedad de encabezado no está en \<encabezados\>...\</headers\> formato. Normalmente esta situación se aplica a InboundHeaders y OutboundCustomHeaders.  
  
## <a name="user-action"></a>Acción del usuario  
 Asegúrese de que es propiedad de encabezado en el formato de \<encabezados\>... \</headers\>.