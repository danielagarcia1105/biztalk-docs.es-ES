---
title: Control de etiqueta en los registros delimitados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 568eb804-bea5-46d4-8547-8bc30b87156c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5be9d28e3de6b1a7613db8d0c5ac7365a298a679
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tag-handling-in-delimited-records"></a>Tratamiento de los registros delimitados de las etiquetas

## <a name="overview"></a>Información general
Los registros delimitados pueden incluir una secuencia conocida de caracteres, denominada etiqueta, que puede usarse para eliminar la ambigüedad existente entre un tipo de registro y otro. Esto permitirá que el Desensamblador de archivos sin formato identificar correctamente la correspondiente **registro** nodo en el esquema que contiene la información necesaria para analizar correctamente el registro de archivo sin formato.  
  
 Puede usar el **identificador de etiquetas** propiedad para especificar la etiqueta en un registro delimitado. A diferencia de las etiquetas de los registros posicionales, las etiquetas de los registros delimitados deben aparecer al principio del registro delimitado y nunca se incluyen automáticamente en los datos cuando el registro se traduce al formato XML equivalente.  
  
## <a name="see-also"></a>Vea también  
-  [Consideraciones de registro delimitadas](../core/delimited-record-considerations.md)   
-  **Identificador (propiedad de nodo de esquemas de archivo sin formato) de etiquetas**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]