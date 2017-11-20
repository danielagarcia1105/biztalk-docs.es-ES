---
title: "Sintaxis para una instrucción EXEC en Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d18481b206b1be7e0062762c1844305fc36e10f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a><span data-ttu-id="714d5-102">Sintaxis para una instrucción EXEC en Siebel</span><span class="sxs-lookup"><span data-stu-id="714d5-102">Syntax for an EXEC Statement in Siebel</span></span>
<span data-ttu-id="714d5-103">Mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], los clientes ADO.NET también pueden realizar una operación de EXEC en la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="714d5-103">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], ADO.NET clients can also perform an EXEC operation on the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="714d5-104">La sintaxis de la instrucción EXEC es:</span><span class="sxs-lookup"><span data-stu-id="714d5-104">The syntax for the EXEC statement is:</span></span>  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
\<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 <span data-ttu-id="714d5-105">En la sintaxis anterior, `\<value 1..n>` representa un conjunto de parámetros sin nombre.</span><span class="sxs-lookup"><span data-stu-id="714d5-105">In the preceding syntax, `\<value 1..n>` represents a set of unnamed parameters.</span></span> <span data-ttu-id="714d5-106">Éstos son valores codificados de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="714d5-106">These are hard-coded values.</span></span> <span data-ttu-id="714d5-107">Normalmente representan en parámetros.</span><span class="sxs-lookup"><span data-stu-id="714d5-107">They usually represent IN parameters.</span></span>  <span data-ttu-id="714d5-108">También pueden representar parámetros INOUT.</span><span class="sxs-lookup"><span data-stu-id="714d5-108">They can also represent INOUT parameters.</span></span> <span data-ttu-id="714d5-109">Sin embargo, si se usa un valor codificado de forma rígida para un parámetro de entrada, el valor de salida asociado a ese parámetro no se puede recuperar después de ejecuta la instrucción EXEC.</span><span class="sxs-lookup"><span data-stu-id="714d5-109">However, if a hard-coded value is used for an INOUT parameter, the output value associated with that parameter cannot be retrieved after the EXEC statement is executed.</span></span>  
  
 <span data-ttu-id="714d5-110">El `@parameter 1..n` sintaxis representa un conjunto de parámetros con nombre, que pueden ser IN, INOUT, o los parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="714d5-110">The `@parameter 1..n` syntax represents a set of named parameters, which can be IN, INOUT, or OUT parameters.</span></span> <span data-ttu-id="714d5-111">Los parámetros de salida deben ir seguidos por el **salida** palabra clave.</span><span class="sxs-lookup"><span data-stu-id="714d5-111">The output parameters must be followed by the **OUTPUT** keyword.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="714d5-112">El **salida** palabra clave solo debe utilizarse con los parámetros de salida y no con parámetros INOUT.</span><span class="sxs-lookup"><span data-stu-id="714d5-112">The **OUTPUT** keyword must only be used with OUT parameters and not with INOUT parameters.</span></span>  
  
 <span data-ttu-id="714d5-113">Para especificar valores de parámetro en línea, use la `@parameter 1..n = <value>` sintaxis.</span><span class="sxs-lookup"><span data-stu-id="714d5-113">To specify parameter values inline, use the `@parameter 1..n = <value>` syntax.</span></span>  
  
 <span data-ttu-id="714d5-114">Todos los parámetros deben ser separados por comas.</span><span class="sxs-lookup"><span data-stu-id="714d5-114">All parameters must be comma-separated.</span></span>  
  
 <span data-ttu-id="714d5-115">Los siguientes son ejemplos de instrucciones EXEC:</span><span class="sxs-lookup"><span data-stu-id="714d5-115">The following are examples of EXEC statements:</span></span>  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="714d5-116">Cada nombre de parámetro (como `@In` en el ejemplo anterior) debe coincidir con el nombre del argumento correspondiente en el método de servicio empresarial de Siebel.</span><span class="sxs-lookup"><span data-stu-id="714d5-116">Every parameter name (like `@In` in the preceding example) must match the corresponding argument name in the Siebel Business Service method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714d5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="714d5-117">See Also</span></span>  
 [<span data-ttu-id="714d5-118">Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness</span><span class="sxs-lookup"><span data-stu-id="714d5-118">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)