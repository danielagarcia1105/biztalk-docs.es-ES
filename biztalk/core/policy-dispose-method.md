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
# <a name="policydispose-method"></a><span data-ttu-id="b88a5-102">Policy.Dispose (método)</span><span class="sxs-lookup"><span data-stu-id="b88a5-102">Policy.Dispose Method</span></span>
<span data-ttu-id="b88a5-103">El **Policy.Dispose** método libera los recursos usados por la **directiva** (clase) y también devuelve el **directiva** objeto a la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b88a5-103">The **Policy.Dispose** method releases resources used by the **Policy** class, and also returns the **Policy** object to the cache.</span></span> <span data-ttu-id="b88a5-104">Cuando se invoca la misma directiva de nuevo, las almacenadas en caché **directiva** se usa el objeto, lo que ahorra el tiempo necesario para crear un nuevo **directiva** objeto.</span><span class="sxs-lookup"><span data-stu-id="b88a5-104">When the same policy is invoked again, the cached **Policy** object is used, which saves the time needed for creating a new **Policy** object.</span></span>  
  
 <span data-ttu-id="b88a5-105">Si no llama de forma explícita el **Policy.Dispose** método y, a continuación, la directiva no se devuelve a la memoria caché hasta que el tiempo de ejecución .NET libera el objeto durante el proceso de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b88a5-105">If you do not explicitly call the **Policy.Dispose** method, then the policy is not returned to the cache until the .NET runtime frees up the object during the garbage collection process.</span></span> <span data-ttu-id="b88a5-106">Por lo tanto, debe llamar a **Policy.Dispose** cuando haya terminado con el **directiva** objeto.</span><span class="sxs-lookup"><span data-stu-id="b88a5-106">Therefore, you should call **Policy.Dispose** when you are finished with the **Policy** object.</span></span>  
  
 <span data-ttu-id="b88a5-107">El código de ejemplo para usar el **Policy.Dispose** método es como sigue:</span><span class="sxs-lookup"><span data-stu-id="b88a5-107">The sample code for using the **Policy.Dispose** method is as follows:</span></span>  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```