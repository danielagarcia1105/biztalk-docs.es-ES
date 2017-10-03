---
title: "Método Policy.Dispose | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db37c6b9-acf0-42ee-9356-4d1567934862
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba4713616edf55c149a215a6f7842cd5d0353dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="policydispose-method"></a>Policy.Dispose (método)
El **Policy.Dispose** método libera los recursos usados por la **directiva** (clase) y también devuelve el **directiva** objeto a la memoria caché. Cuando se invoca la misma directiva de nuevo, las almacenadas en caché **directiva** se usa el objeto, lo que ahorra el tiempo necesario para crear un nuevo **directiva** objeto.  
  
 Si no llama de forma explícita el **Policy.Dispose** método y, a continuación, la directiva no se devuelve a la memoria caché hasta que el tiempo de ejecución .NET libera el objeto durante el proceso de recopilación de elementos no utilizados. Por lo tanto, debe llamar a **Policy.Dispose** cuando haya terminado con el **directiva** objeto.  
  
 El código de ejemplo para usar el **Policy.Dispose** método es como sigue:  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```