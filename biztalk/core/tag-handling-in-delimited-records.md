---
title: Control de etiqueta en los registros delimitados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 568eb804-bea5-46d4-8547-8bc30b87156c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c50a3daad9bb77ba4a9cbc264f018e29601edfff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972469"
---
# <a name="tag-handling-in-delimited-records"></a>Etiqueta de control en los registros delimitados

## <a name="overview"></a>Información general
Los registros delimitados pueden incluir una secuencia conocida de caracteres, denominada etiqueta, que puede usarse para eliminar la ambigüedad existente entre un tipo de registro y otro. Esto permitirá que el Desensamblador de archivos sin formato identificar correctamente el adecuado **registro** nodo en el esquema que contiene la información necesaria para analizar correctamente el registro de archivo sin formato.  

 Puede usar el **identificador de etiquetas** propiedad para especificar la etiqueta dentro de un registro delimitado. A diferencia de las etiquetas de los registros posicionales, las etiquetas de los registros delimitados deben aparecer al principio del registro delimitado y nunca se incluyen automáticamente en los datos cuando el registro se traduce al formato XML equivalente.  

## <a name="see-also"></a>Vea también  
- [Consideraciones acerca de los registros delimitados](../core/delimited-record-considerations.md)   
- **Identificador de etiquetas (propiedad de nodo de esquemas de archivo sin formato)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
