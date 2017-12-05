---
title: Analizar caracteres de Escape | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], escape characters
- pipeline components [custom], parsing
ms.assetid: 2b33f436-3c29-4ff5-8dfa-26d6591713bc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f200e7c68a43360dc9edbae42ebea196b884f577
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="parsing-escape-characters"></a>Analizar caracteres de Escape
Cuando el analizador detecta un carácter de escape que se antepone a un carácter normal (esto es, uno que no es delimitador ni otro carácter especial), el carácter de escape se omite. Por ejemplo, dada una cadena "abc\d" donde "\\" es el carácter de escape, el resultado es "abcd".  
  
 Si el analizador detecta un carácter de doble escape (por ejemplo, "abc\\\d"), el resultado incluye un carácter de escape ("abc\d").  
  
 Si el analizador detecta tres caracteres de escape (por ejemplo, abc\\\\\d), el resultado es "abc\d" porque se analizan los primeros caracteres de escape de dos a "\\" y se omite el tercer carácter de escape.  
  
 El analizador trata los delimitadores colocados de forma errónea como caracteres normales. Por ejemplo, si se recibe "Record, Field1, Field, 2", el resultado XML es \<Field1\> \<Field, 2\>.  
  
## <a name="see-also"></a>Vea también  
 [Uso del motor de análisis de archivo sin formato](../core/using-the-flat-file-parsing-engine.md)