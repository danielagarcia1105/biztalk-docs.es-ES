---
title: Motor de análisis de archivos de invocar el plano | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- IFFDocumentSpec interface
- pipeline components [custom], flat file documents
- pipeline components [custom], engines
ms.assetid: 9c5d325e-2fae-4291-af13-3fb06657ec0e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90108ff2ade354c51f87499a388ae54135f14c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261844"
---
# <a name="invoking-the-flat-file-parsing-engine"></a>Invocar el motor de análisis de archivo sin formato
El motor de análisis de archivo sin formato puede invocarse mediante una llamada a la **analizar** método de la **IFFDocumentSpec** interfaz, que a su vez es convertir el tipo de la `IDocumentSpec Interface` recuperados de la  **PipelineContext**. Dado que la **XmlReader** devuelto desde el **analizar** método permite a los clientes recuperar un nodo a la vez, se trata de una buena oportunidad para personalizar el analizador.  
  
## <a name="example"></a>Ejemplo  
  
```  
XmlReader xr = docspec.Parse(new DataReader());  
while (xr.Read())  
{  
   switch(xr.NodeType)  
   {  
      case XmlNodeType.Element :  
         // Customize the element  
         //   
         break;  
      case XmlNodeType.Attribute :  
         // Customize the attribute  
         //   
         break;  
      // Customize other types of nodes  
      //   
   }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar el motor de análisis de archivo sin formato](../core/using-the-flat-file-parsing-engine.md)