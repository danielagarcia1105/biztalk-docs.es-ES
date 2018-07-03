---
title: Anidar registros delimitados y posicionales | Microsoft Docs
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
ms.openlocfilehash: 3896eb41a52ee356021a6fcf7e7621267f8764f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971221"
---
# <a name="nested-positional-and-delimited-records"></a>Registros delimitados y posicionales anidados
En los formatos de archivo sin formato compatibles con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se permiten algunas combinaciones de registros delimitados y posicionales y otras no. Se permiten las siguientes combinaciones:  
  
- Los archivos sin formato en los que se usan delimitadores para determinar los límites entre todos los registros y los registros subordinados entre sí, y en los que se utilizan delimitadores (probablemente diferentes) para separar los campos dentro de estos registros.  
  
- Los archivos sin formato en los que los límites entre todos los registros, los registros subordinados y los campos se determinan en función de la posición que ocupan dentro del archivo según longitudes predefinidas de registro y campo.  
  
- Los archivos sin formato en los que se usan delimitadores para determinar los límites entre, como mínimo, el conjunto de registros más externo del archivo y en los que se utiliza una combinación de registros delimitados y posicionales subordinados. Los límites entre los campos de un registro delimitado o posicional subordinado se determinan mediante delimitadores o longitudes de campo fijas, respectivamente Los registros subordinados de un registro posicional (subordinado) también deben ser posicionales; es decir, una vez que una parte del archivo cambia de registros delimitados a posicionales, toda la parte subordinada del archivo debe ser posicional.  
  
  Debido a las ambigüedades de análisis que podrían resultar, los registros posicionales no pueden contener registros subordinados delimitados, con independencia de dónde aparezcan.  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones al crear esquemas de mensajes de archivo sin formato](../core/considerations-when-creating-flat-file-message-schemas.md)