---
title: Cómo ejecutar directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0aa834150f0d5c84ebb4c757769a2be38f3942
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253804"
---
# <a name="how-to-execute-policies"></a><span data-ttu-id="b80c7-102">Cómo ejecutar directivas</span><span class="sxs-lookup"><span data-stu-id="b80c7-102">How to Execute Policies</span></span>
<span data-ttu-id="b80c7-103">El código de ejemplo siguiente muestra cómo invocar el motor de reglas para ejecutar una directiva mediante programación utilizando la **directiva** clase en el **Microsoft.RuleEngine** ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b80c7-103">The following sample code shows how to invoke the rule engine to execute a policy programmatically by using the **Policy** class in the **Microsoft.RuleEngine** assembly.</span></span>  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a><span data-ttu-id="b80c7-104">Métodos importantes de la clase de directiva</span><span class="sxs-lookup"><span data-stu-id="b80c7-104">Important methods of the Policy class</span></span>  
 <span data-ttu-id="b80c7-105">A continuación se presentan los métodos importantes de la clase Directiva y las descripciones correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b80c7-105">Here are the important methods of the Policy class and their descriptions.</span></span>  
  
|<span data-ttu-id="b80c7-106">Método de la clase Directiva</span><span class="sxs-lookup"><span data-stu-id="b80c7-106">Method in the Policy class</span></span>|<span data-ttu-id="b80c7-107">Description</span><span class="sxs-lookup"><span data-stu-id="b80c7-107">Description</span></span>|  
|--------------------------------|-----------------|  
|<span data-ttu-id="b80c7-108">Execute</span><span class="sxs-lookup"><span data-stu-id="b80c7-108">Execute</span></span>|<span data-ttu-id="b80c7-109">Agrega los hechos a corto plazo especificados en la memoria de trabajo del motor de reglas y ejecuta la directiva mediante el algoritmo de acción o resolución de conflictos o coincidencias.</span><span class="sxs-lookup"><span data-stu-id="b80c7-109">Adds the specified short-term facts into the rule engine's working memory and executes the policy using Match-Conflict Resolution-Action algorithm.</span></span> <span data-ttu-id="b80c7-110">Para obtener más información sobre el algoritmo de acción o resolución de conflictos o coincidencias, vea [evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md) .</span><span class="sxs-lookup"><span data-stu-id="b80c7-110">For more information on Match-Conflict Resolution-Action algorithm, see [Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) .</span></span>|  
|<span data-ttu-id="b80c7-111">Dispose</span><span class="sxs-lookup"><span data-stu-id="b80c7-111">Dispose</span></span>|<span data-ttu-id="b80c7-112">Publica los recursos que usa el motor de reglas para la ejecución de la directiva.</span><span class="sxs-lookup"><span data-stu-id="b80c7-112">Releases the resources used by the rule engine for executing the policy.</span></span>|  
|<span data-ttu-id="b80c7-113">Desactivar</span><span class="sxs-lookup"><span data-stu-id="b80c7-113">Clear</span></span>|<span data-ttu-id="b80c7-114">Borra o restablece la memoria de trabajo y la agenda de la instancia del motor de reglas para la ejecución de la directiva.</span><span class="sxs-lookup"><span data-stu-id="b80c7-114">Clears or resets the working memory and the agenda of the rule engine instance created for executing the policy.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b80c7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b80c7-115">See Also</span></span>  
 [<span data-ttu-id="b80c7-116">Método Policy.Dispose</span><span class="sxs-lookup"><span data-stu-id="b80c7-116">Policy.Dispose Method</span></span>](../core/policy-dispose-method.md)