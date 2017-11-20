---
title: "Motor de análisis de archivos de invocar el plano | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- IFFDocumentSpec interface
- pipeline components [custom], flat file documents
- pipeline components [custom], engines
ms.assetid: 9c5d325e-2fae-4291-af13-3fb06657ec0e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90108ff2ade354c51f87499a388ae54135f14c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoking-the-flat-file-parsing-engine"></a><span data-ttu-id="09c37-102">Invocar el motor de análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="09c37-102">Invoking the Flat File Parsing Engine</span></span>
<span data-ttu-id="09c37-103">El motor de análisis de archivo sin formato puede invocarse mediante una llamada a la **analizar** método de la **IFFDocumentSpec** interfaz, que a su vez es convertir el tipo de la `IDocumentSpec Interface` recuperados de la  **PipelineContext**.</span><span class="sxs-lookup"><span data-stu-id="09c37-103">The flat file parsing engine can be invoked by calling the **Parse** method of the **IFFDocumentSpec** interface, which in turn is typecast from the `IDocumentSpec Interface` retrieved from the **PipelineContext**.</span></span> <span data-ttu-id="09c37-104">Dado que la **XmlReader** devuelto desde el **analizar** método permite a los clientes recuperar un nodo a la vez, se trata de una buena oportunidad para personalizar el analizador.</span><span class="sxs-lookup"><span data-stu-id="09c37-104">Because the **XmlReader** returned from the **Parse** method allows clients to retrieve one node at a time, this is a good opportunity to customize the parser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09c37-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09c37-105">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="09c37-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="09c37-106">See Also</span></span>  
 [<span data-ttu-id="09c37-107">Usar el motor de análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="09c37-107">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)