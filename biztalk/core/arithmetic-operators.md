---
title: Operadores aritméticos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73e153c-aac1-4cea-92d8-af4a1bea6e6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b3d66a990437929176835228efa1a74a5fa8683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230524"
---
# <a name="arithmetic-operators"></a><span data-ttu-id="b7aae-102">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="b7aae-102">Arithmetic Operators</span></span>
<span data-ttu-id="b7aae-103">El marco de trabajo de reglas de negocios admite el uso de los operadores de suma, resta, multiplicación, división y resto (módulo) para la creación de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="b7aae-103">The Business Rules Framework supports using the addition, subtraction, multiplication, division, and remainder (modulo) operators in creating business rules.</span></span> <span data-ttu-id="b7aae-104">En la tabla siguiente se describen los operadores aritméticos.</span><span class="sxs-lookup"><span data-stu-id="b7aae-104">The following table describes the arithmetic operators.</span></span>  
  
|<span data-ttu-id="b7aae-105">Operador aritmético</span><span class="sxs-lookup"><span data-stu-id="b7aae-105">Arithmetic operator</span></span>|<span data-ttu-id="b7aae-106">Description</span><span class="sxs-lookup"><span data-stu-id="b7aae-106">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="b7aae-107">**Agregar**</span><span class="sxs-lookup"><span data-stu-id="b7aae-107">**Add**</span></span>|<span data-ttu-id="b7aae-108">Representa el operador de suma (arg1 sumado a arg2).</span><span class="sxs-lookup"><span data-stu-id="b7aae-108">Represents the addition operator (arg1 added to arg2).</span></span>|  
|<span data-ttu-id="b7aae-109">**Restar**</span><span class="sxs-lookup"><span data-stu-id="b7aae-109">**Subtract**</span></span>|<span data-ttu-id="b7aae-110">Representa el operador de resta (arg1 restado de arg2).</span><span class="sxs-lookup"><span data-stu-id="b7aae-110">Represents the subtraction operator (arg1 subtracted from arg2).</span></span>|  
|<span data-ttu-id="b7aae-111">**Multiplicar**</span><span class="sxs-lookup"><span data-stu-id="b7aae-111">**Multiply**</span></span>|<span data-ttu-id="b7aae-112">Representa el operador de multiplicación (arg1 multiplicado por arg2).</span><span class="sxs-lookup"><span data-stu-id="b7aae-112">Represents the multiplication operator (arg1 multiplied by arg2).</span></span>|  
|<span data-ttu-id="b7aae-113">**Divide**</span><span class="sxs-lookup"><span data-stu-id="b7aae-113">**Divide**</span></span>|<span data-ttu-id="b7aae-114">Representa el operador de división (arg1 dividido entre arg2).</span><span class="sxs-lookup"><span data-stu-id="b7aae-114">Represents the division operator (arg1 divided by arg2).</span></span>|  
|<span data-ttu-id="b7aae-115">**Resto**</span><span class="sxs-lookup"><span data-stu-id="b7aae-115">**Remainder**</span></span>|<span data-ttu-id="b7aae-116">Representa el operador de resto (arg1 módulo arg2).</span><span class="sxs-lookup"><span data-stu-id="b7aae-116">Represents the remainder operator (arg1 modulo arg2).</span></span>|  
  
 <span data-ttu-id="b7aae-117">Cuando los operandos son de diferentes tipos se produce una promoción numérica automática, en la que el tipo de operando más pequeño se convierte en el tipo de operando mayor.</span><span class="sxs-lookup"><span data-stu-id="b7aae-117">When operands are of different types, automatic numeric promotion occurs with the smaller operand type being converted to the larger operand type.</span></span> <span data-ttu-id="b7aae-118">Por ejemplo, si la **agregar** operador se usa con el primer operando de **int** tipo y el segundo operando del **largo** tipo, el tipo del primer operando se convierte en **largo** antes de realizar la **agregar** operación.</span><span class="sxs-lookup"><span data-stu-id="b7aae-118">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **long** type, the type of the first operand is converted to **long** before performing the **Add** operation.</span></span> <span data-ttu-id="b7aae-119">El motor de reglas también admite la promoción doble si ambos operandos se pueden promocionar a un tipo común.</span><span class="sxs-lookup"><span data-stu-id="b7aae-119">The rule engine also supports double promotion if both the operands can be promoted to a common type.</span></span> <span data-ttu-id="b7aae-120">Por ejemplo, si la **agregar** operador se usa con el primer operando de **int** tipo y el segundo operando del **uint** tipo, los tipos de ambos operandos se convierten en **long** antes de realizar la **agregar** operación.</span><span class="sxs-lookup"><span data-stu-id="b7aae-120">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **uint** type, the types of both operands are converted to **long** before performing the **Add** operation.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="b7aae-121">Para usar un operador lógico en una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="b7aae-121">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="b7aae-122">Use el siguiente procedimiento para usar un operador lógico en una regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="b7aae-122">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="b7aae-123">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.</span><span class="sxs-lookup"><span data-stu-id="b7aae-123">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="b7aae-124">Expanda **vocabularios**, expanda **funciones**, expanda **versión 1.0 - publicada**y, a continuación, arrastre el **agregar/restar/multiplicar/dividir/aviso** al panel condiciones o acciones de panel.</span><span class="sxs-lookup"><span data-stu-id="b7aae-124">Expand **Vocabularies**, expand **Functions**, expand **Version 1.0 - Published**, and then drag the **Add/Subtract/Multiply/Divide/Remainder** to the Conditions pane/Actions pane.</span></span>  
  
3.  <span data-ttu-id="b7aae-125">Especifique valores para los operadores izquierdo y derecho.</span><span class="sxs-lookup"><span data-stu-id="b7aae-125">Specify values for left and right operators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7aae-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7aae-126">See Also</span></span>  
 [<span data-ttu-id="b7aae-127">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="b7aae-127">Logical Operators</span></span>](../core/logical-operators.md)