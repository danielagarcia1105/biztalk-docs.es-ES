---
title: Sintaxis para una instrucción EXEC en Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4db9ca810860ea64ffa474725dc485fecfaa5e78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963082"
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a><span data-ttu-id="36dad-102">Sintaxis para una instrucción EXEC en Siebel</span><span class="sxs-lookup"><span data-stu-id="36dad-102">Syntax for an EXEC Statement in Siebel</span></span>
<span data-ttu-id="36dad-103">Mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], los clientes ADO.NET también pueden realizar una operación de EXEC en la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36dad-103">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], ADO.NET clients can also perform an EXEC operation on the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="36dad-104">La sintaxis de la instrucción EXEC es:</span><span class="sxs-lookup"><span data-stu-id="36dad-104">The syntax for the EXEC statement is:</span></span>  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 <span data-ttu-id="36dad-105">En la sintaxis anterior, `\<value 1..n\>` representa un conjunto de parámetros sin nombre.</span><span class="sxs-lookup"><span data-stu-id="36dad-105">In the preceding syntax, `\<value 1..n\>` represents a set of unnamed parameters.</span></span> <span data-ttu-id="36dad-106">Éstos son valores codificados de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="36dad-106">These are hard-coded values.</span></span> <span data-ttu-id="36dad-107">Normalmente representan en parámetros.</span><span class="sxs-lookup"><span data-stu-id="36dad-107">They usually represent IN parameters.</span></span>  <span data-ttu-id="36dad-108">También pueden representar parámetros INOUT.</span><span class="sxs-lookup"><span data-stu-id="36dad-108">They can also represent INOUT parameters.</span></span> <span data-ttu-id="36dad-109">Sin embargo, si se usa un valor codificado de forma rígida para un parámetro de entrada, el valor de salida asociado a ese parámetro no se puede recuperar después de ejecuta la instrucción EXEC.</span><span class="sxs-lookup"><span data-stu-id="36dad-109">However, if a hard-coded value is used for an INOUT parameter, the output value associated with that parameter cannot be retrieved after the EXEC statement is executed.</span></span>  
  
 <span data-ttu-id="36dad-110">El `@parameter 1..n` sintaxis representa un conjunto de parámetros con nombre, que pueden ser IN, INOUT, o los parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="36dad-110">The `@parameter 1..n` syntax represents a set of named parameters, which can be IN, INOUT, or OUT parameters.</span></span> <span data-ttu-id="36dad-111">Los parámetros de salida deben ir seguidos por el **salida** palabra clave.</span><span class="sxs-lookup"><span data-stu-id="36dad-111">The output parameters must be followed by the **OUTPUT** keyword.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36dad-112">El **salida** palabra clave solo debe utilizarse con los parámetros de salida y no con parámetros INOUT.</span><span class="sxs-lookup"><span data-stu-id="36dad-112">The **OUTPUT** keyword must only be used with OUT parameters and not with INOUT parameters.</span></span>  
  
 <span data-ttu-id="36dad-113">Para especificar valores de parámetro en línea, use la `@parameter 1..n = <value>` sintaxis.</span><span class="sxs-lookup"><span data-stu-id="36dad-113">To specify parameter values inline, use the `@parameter 1..n = <value>` syntax.</span></span>  
  
 <span data-ttu-id="36dad-114">Todos los parámetros deben ser separados por comas.</span><span class="sxs-lookup"><span data-stu-id="36dad-114">All parameters must be comma-separated.</span></span>  
  
 <span data-ttu-id="36dad-115">Los siguientes son ejemplos de instrucciones EXEC:</span><span class="sxs-lookup"><span data-stu-id="36dad-115">The following are examples of EXEC statements:</span></span>  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="36dad-116">Cada nombre de parámetro (como `@In` en el ejemplo anterior) debe coincidir con el nombre del argumento correspondiente en el método de servicio empresarial de Siebel.</span><span class="sxs-lookup"><span data-stu-id="36dad-116">Every parameter name (like `@In` in the preceding example) must match the corresponding argument name in the Siebel Business Service method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36dad-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="36dad-117">See Also</span></span>  
 [<span data-ttu-id="36dad-118">Usar el proveedor de datos de .NET Framework para aplicaciones de negocio electrónico de Siebel</span><span class="sxs-lookup"><span data-stu-id="36dad-118">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)