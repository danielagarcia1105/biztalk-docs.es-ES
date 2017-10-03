---
title: Analizar esquemas de archivo sin formato con registros posicionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], flat file documents
- pipeline components [custom], parsing
ms.assetid: 1ceb8c06-ac21-490e-b3d5-54e5035e5f6a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c4a6a1d5d6c263c0f794d1b703eff256f15c43b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="parsing-flat-file-schemas-with-positional-records"></a>Analizar esquemas de archivo sin formato con registros posicionales
Al analizar un esquema de archivo sin formato con registros posicionales de tamaños desiguales, debe incluir una etiqueta en cada registro del esquema, o bien el finalizador, para indicar el tamaño de cada registro posicional. De lo contrario, el motor de análisis devuelve el tamaño de registro más largo.  
  
## <a name="see-also"></a>Vea también  
 [Usar el motor de análisis de archivo sin formato](../core/using-the-flat-file-parsing-engine.md)