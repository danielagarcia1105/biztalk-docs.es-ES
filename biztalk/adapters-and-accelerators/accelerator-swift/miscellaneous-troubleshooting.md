---
title: Solución de problemas de varios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 6ebc1867-b5d3-46de-b3bd-69e570ed2b2c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765b32895fa76c0c77b740b76e2e6a03f0571351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211180"
---
# <a name="miscellaneous-troubleshooting"></a><span data-ttu-id="897a7-102">Solución de problemas de varios</span><span class="sxs-lookup"><span data-stu-id="897a7-102">Miscellaneous Troubleshooting</span></span>
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a><span data-ttu-id="897a7-103">Ceros iniciales no se realiza la validación de campos que utilizan el método CheckLeadingZeroesInElement para validar un campo en el mensaje de la directiva de validación.</span><span class="sxs-lookup"><span data-stu-id="897a7-103">Leading zeroes validation is not performed for fields that use the CheckLeadingZeroesInElement method to validate a field in the message Validation Policy.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="897a7-104">Síntoma</span><span class="sxs-lookup"><span data-stu-id="897a7-104">Symptom</span></span>  
 <span data-ttu-id="897a7-105">Si se envía un mensaje con ceros a la izquierda en un campo, aunque no se permiten ceros a la izquierda del campo y la directiva de validación incluye una regla para el campo que realiza esta validación, se devuelve ningún error de validación de BRE.</span><span class="sxs-lookup"><span data-stu-id="897a7-105">No BRE validation error is returned if a message is submitted with leading zeroes in a field, even though leading zeroes are not permitted for the field and the validation policy includes a rule for the field that performs this validation.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="897a7-106">Causa posible</span><span class="sxs-lookup"><span data-stu-id="897a7-106">Possible Cause</span></span>  
 <span data-ttu-id="897a7-107">El **CheckLeadingZeroInElement** método se incluye en una regla de negocios en la directiva de validación para el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="897a7-107">The **CheckLeadingZeroInElement** method is included in a business rule in the validation policy for the message type.</span></span> <span data-ttu-id="897a7-108">Este método es desusado.</span><span class="sxs-lookup"><span data-stu-id="897a7-108">This method is deprecated.</span></span> <span data-ttu-id="897a7-109">El propósito de la llamada de función es generen un error si no hay un cero inicial en el elemento proporcionado en la llamada de función en la validación.</span><span class="sxs-lookup"><span data-stu-id="897a7-109">The purpose of the function call is to cause validation to fail if there is a leading zero in the element provided in the function call.</span></span> <span data-ttu-id="897a7-110">Sin embargo, este método no hace que no puede validarse, incluso si hay un cero inicial en el campo.</span><span class="sxs-lookup"><span data-stu-id="897a7-110">However, this method does not cause validation to fail, even if there is a leading zero in the field.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="897a7-111">Solución</span><span class="sxs-lookup"><span data-stu-id="897a7-111">Solution</span></span>  
 <span data-ttu-id="897a7-112">Si desea comprobar los ceros iniciales, debe implementar la **CheckLeadingZero** en lugar del método la **CheckLeadingZeroInElement** método.</span><span class="sxs-lookup"><span data-stu-id="897a7-112">If you want to check leading zeroes, you must implement the **CheckLeadingZero** method instead of the **CheckLeadingZeroInElement** method.</span></span> <span data-ttu-id="897a7-113">**CheckLeadingZero** producirá un error de validación si no hay un cero a la izquierda de la entrada de cadena a la función.</span><span class="sxs-lookup"><span data-stu-id="897a7-113">**CheckLeadingZero** causes a validation error if there is a leading zero in the string input to the function.</span></span>  
  
 <span data-ttu-id="897a7-114">Para implementar la **CheckLeadingZero** método, debe crear un método personalizado que se invoca el **CheckLeadingZero** método desde dentro de la función personalizada y proporciona a ella como una cadena el valor para que sea validar por ceros iniciales.</span><span class="sxs-lookup"><span data-stu-id="897a7-114">To implement the **CheckLeadingZero** method, you must create a custom method that invokes the **CheckLeadingZero** method from within the custom function and provides to it as a string the value to be validated for leading zeroes.</span></span> <span data-ttu-id="897a7-115">Esto es porque **CheckLeadingZero** no registra un error, pero en su lugar, simplemente devuelve un valor booleano False si la cadena de entrada no es un campo de número de SWIFT válido o si la entrada de cadena tiene un cero inicial.</span><span class="sxs-lookup"><span data-stu-id="897a7-115">This is because **CheckLeadingZero** does not log an error, but instead simply returns a Boolean False if the input string is not a valid SWIFT Number field or if the string input has a leading zero.</span></span> <span data-ttu-id="897a7-116">En caso contrario, devuelve True.</span><span class="sxs-lookup"><span data-stu-id="897a7-116">Otherwise, it returns True.</span></span> <span data-ttu-id="897a7-117">El método personalizado, a continuación, puede registrar los errores según corresponda.</span><span class="sxs-lookup"><span data-stu-id="897a7-117">Your custom method can then log errors accordingly.</span></span>  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a><span data-ttu-id="897a7-118">Se devuelve un error por la directiva de validación de mensaje si el campo de número de SWIFT tiene un cero a la izquierda</span><span class="sxs-lookup"><span data-stu-id="897a7-118">An error is returned by the message validation policy if the SWIFT Number field has a leading zero</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="897a7-119">Síntoma</span><span class="sxs-lookup"><span data-stu-id="897a7-119">Symptom</span></span>  
 <span data-ttu-id="897a7-120">Si un mensaje se envía con ceros a la izquierda en un campo aunque iniciales se permiten ceros para el campo, se devuelve un error de validación de BRE.</span><span class="sxs-lookup"><span data-stu-id="897a7-120">A BRE validation error is returned if a message is submitted with leading zeroes in a field even though leading zeroes are permitted for the field.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="897a7-121">Causa posible</span><span class="sxs-lookup"><span data-stu-id="897a7-121">Possible Cause</span></span>  
 <span data-ttu-id="897a7-122">Esto puede ocurrir si se usa alguno de los métodos siguientes para validar un campo de número de SWIFT en la regla que se trate, normalmente en la parte de la acción de la regla.</span><span class="sxs-lookup"><span data-stu-id="897a7-122">This can occur if one of the following methods is used to validate a SWIFT Number field in the rule concerned, usually in the Action part of the rule.</span></span> <span data-ttu-id="897a7-123">Esto puede ocurrir en un campo de cantidad, velocidad, el precio o cantidad.</span><span class="sxs-lookup"><span data-stu-id="897a7-123">This may occur in an Amount, Rate, Price, or Quantity field.</span></span>  
  
-   <span data-ttu-id="897a7-124">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="897a7-124">**CheckCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="897a7-125">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="897a7-125">**CheckValidAmount**</span></span>  
  
-   <span data-ttu-id="897a7-126">**CheckValidCurrencyAndPriceCode**</span><span class="sxs-lookup"><span data-stu-id="897a7-126">**CheckValidCurrencyAndPriceCode**</span></span>  
  
-   <span data-ttu-id="897a7-127">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="897a7-127">**CheckValidSignCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="897a7-128">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="897a7-128">**CheckValidSignDateCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="897a7-129">**CheckValidSignRate**</span><span class="sxs-lookup"><span data-stu-id="897a7-129">**CheckValidSignRate**</span></span>  
  
-   <span data-ttu-id="897a7-130">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="897a7-130">**IsValidTransactionDetailsCurrencyAmount**</span></span>  
  
### <a name="solution"></a><span data-ttu-id="897a7-131">Solución</span><span class="sxs-lookup"><span data-stu-id="897a7-131">Solution</span></span>  
 <span data-ttu-id="897a7-132">Si cualquiera de los métodos en la lista anterior, excepto para **CheckValidSignRate**, se utiliza en la regla en la directiva de validación, habilitar los ceros iniciales como se describe en [compatible con ceros a la izquierda en el campo de cantidad validaciones](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).</span><span class="sxs-lookup"><span data-stu-id="897a7-132">If any of the methods in the list above, except for **CheckValidSignRate**, is used in the rule in the Validation policy, enable leading zeros as described in [Supporting Leading Zeros in Amount Field Validations](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).</span></span>  
  
 <span data-ttu-id="897a7-133">Si el **CheckValidSignRate** método se utiliza en la regla que devuelve este error, es la única manera de admitir ceros a la izquierda quitar esta regla de la directiva de validación.</span><span class="sxs-lookup"><span data-stu-id="897a7-133">If the **CheckValidSignRate** method is used in the rule that returned this error, the only way to support leading zeroes is to remove this rule from the Validation policy.</span></span> <span data-ttu-id="897a7-134">Siga estos pasos para lograr esto:</span><span class="sxs-lookup"><span data-stu-id="897a7-134">Follow the steps below to accomplish this:</span></span>  
  
1.  <span data-ttu-id="897a7-135">En el Compositor de reglas de negocio, haga clic en el **versión** nodo para la directiva implementada que contiene una regla mediante el **CheckValidSignRate** método.</span><span class="sxs-lookup"><span data-stu-id="897a7-135">In Business Rule Composer, right-click the **Version** node for the deployed policy that contains a rule using the **CheckValidSignRate** method.</span></span> <span data-ttu-id="897a7-136">Haga clic en **Anular la implementación**.</span><span class="sxs-lookup"><span data-stu-id="897a7-136">Click **Undeploy**.</span></span>  
  
2.  <span data-ttu-id="897a7-137">Haga clic en el **versión** nodo para la misma directiva y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="897a7-137">Right-click the **Version** node for the same policy, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="897a7-138">Haga clic en el **Validation_Policy** nodo para la misma directiva y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="897a7-138">Right-click the **Validation_Policy** node for the same policy, and then click **Paste**.</span></span>  
  
4.  <span data-ttu-id="897a7-139">Expanda la nueva versión que no haya guardado de la directiva.</span><span class="sxs-lookup"><span data-stu-id="897a7-139">Expand the new unsaved version of the policy.</span></span> <span data-ttu-id="897a7-140">Haga clic en la regla que tiene el **CheckValidSignRate** llamada al método y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="897a7-140">Right-click the rule that has the **CheckValidSignRate** method call, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="897a7-141">Menú contextual nuevo sin guardar la directiva **versión** nodo y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="897a7-141">Right-click the policy's new unsaved **Version** node, and then click **Save**.</span></span> <span data-ttu-id="897a7-142">Haga clic en el mismo nodo y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="897a7-142">Right-click the same node, and then click **Publish**.</span></span> <span data-ttu-id="897a7-143">Haga clic en el mismo nodo y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="897a7-143">Right-click the same node, and then click **Deploy**.</span></span>  
  
## <a name="a4swift-database-requires-archiving"></a><span data-ttu-id="897a7-144">Base de datos de A4SWIFT requiere el archivado</span><span class="sxs-lookup"><span data-stu-id="897a7-144">A4SWIFT database requires archiving</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="897a7-145">Síntoma</span><span class="sxs-lookup"><span data-stu-id="897a7-145">Symptom</span></span>  
 <span data-ttu-id="897a7-146">El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos es demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="897a7-146">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database is growing too large.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="897a7-147">Causa posible</span><span class="sxs-lookup"><span data-stu-id="897a7-147">Possible Cause</span></span>  
 <span data-ttu-id="897a7-148">La tabla de historial en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos no se archiva automáticamente.</span><span class="sxs-lookup"><span data-stu-id="897a7-148">The History table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database is not automatically archived.</span></span> <span data-ttu-id="897a7-149">Esta tabla almacena datos acerca de la reparación de mensajes y nuevo envío, incluido quién llevó a cabo las tareas y los datos acerca de los procesos de orquestación.</span><span class="sxs-lookup"><span data-stu-id="897a7-149">This table stores data about message repair and new submission, including who performed which tasks and data about orchestration processes.</span></span> <span data-ttu-id="897a7-150">Esta tabla continuará creciendo como para realizar la reparación de mensajes y las operaciones de envío nuevo.</span><span class="sxs-lookup"><span data-stu-id="897a7-150">This table will continue to grow as you perform message repair and new submission operations.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="897a7-151">Solución</span><span class="sxs-lookup"><span data-stu-id="897a7-151">Solution</span></span>  
 <span data-ttu-id="897a7-152">Para limitar el crecimiento de la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos, archivarse periódicamente datos fuera de la tabla de historial, mediante el estándar de archivar los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="897a7-152">To limit growth of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, routinely archive data out of the History table, using your standard archiving procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="897a7-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="897a7-153">See Also</span></span>  
 [<span data-ttu-id="897a7-154">Solución de problemas: Problemas y soluciones</span><span class="sxs-lookup"><span data-stu-id="897a7-154">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)