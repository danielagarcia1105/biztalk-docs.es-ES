---
title: Acerca de la búsqueda de metadatos y examinar con el adaptador de SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1dc529ba-86ce-4f83-a4f8-73f5765308e2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 215199bec64562a302c9550bc5526a8758e4843a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983437"
---
# <a name="about-metadata-search-and-browse-with-your-wcf-lob-adapter-sdk-adapter"></a>Acerca de la búsqueda de metadatos y examinar con el adaptador de SDK de adaptador LOB de WCF
A diferencia de un servicio estático creado mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], adaptadores generada mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] puede proporcionar información dinámica sobre los tipos y las operaciones disponibles en un sistema de línea de negocio. Los desarrolladores pueden admitir las operaciones siguientes:  
  
- **Exploración de metadatos**, permitir que el usuario revisar una lista de todas las operaciones y los tipos disponibles en el sistema de línea de negocio.  
  
- **Búsqueda de metadatos**, que permite al usuario buscar operaciones con distintos criterios que a menudo se basa en la línea del sistema de negocio. Por ejemplo, el usuario podría buscar en "* CUST\*" para recuperar todas las operaciones que tienen "CUST" en cualquier lugar en su nombre.  
  
- **Recuperación de metadatos**, que proporciona información acerca de una lista específica de los tipos de datos o las operaciones compatibles.  
  
  Si la línea del sistema de negocio contiene cientos o miles de operaciones, que proporciona la capacidad de buscar para operaciones específicas o ciertos grupos de información puede mejorar la experiencia del usuario.  
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF ](plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)