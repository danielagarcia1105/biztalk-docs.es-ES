---
title: Anidar registros posicionales y delimitados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1688f04-d3c7-492c-82f7-a734bec0e409
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc3d994a3561f26df1bdffa7b547b1f647936a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263084"
---
# <a name="nested-positional-and-delimited-records"></a>Registros delimitados y posicionales anidados
En los formatos de archivo sin formato compatibles con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se permiten algunas combinaciones de registros delimitados y posicionales y otros no están permitidos. Se permiten las siguientes combinaciones:  
  
-   Los archivos sin formato en los que se usan delimitadores para determinar los límites entre todos los registros y los registros subordinados entre sí, y en los que se utilizan delimitadores (probablemente diferentes) para separar los campos dentro de estos registros.  
  
-   Los archivos sin formato en los que los límites entre todos los registros, los registros subordinados y los campos se determinan en función de la posición que ocupan dentro del archivo según longitudes predefinidas de registro y campo.  
  
-   Los archivos sin formato en los que se usan delimitadores para determinar los límites entre, como mínimo, el conjunto de registros más externo del archivo y en los que se utiliza una combinación de registros delimitados y posicionales subordinados. Los límites entre los campos de un registro delimitado o posicional subordinado se determinan mediante delimitadores o longitudes de campo fijas, respectivamente Los registros subordinados de un registro posicional (subordinado) también deben ser posicionales; es decir, una vez que una parte del archivo cambia de registros delimitados a posicionales, toda la parte subordinada del archivo debe ser posicional.  
  
 Debido a las ambigüedades de análisis que podrían resultar, los registros posicionales no pueden contener registros subordinados delimitados, con independencia de dónde aparezcan.  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones al crear sin formato de archivo esquemas de mensaje](../core/considerations-when-creating-flat-file-message-schemas.md)