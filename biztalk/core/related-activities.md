---
title: Actividades relacionadas con | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], related activities
- Query Builder [BAM portal], related activities
- queries [BAM], related activities
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
ms.assetid: 141b7943-d244-4810-aa88-12aa4a2b7658
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fea95a74a15c685f2cff202fcf7f04c86244041b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="related-activities"></a>Actividades relacionadas
El área Actividades relacionadas contiene una lista de actividades que se relacionan con la actividad en la que se basa la consulta. Un ejemplo de una actividad relacionada para una actividad de pedido de compra serían varias actividades de envío, ya que los artículos de un pedido de compra se pueden entregar en varios envíos.  
  
## <a name="creating-related-activities"></a>Crear actividades relacionadas  
 La lista de actividades relacionadas se genera de una de las dos maneras siguientes:  
  
-   Se definen dos actividades y luego se crea una vista única que incluye las dos. El programador realiza una conexión de correlación entre las dos al implementar la clave, el campo y las relaciones de valor entre las actividades.  
  
-   Se definen dos actividades. El programador realiza una conexión de correlación en su aplicación personalizada llamando a AddRelationship() y definiendo la clave, el campo y las relaciones de valor entre las actividades.  
  
 Definir las relaciones de actividad en cualquiera de estas formas agrega una fila en la \<activityname > _Relationships tabla.  
  
> [!NOTE]
>  solo el primer método de definición de relaciones hace que las actividades relacionadas tengan vínculos activos entre ellas. El segundo método no define una vista de distribución y por tanto, el portal no puede conocer la relación entre las dos actividades.  
  
## <a name="see-also"></a>Vea también  
 [Cómo ver los resultados de una búsqueda de actividad](../core/how-to-view-the-results-of-an-activity-search.md)