---
title: "Acerca de la búsqueda de metadatos y exploración con el adaptador de SDK de adaptador LOB de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1dc529ba-86ce-4f83-a4f8-73f5765308e2
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1804425c48fe3a2613cf924aab968cb0a08303ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-metadata-search-and-browse-with-your-wcf-lob-adapter-sdk-adapter"></a>Acerca de la búsqueda de metadatos y exploración con el adaptador de SDK de adaptador LOB de WCF
A diferencia de un servicio estático compilado con la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], adaptadores generada mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] puede proporcionar información dinámica sobre los tipos y las operaciones disponibles en un sistema de línea de negocio. Los desarrolladores pueden admitir las operaciones siguientes:  
  
-   **Examinar metadatos**, permitir que el usuario revisar una lista de todas las operaciones y los tipos disponibles en el sistema de línea de negocio.  
  
-   **Búsqueda de metadatos**, permitir que el usuario buscar operaciones con distintos criterios que se suele basadas en la línea de sistema de negocio. Por ejemplo, podría buscar el usuario en "* CUST\*" para recuperar todas las operaciones que tienen "CUST" en cualquier lugar en su nombre.  
  
-   **Recuperación de metadatos**, lo que proporciona información acerca de una lista específica de tipos de datos o las operaciones compatibles.  
  
 Si la línea de sistema de negocio contiene cientos o miles de operaciones, que proporciona la capacidad de búsqueda para las operaciones concretas o examinar algunos grupos de información puede mejorar la experiencia del usuario.  
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF](plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)