---
title: Actividades relacionadas con | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], related activities
- Query Builder [BAM portal], related activities
- queries [BAM], related activities
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
ms.assetid: 141b7943-d244-4810-aa88-12aa4a2b7658
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f50e4de965e8f1efaa1454bb9123317ae904f7e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971858"
---
# <a name="related-activities"></a>Actividades relacionadas
El área Actividades relacionadas contiene una lista de actividades que se relacionan con la actividad en la que se basa la consulta. Un ejemplo de una actividad relacionada para una actividad de pedido de compra serían varias actividades de envío, ya que los artículos de un pedido de compra se pueden entregar en varios envíos.  
  
## <a name="creating-related-activities"></a>Crear actividades relacionadas  
 La lista de actividades relacionadas se genera de una de las dos maneras siguientes:  
  
-   Se definen dos actividades y luego se crea una vista única que incluye las dos. El programador realiza una conexión de correlación entre las dos al implementar la clave, el campo y las relaciones de valor entre las actividades.  
  
-   Se definen dos actividades. El programador realiza una conexión de correlación en su aplicación personalizada llamando a AddRelationship() y definiendo la clave, el campo y las relaciones de valor entre las actividades.  
  
 Definir las relaciones de actividad en cualquiera de estas formas agrega una fila en la \<activityname\>tabla _Relationships.  
  
> [!NOTE]
>  solo el primer método de definición de relaciones hace que las actividades relacionadas tengan vínculos activos entre ellas. El segundo método no define una vista de distribución y por tanto, el portal no puede conocer la relación entre las dos actividades.  
  
## <a name="see-also"></a>Vea también  
 [Cómo ver los resultados de una búsqueda de actividad](../core/how-to-view-the-results-of-an-activity-search.md)