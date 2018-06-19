---
title: El motor de análisis de ajuste | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], wrapping
- pipeline components [custom], code samples
ms.assetid: e00994de-bb86-40c0-a891-3f202147b5fe
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99d6960ba2f5f795a37bb336dab227f23eb12353
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288596"
---
# <a name="wrapping-the-parsing-engine"></a>El motor de análisis de ajuste
Puede crear sus propias **XmlReader** que incrusta el lector devuelto por la **analizar** método y ofrece personalización.  
  
## <a name="example"></a>Ejemplo  
  
```  
class MyXmlReader : XmlReader  
{  
   public MyXmlReader(XmlReader xr)  
   {  
      _xr = xr;  
   }  
  
   // Overrides XmlReader and provides customized functionality of _xr  
   // ...  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar el motor de análisis de archivo sin formato](../core/using-the-flat-file-parsing-engine.md)