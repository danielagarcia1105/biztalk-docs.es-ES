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
ms.openlocfilehash: 50e65ccbe1a1197a3b85ec86a8ae9e11f25eaf61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="parsing-escape-characters"></a><span data-ttu-id="d3f17-102">Analizar caracteres de Escape</span><span class="sxs-lookup"><span data-stu-id="d3f17-102">Parsing Escape Characters</span></span>
<span data-ttu-id="d3f17-103">Cuando el analizador detecta un carácter de escape que se antepone a un carácter normal (esto es, uno que no es delimitador ni otro carácter especial), el carácter de escape se omite.</span><span class="sxs-lookup"><span data-stu-id="d3f17-103">When the parser encounters an escape character that prefixes a regular character (that is, one that is not a delimiter or other special character), the escape character is ignored.</span></span> <span data-ttu-id="d3f17-104">Por ejemplo, dada una cadena "abc\d" donde "\\" es el carácter de escape, el resultado es "abcd".</span><span class="sxs-lookup"><span data-stu-id="d3f17-104">For example, given a string "abc\d" where "\\" is the escape character, the output is "abcd".</span></span>  
  
 <span data-ttu-id="d3f17-105">Si el analizador detecta un carácter de doble escape (por ejemplo, "abc\\\d"), el resultado incluye un carácter de escape ("abc\d").</span><span class="sxs-lookup"><span data-stu-id="d3f17-105">If the parser encounters a double escape character (for example, "abc\\\d"), the output includes a single escape character ("abc\d").</span></span>  
  
 <span data-ttu-id="d3f17-106">Si el analizador detecta tres caracteres de escape (por ejemplo, abc\\\\\d), el resultado es "abc\d" porque se analizan los primeros caracteres de escape de dos a "\\" y se omite el tercer carácter de escape.</span><span class="sxs-lookup"><span data-stu-id="d3f17-106">If the parser encounters three escape characters (for example, abc\\\\\d), the output is "abc\d" because the first two escape characters are parsed to "\\" and the third escape character is ignored.</span></span>  
  
 <span data-ttu-id="d3f17-107">El analizador trata los delimitadores colocados de forma errónea como caracteres normales.</span><span class="sxs-lookup"><span data-stu-id="d3f17-107">The parser treats misplaced delimiters as regular characters.</span></span> <span data-ttu-id="d3f17-108">Por ejemplo, si se recibe "Record, Field1, Field, 2", el resultado XML es \<Field1 > \<Field, 2 >.</span><span class="sxs-lookup"><span data-stu-id="d3f17-108">For example, if "Record, Field1, Field,2" is received, the output XML is \<Field1> \<Field,2>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f17-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3f17-109">See Also</span></span>  
 [<span data-ttu-id="d3f17-110">Usar el motor de análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="d3f17-110">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)