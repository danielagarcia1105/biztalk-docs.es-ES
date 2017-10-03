---
title: Objeto Recaller | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Recaller object
- Invoke method
- process management solution tutorial, Recaller object
- process management solution tutorial, errors
ms.assetid: b30ad1ae-475f-4913-b402-4d3263fcf072
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f7703eb9145b1249872902d0b867fe22622ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-recaller-object"></a><span data-ttu-id="aec7c-102">Objeto Recaller</span><span class="sxs-lookup"><span data-stu-id="aec7c-102">The Recaller Object</span></span>
<span data-ttu-id="aec7c-103">La solución Administración de procesos empresariales proporciona una forma genérica de reintentar llamar a algunos métodos de objeto con errores.</span><span class="sxs-lookup"><span data-stu-id="aec7c-103">The business process management solution provides for retrying, in a generic way, some failed object method calls.</span></span> <span data-ttu-id="aec7c-104">La solución hace esto mediante la **Recaller** objeto en el **ExceptionHandler** orquestación.</span><span class="sxs-lookup"><span data-stu-id="aec7c-104">The solution does this through the **Recaller** object in the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="aec7c-105">El **ExceptionHandler** orquestación utiliza el objeto para volver a intentar las llamadas de método de objeto.</span><span class="sxs-lookup"><span data-stu-id="aec7c-105">The **ExceptionHandler** orchestration uses the object to retry object method calls.</span></span> <span data-ttu-id="aec7c-106">Para obtener más información, consulte [la orquestación de ExceptionHandler](../core/the-exceptionhandler-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="aec7c-106">For more information, see [The ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md).</span></span>  
  
## <a name="the-invoke-method"></a><span data-ttu-id="aec7c-107">Método Invoke</span><span class="sxs-lookup"><span data-stu-id="aec7c-107">The Invoke Method</span></span>  
 <span data-ttu-id="aec7c-108">El **Recaller** objeto tiene un único método estático, **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="aec7c-108">The **Recaller** object has a single, static method, **Invoke**.</span></span> <span data-ttu-id="aec7c-109">Puesto que es estático, nunca debe crear una instancia de la **Recaller** objeto.</span><span class="sxs-lookup"><span data-stu-id="aec7c-109">Because it is static, you never need to create an instance of the **Recaller** object.</span></span> <span data-ttu-id="aec7c-110">Puede usar el **Invoke** método de tres maneras: para crear un objeto, llamar a un método estático para un objeto, o para llamar a un método no estático de un objeto.</span><span class="sxs-lookup"><span data-stu-id="aec7c-110">You can use the **Invoke** method in three ways: to construct an object, to call a static method for an object, or to call a non-static method for an object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aec7c-111">El **Invoke** método actúa como un contenedor para la **Type.InvokeMember** método en el [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="aec7c-111">The **Invoke** method serves as a wrapper for the **Type.InvokeMember** method in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
### <a name="arguments-for-the-invoke-method"></a><span data-ttu-id="aec7c-112">Argumentos del método Invoke</span><span class="sxs-lookup"><span data-stu-id="aec7c-112">Arguments for the Invoke Method</span></span>  
 <span data-ttu-id="aec7c-113">La tabla siguiente describe los argumentos para el **Invoke** método:</span><span class="sxs-lookup"><span data-stu-id="aec7c-113">The following table describes arguments for the **Invoke** method:</span></span>  
  
|<span data-ttu-id="aec7c-114">Parámetro</span><span class="sxs-lookup"><span data-stu-id="aec7c-114">Parameter</span></span>|<span data-ttu-id="aec7c-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="aec7c-115">Type</span></span>|<span data-ttu-id="aec7c-116">Description</span><span class="sxs-lookup"><span data-stu-id="aec7c-116">Description</span></span>|  
|---------------|----------|-----------------|  
|<span data-ttu-id="aec7c-117">*t*</span><span class="sxs-lookup"><span data-stu-id="aec7c-117">*t*</span></span>|<span data-ttu-id="aec7c-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="aec7c-118">**Type**</span></span>|<span data-ttu-id="aec7c-119">Tipo de objeto en el que se debe llamar el método.</span><span class="sxs-lookup"><span data-stu-id="aec7c-119">The type of the object on which to call the method.</span></span>|  
|<span data-ttu-id="aec7c-120">*obj*</span><span class="sxs-lookup"><span data-stu-id="aec7c-120">*obj*</span></span>|<span data-ttu-id="aec7c-121">**Object**</span><span class="sxs-lookup"><span data-stu-id="aec7c-121">**Object**</span></span>|<span data-ttu-id="aec7c-122">Instancia del objeto que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="aec7c-122">The instance of the object to use.</span></span>|  
|<span data-ttu-id="aec7c-123">*methodName*</span><span class="sxs-lookup"><span data-stu-id="aec7c-123">*methodName*</span></span>|<span data-ttu-id="aec7c-124">**string**</span><span class="sxs-lookup"><span data-stu-id="aec7c-124">**string**</span></span>|<span data-ttu-id="aec7c-125">El nombre del método que se invoca.</span><span class="sxs-lookup"><span data-stu-id="aec7c-125">The name of the method to invoke.</span></span>|  
|<span data-ttu-id="aec7c-126">*args*</span><span class="sxs-lookup"><span data-stu-id="aec7c-126">*args*</span></span>|<span data-ttu-id="aec7c-127">**Matriz**</span><span class="sxs-lookup"><span data-stu-id="aec7c-127">**Array**</span></span>|<span data-ttu-id="aec7c-128">Una matriz de tipo **objeto** que contiene los argumentos del método.</span><span class="sxs-lookup"><span data-stu-id="aec7c-128">An array of type **Object** containing the method's arguments.</span></span>|  
  
 <span data-ttu-id="aec7c-129">Para llamar al constructor de un objeto, use una cadena vacía ("") o **null** para *methodName*.</span><span class="sxs-lookup"><span data-stu-id="aec7c-129">To call the constructor for an object, use an empty string ("") or **null** for *methodName*.</span></span>  
  
 <span data-ttu-id="aec7c-130">Para llamar a un método estático, use **null** para *obj*.</span><span class="sxs-lookup"><span data-stu-id="aec7c-130">To call a static method, use **null** for *obj*.</span></span>  
  
 <span data-ttu-id="aec7c-131">Para llamar a un método no estático, proporcione todos los argumentos.</span><span class="sxs-lookup"><span data-stu-id="aec7c-131">To call a non-static method, supply all of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aec7c-132">Usar **null** como el valor del argumento de tipo, *t*, hace que **Invoke** para producir un **ArgumentNullException** excepción.</span><span class="sxs-lookup"><span data-stu-id="aec7c-132">Using **null** as the value of the Type argument, *t*, causes **Invoke** to throw an **ArgumentNullException** exception.</span></span> <span data-ttu-id="aec7c-133">El argumento *t* no debe ser null porque el **Invoke** método usa la **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] método.</span><span class="sxs-lookup"><span data-stu-id="aec7c-133">The argument *t* should not be null because the **Invoke** method uses the **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] method.</span></span>  
  
## <a name="calling-invoke"></a><span data-ttu-id="aec7c-134">Llamar a Invoke</span><span class="sxs-lookup"><span data-stu-id="aec7c-134">Calling Invoke</span></span>  
 <span data-ttu-id="aec7c-135">En la solución, solo el **ExceptionHandler** orquestación utiliza la **Recaller** objeto.</span><span class="sxs-lookup"><span data-stu-id="aec7c-135">In the solution, only the **ExceptionHandler** orchestration uses the **Recaller** object.</span></span> <span data-ttu-id="aec7c-136">El **ExceptionHandler** , a su vez, utiliza otras orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="aec7c-136">The **ExceptionHandler** is, in turn, used by other orchestrations.</span></span> <span data-ttu-id="aec7c-137">Los valores pasados a la **Invoke** método proceden de estas otras orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="aec7c-137">The values passed to the **Invoke** method come from these other orchestrations.</span></span> <span data-ttu-id="aec7c-138">Por ejemplo, aparece el siguiente código en el **activar** orquestación en el **InitialException** forma expresión:</span><span class="sxs-lookup"><span data-stu-id="aec7c-138">For example, the following code appears in the **Activate** orchestration in the **InitialException** Expression shape:</span></span>  
  
```  
Ex = CodeEx;  
ObjectType = orderHandler.GetType();  
CalledObject = orderHandler;  
Reason = "Standard Activate Failed";  
MethodName = "Activate";  
ParameterArray = System.Array.CreateInstance(typeof(System.Object),  
                                              3 );  
ParameterArray.SetValue(ServiceType, 0);  
ParameterArray.SetValue(OrderMsg.CustNum, 1);  
ParameterArray.SetValue(OrderMsg.OrderNum, 2);  
ReturnValue = null; // no return value expected  
  
```  
  
 <span data-ttu-id="aec7c-139">Observe cómo el código crea una matriz mediante **System.Array.CreateInstance** y usa el **SetValue** método para almacenar los valores que se usan en él.</span><span class="sxs-lookup"><span data-stu-id="aec7c-139">Notice how the code creates an array using **System.Array.CreateInstance** and uses the **SetValue** method to store the values used in it.</span></span>  
  
 <span data-ttu-id="aec7c-140">Después de la forma de expresión, la orquestación Activate llama el **ExceptionHandler** orquestación.</span><span class="sxs-lookup"><span data-stu-id="aec7c-140">After the Expression shape, the Activate orchestration calls the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="aec7c-141">En el siguiente código se muestra cómo el Diseñador de orquestaciones traduce la forma de llamada:</span><span class="sxs-lookup"><span data-stu-id="aec7c-141">The following code shows how the orchestration designer translates the Call shape:</span></span>  
  
```  
call Microsoft.Samples.  
    BizTalk.SouthridgeVideo.  
        OrderManager.ExceptionHandlerOrch  
            (  
                Reason,  
                Ex,  
                CalledObject,  
                MethodName,   
                ParameterArray,   
                OrderCorrelation,   
                OrderMsg,   
                out ReturnValue,   
                ObjectType  
            );  
  
```  
  
 <span data-ttu-id="aec7c-142">En el **ExceptionHandler** orquestación, el código siguiente aparece en el **Call Original Code** forma expresión:</span><span class="sxs-lookup"><span data-stu-id="aec7c-142">In the **ExceptionHandler** orchestration, the following code appears in the **Call Original Code** Expression shape:</span></span>  
  
```  
ReturnValue =   
    Microsoft.Samples.  
        BizTalk.SouthridgeVideo.  
            Utilities.Recaller.  
                Invoke(  
                    ObjectType,  
                    CalledObject,  
                    MethodName,  
                    ParameterArray  
                );  
```  
  
 <span data-ttu-id="aec7c-143">Observe que aunque los nombres de argumento coinciden con los de la llamada de la orquestación Activate, los argumentos coinciden por orden y no por nombre cuando se llaman las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="aec7c-143">Notice that, although the argument names match those in the Activate orchestration's call, arguments are matched by order and not by name when calling orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec7c-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="aec7c-144">See Also</span></span>  
 <span data-ttu-id="aec7c-145">[Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="aec7c-145">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="aec7c-146">La orquestación de ExceptionHandler</span><span class="sxs-lookup"><span data-stu-id="aec7c-146">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)