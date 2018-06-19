---
title: Operadores lógicos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aaceb64-a5a0-462a-a0eb-8352bed999e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3b3c187e353babafd86590fdeacdc19fc115b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262076"
---
# <a name="logical-operators"></a><span data-ttu-id="b3221-102">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="b3221-102">Logical Operators</span></span>
<span data-ttu-id="b3221-103">El Marco de trabajo de reglas de negocio admite el uso de los operadores lógicos Y, O y NO en la creación de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="b3221-103">The Business Rules Framework supports using the logical AND, logical OR, and logical NOT operators in creating business rules.</span></span> <span data-ttu-id="b3221-104">En la tabla siguiente se describen los operadores lógicos.</span><span class="sxs-lookup"><span data-stu-id="b3221-104">The following table describes the logical operators.</span></span>  
  
|<span data-ttu-id="b3221-105">Operador lógico</span><span class="sxs-lookup"><span data-stu-id="b3221-105">Logical Operator</span></span>|<span data-ttu-id="b3221-106">Description</span><span class="sxs-lookup"><span data-stu-id="b3221-106">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="b3221-107">**AND**</span><span class="sxs-lookup"><span data-stu-id="b3221-107">**AND**</span></span>|<span data-ttu-id="b3221-108">Devuelve **true** si ambos operandos se evalúan como **true**; de lo contrario devuelve **false**.</span><span class="sxs-lookup"><span data-stu-id="b3221-108">Returns **true** if both the operands evaluate to **true**; otherwise returns **false**.</span></span>|  
|<span data-ttu-id="b3221-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="b3221-109">**OR**</span></span>|<span data-ttu-id="b3221-110">Devuelve **true** si uno de los operandos se evalúa como **true**, de lo contrario devuelve **false**.</span><span class="sxs-lookup"><span data-stu-id="b3221-110">Returns **true** if one of the operands evaluates to **true**, otherwise returns **false**.</span></span>|  
|<span data-ttu-id="b3221-111">**NOT**</span><span class="sxs-lookup"><span data-stu-id="b3221-111">**NOT**</span></span>|<span data-ttu-id="b3221-112">Devuelve **true** si el operando se evalúa como **false**, de lo contrario devuelve **false**.</span><span class="sxs-lookup"><span data-stu-id="b3221-112">Returns **true** if the operand evaluates to **false**, otherwise returns **false**.</span></span>|  
  
 <span data-ttu-id="b3221-113">Cuando los operandos son de tipos diferentes, el motor de reglas convierte el tipo de uno de los parámetros para que coincida con el tipo del otro parámetro, o bien convierte los dos parámetros a un tipo común antes de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="b3221-113">When operands are of different types, the rule engine converts type of one of the parameters to match the type of the other parameter or converts types of both the parameters to a common type before evaluating the expression.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="b3221-114">Para usar un operador lógico en una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="b3221-114">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="b3221-115">Use el siguiente procedimiento para usar un operador lógico en una regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="b3221-115">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="b3221-116">En el **IF** panel del compositor de reglas de negocio, haga clic en el **condiciones** nodo y, a continuación, seleccione el operador lógico que desea agregar a la expresión lógica.</span><span class="sxs-lookup"><span data-stu-id="b3221-116">In the **IF** pane of Business Rule Composer, right-click the **Conditions** node, and then select the logical operator that you wish to add to the logical expression.</span></span>  
  
2.  <span data-ttu-id="b3221-117">Haga clic con el botón secundario en el operador lógico y agregue los predicados o los operadores lógicos anidados que desee.</span><span class="sxs-lookup"><span data-stu-id="b3221-117">Right-click the logical operator, and add the predicates or nested logical operators you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3221-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3221-118">See Also</span></span>  
 [<span data-ttu-id="b3221-119">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="b3221-119">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)