---
title: Con el formato de archivos motor de serialización | Documentos de Microsoft
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
ms.assetid: 0a519f0f-392b-4fa3-ab08-f09012d033af
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4f39f42c3513932b54a92946e448d821ee362a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287572"
---
# <a name="using-the-flat-file-serializing-engine"></a><span data-ttu-id="4daf9-102">Usar el motor de serialización de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="4daf9-102">Using the Flat File Serializing Engine</span></span>
<span data-ttu-id="4daf9-103">El motor de serialización de archivo sin formato se invoca mediante una llamada a la **Serialize** método de la **IFFDocumentSpec** interfaz.</span><span class="sxs-lookup"><span data-stu-id="4daf9-103">The flat file serializing engine is invoked by calling the **Serialize** method of the **IFFDocumentSpec** interface.</span></span> <span data-ttu-id="4daf9-104">Proporcionando un personalizada **XmlReader** como argumento al método, puede controlar los datos finales que se serializarán.</span><span class="sxs-lookup"><span data-stu-id="4daf9-104">By providing a customized **XmlReader** as the argument to the method, you can control the final data that gets serialized.</span></span> <span data-ttu-id="4daf9-105">Los datos pueden estar en cualquier formato, o ser simplemente un lector creado a partir de un XmlDocument.</span><span class="sxs-lookup"><span data-stu-id="4daf9-105">Data could be in any format, or could simply be a reader created of off an XmlDocument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4daf9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4daf9-106">Example</span></span>  
  
```  
Stream stm = docspec.Serialize(new MyXmlReader(originalXmlReader), Encoding.Unicode);  
```  
  
## <a name="see-also"></a><span data-ttu-id="4daf9-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="4daf9-107">See Also</span></span>  
 <span data-ttu-id="4daf9-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span><span class="sxs-lookup"><span data-stu-id="4daf9-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span></span>  
 [<span data-ttu-id="4daf9-109">Usar el motor de análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="4daf9-109">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)