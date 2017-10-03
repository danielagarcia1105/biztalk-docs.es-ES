---
title: Uso de esquemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], schemas
ms.assetid: 07e60532-1032-422d-865e-0bd65c45dab6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a7cb71319fef61d3b6cb854b04b41e3815a6129
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-schemas"></a><span data-ttu-id="c9112-102">Uso de esquemas</span><span class="sxs-lookup"><span data-stu-id="c9112-102">Using Schemas</span></span>
<span data-ttu-id="c9112-103">Esta sección contiene ejemplos de código para tareas comunes asociadas con el uso de esquemas.</span><span class="sxs-lookup"><span data-stu-id="c9112-103">This section contains code examples for common tasks associated with using schemas.</span></span>  
  
## <a name="using-xsd-schemas"></a><span data-ttu-id="c9112-104">Utilizar esquemas XSD</span><span class="sxs-lookup"><span data-stu-id="c9112-104">Using XSD schemas</span></span>  
 <span data-ttu-id="c9112-105">El `IDocumentSpec Interface` interfaz representa una forma de documento definida por un esquema (XSD) de lenguaje de definición de esquemas XML; la forma tiene su raíz en un elemento de nivel superior del XSD.</span><span class="sxs-lookup"><span data-stu-id="c9112-105">The `IDocumentSpec Interface` interface represents a document shape defined by an XML Schema definition language (XSD) schema; the shape is rooted by a top-level element of the XSD.</span></span> <span data-ttu-id="c9112-106">Después de instala el esquema, se puede recuperar mediante una llamada a la `IPipelineContext.GetDocumentSpecByType Method` o `IPipelineContext.GetDocumentSpecByName Method` métodos en el **IPipelineContext** interfaz.</span><span class="sxs-lookup"><span data-stu-id="c9112-106">After the schema is installed, it can be retrieved by calling the `IPipelineContext.GetDocumentSpecByType Method` or `IPipelineContext.GetDocumentSpecByName Method` methods in the **IPipelineContext** interface.</span></span>  
  
```  
IDocumentSpec docspec = pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="using-xsd-flat-file-schemas"></a><span data-ttu-id="c9112-107">Utilizar esquemas de archivo sin formato XSD</span><span class="sxs-lookup"><span data-stu-id="c9112-107">Using XSD flat file schemas</span></span>  
 <span data-ttu-id="c9112-108">Tanto el **GetDocumentSpecByType** y **GetDocumentSpecByName** métodos devuelven el **IDocumentSpec** interfaz.</span><span class="sxs-lookup"><span data-stu-id="c9112-108">Both the **GetDocumentSpecByType** and **GetDocumentSpecByName** methods return the **IDocumentSpec** interface.</span></span> <span data-ttu-id="c9112-109">Si el esquema es realmente un esquema de archivo sin formato (uno que tenga otras anotaciones específico de archivo sin formato), se puede convertir el tipo del **IDocumentSpec** en **IFFDocumentSpec** e iniciar el análisis y serialización secuencias desde allí.</span><span class="sxs-lookup"><span data-stu-id="c9112-109">If the schema is actually a flat file schema (one that has additional flat file-specific annotations), you can typecast the **IDocumentSpec** into **IFFDocumentSpec** and initiate parsing and serializing sequences from there.</span></span>  
  
```  
IFFDocumentSpec docspec = (IFFDocumentSpec) pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9112-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9112-110">See Also</span></span>  

[<span data-ttu-id="c9112-111">Utilizar los motores de análisis y serialización</span><span class="sxs-lookup"><span data-stu-id="c9112-111">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)