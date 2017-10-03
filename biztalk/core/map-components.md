---
title: Asignar componentes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper, output
- maps, file type
- maps, file contents
- BizTalk Mapper, file type
- maps, components
ms.assetid: be438d21-80a8-49d8-bd08-d85618ab23de
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58a7555ff45d25c4e131b05b078c713f7a169687
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="map-components"></a>Componentes de asignaciones
Los archivos de asignación (extensión .btm) almacenan la mayoría de los componentes de una asignación. Los elementos almacenados en el archivo incluyen:  
  
-   Referencias a los esquemas de origen y de destino  
  
-   Vínculos, incluidas las propiedades de vínculos  
  
-   Functoids, con sus propiedades, como los parámetros de entrada  
  
-   Otras propiedades varias, como las asociadas con la propia asignación y la cuadrícula.  
  
 Aunque el Asignador de BizTalk compila la asignación del archivo .btm en un archivo de Transformación de lenguaje de hojas de estilo extensible (XSLT), el XSLT no forma parte del archivo. El Asignador de BizTalk produce el XSLT para la asignación solo cuando se compila el proyecto o cuando se valida la asignación. El Asignador de BizTalk empaqueta el XSLT como parte del ensamblado del proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Mapas](../core/maps.md)   
 [Crear asignaciones usando al asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)