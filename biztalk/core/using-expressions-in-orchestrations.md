---
title: Usar expresiones en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1947cd39-6ef2-4b2d-afeb-a0132b19db97
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 880e1ee08a232aca3a04763c5d5c1797fd238fbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287140"
---
# <a name="using-expressions-in-orchestrations"></a><span data-ttu-id="63a15-102">Usar expresiones en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="63a15-102">Using Expressions in Orchestrations</span></span>
<span data-ttu-id="63a15-103">Puede usar el Editor de expresiones de BizTalk para escribir expresiones XLANG/s a fin de agregar lógica que manipule y pruebe los valores de las variables y mensajes de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="63a15-103">You can use BizTalk Expression Editor to enter XLANG/s expressions to add logic to manipulate and test the values of your orchestration variables and messages.</span></span> <span data-ttu-id="63a15-104">No obstante, no es recomendable utilizarlo en la lógica de orquestación de alto nivel, que se visualizaría mejor en el propio diseño de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="63a15-104">However, it is not a good practice to use it to perform high-level orchestration logic, which preferably would be visible in the orchestration drawing itself.</span></span> <span data-ttu-id="63a15-105">Por motivos de transparencia empresarial y de facilidad de reconfiguración, recomendamos usar expresiones sencillas y modulares.</span><span class="sxs-lookup"><span data-stu-id="63a15-105">For business process transparency and easy of reconfiguration, we recommend that you use simple and modular expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63a15-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="63a15-106">In This Section</span></span>  
 [<span data-ttu-id="63a15-107">Requisitos y limitaciones para las expresiones</span><span class="sxs-lookup"><span data-stu-id="63a15-107">Requirements and Limitations for Expressions</span></span>](../core/requirements-and-limitations-for-expressions.md)  
  
 [<span data-ttu-id="63a15-108">Formas que usan expresiones</span><span class="sxs-lookup"><span data-stu-id="63a15-108">Shapes that Take Expressions</span></span>](../core/shapes-that-take-expressions.md)  
  
 [<span data-ttu-id="63a15-109">Cómo crear expresiones</span><span class="sxs-lookup"><span data-stu-id="63a15-109">How to Create Expressions</span></span>](../core/how-to-create-expressions.md)  
  
 [<span data-ttu-id="63a15-110">Usar operadores en expresiones</span><span class="sxs-lookup"><span data-stu-id="63a15-110">Using Operators in Expressions</span></span>](../core/using-operators-in-expressions.md)  
  
 [<span data-ttu-id="63a15-111">Cómo usar expresiones para realizar asignaciones de mensajes</span><span class="sxs-lookup"><span data-stu-id="63a15-111">How to Use Expressions to Perform Message Assignments</span></span>](../core/how-to-use-expressions-to-perform-message-assignments.md)  
  
 [<span data-ttu-id="63a15-112">Cómo usar expresiones para transformar dinámica mensajes</span><span class="sxs-lookup"><span data-stu-id="63a15-112">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)  
  
 [<span data-ttu-id="63a15-113">Cómo usar expresiones para ejecutar canalizaciones</span><span class="sxs-lookup"><span data-stu-id="63a15-113">How to Use Expressions to Execute Pipelines</span></span>](../core/how-to-use-expressions-to-execute-pipelines.md)  
  
 [<span data-ttu-id="63a15-114">Cómo usar expresiones para crear objetos y llamar a métodos de objeto</span><span class="sxs-lookup"><span data-stu-id="63a15-114">How to Use Expressions to Create Objects and Call Object Methods</span></span>](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)  
  
 [<span data-ttu-id="63a15-115">Cómo usar expresiones para asignar valores a puertos dinámicos</span><span class="sxs-lookup"><span data-stu-id="63a15-115">How to Use Expressions to Assign Values to Dynamic Ports</span></span>](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="63a15-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="63a15-116">See Also</span></span>  
 <span data-ttu-id="63a15-117">[Lenguaje XLANG-s.](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="63a15-117">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="63a15-118">[Usar mensajes en orquestaciones](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="63a15-118">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="63a15-119">Usar Variables en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="63a15-119">Using Variables in Orchestrations</span></span>](../core/using-variables-in-orchestrations.md)