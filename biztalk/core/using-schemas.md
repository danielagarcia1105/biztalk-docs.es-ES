---
title: Uso de esquemas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], schemas
ms.assetid: 07e60532-1032-422d-865e-0bd65c45dab6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a7cb71319fef61d3b6cb854b04b41e3815a6129
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287244"
---
# <a name="using-schemas"></a>Uso de esquemas
Esta sección contiene ejemplos de código para tareas comunes asociadas con el uso de esquemas.  
  
## <a name="using-xsd-schemas"></a>Utilizar esquemas XSD  
 El `IDocumentSpec Interface` interfaz representa una forma de documento definida por un esquema (XSD) de lenguaje de definición de esquemas XML; la forma tiene su raíz en un elemento de nivel superior del XSD. Después de instala el esquema, se puede recuperar mediante una llamada a la `IPipelineContext.GetDocumentSpecByType Method` o `IPipelineContext.GetDocumentSpecByName Method` métodos en el **IPipelineContext** interfaz.  
  
```  
IDocumentSpec docspec = pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="using-xsd-flat-file-schemas"></a>Utilizar esquemas de archivo sin formato XSD  
 Tanto el **GetDocumentSpecByType** y **GetDocumentSpecByName** métodos devuelven el **IDocumentSpec** interfaz. Si el esquema es realmente un esquema de archivo sin formato (uno que tenga otras anotaciones específico de archivo sin formato), se puede convertir el tipo del **IDocumentSpec** en **IFFDocumentSpec** e iniciar el análisis y serialización secuencias desde allí.  
  
```  
IFFDocumentSpec docspec = (IFFDocumentSpec) pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="see-also"></a>Vea también  

[Utilizar los motores de análisis y serialización](../core/using-the-parsing-and-serializing-engines.md)