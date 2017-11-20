---
title: Tipos de datos de XLANG-s | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- Orchestration Designer, managing data
- Orchestration Designer, variables
- orchestrations, variables
- Orchestration Designer, expressions
ms.assetid: 5b08aaa6-1533-4bac-a76d-f9162e39bf4f
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c21ed77c5fdd56485514d17ed75e921c63a56212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-data-types"></a><span data-ttu-id="a1bb4-102">Tipos de datos de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="a1bb4-102">XLANG-s Data Types</span></span>
<span data-ttu-id="a1bb4-103">XLANG/s define los tipos de valores estándar que son un reflejo de sus homólogos en C#.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-103">XLANG/s defines standard value types that are reflections of their C# counterparts.</span></span> <span data-ttu-id="a1bb4-104">Puede tratarse de **booleano**, **bytes**, **Char**, **Decimal**, **doble**, **Int16** , **Int32**, **Int64**, **SByte**, **único**, **cadena**,  **UInt16**, **UInt32**, y **UInt64**.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-104">These include **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**.</span></span> <span data-ttu-id="a1bb4-105">XLANG/s admite matrices unidimensionales, pero no literales de matriz.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-105">XLANG/s supports single-dimensional arrays, but does not support array literals.</span></span>  
  
 <span data-ttu-id="a1bb4-106">XLANG/s también ofrece una gran compatibilidad con el control de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-106">XLANG/s also has rich support for message handling.</span></span> <span data-ttu-id="a1bb4-107">Los mensajes pueden basarse en esquemas, clases .NET, tipos de mensajes Web (WSDL) o tipos de mensajes complejos.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-107">Messages can be based on schemas, .NET classes, Web message types (WSDL), or complex message types.</span></span> <span data-ttu-id="a1bb4-108">XLANG/s admite lo siguientes tipos de datos complejos:</span><span class="sxs-lookup"><span data-stu-id="a1bb4-108">XLANG/s supports the following complex data types:</span></span>  
  
-   <span data-ttu-id="a1bb4-109">**MessageType.**</span><span class="sxs-lookup"><span data-stu-id="a1bb4-109">**messagetype.**</span></span> <span data-ttu-id="a1bb4-110">este tipo de datos define los tipos de mensajes con varias partes que se definen como combinaciones de elementos de datos, mensajes basados en XSD y tipos de método-mensaje (mensajes que coinciden con el formato de firma de un método de una clase o interfaz).</span><span class="sxs-lookup"><span data-stu-id="a1bb4-110">This data type defines multipart message types which are defined as combinations of data elements and XSD-based messages and Method-Message types (messages that match the signature format of a method of a class or interface).</span></span>  
  
-   <span data-ttu-id="a1bb4-111">**portType.**</span><span class="sxs-lookup"><span data-stu-id="a1bb4-111">**porttype.**</span></span> <span data-ttu-id="a1bb4-112">este tipo de datos define una colección de operaciones de puertos sobre la que puede actuar una instancia de puerto de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-112">This data type defines a collection of port operations that a port instance of that type can act upon.</span></span>  
  
-   <span data-ttu-id="a1bb4-113">**correlationsettype.**</span><span class="sxs-lookup"><span data-stu-id="a1bb4-113">**correlationsettype.**</span></span> <span data-ttu-id="a1bb4-114">este tipo de datos define los datos que se usarán en cualquier instancia de una variable de conjuntos de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-114">This data type defines the data that will be used in any instance of a correlation set variable.</span></span> <span data-ttu-id="a1bb4-115">Los datos de los conjuntos de correlaciones son el mecanismo de enrutamiento utilizado para garantizar que los mensajes que se desplazan por el sistema se entregan a la instancia en ejecución adecuada de un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-115">Correlation set data is the routing mechanism used to ensure that messages moving through the system are dispatched to the appropriate running instance of a business process.</span></span> <span data-ttu-id="a1bb4-116">Por ejemplo, si se envía un pedido a un socio comercial para su procesamiento, resulta fundamental que se invoque la instancia correcta del proceso empresarial en el momento de su devolución.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-116">For example, if a purchase order is sent to a trading partner for processing, it is imperative that the correct instance of the business process corresponding to that purchase order be invoked on its return.</span></span>  
  
-   <span data-ttu-id="a1bb4-117">**servicelinktype.**</span><span class="sxs-lookup"><span data-stu-id="a1bb4-117">**servicelinktype.**</span></span> <span data-ttu-id="a1bb4-118">Este tipo de datos define el conjunto de **porttype** valores que forman un grupo de puertos utilizados en un proceso empresarial lógicamente coherente.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-118">This data type defines the set of **porttype** values that form a logically consistent group of ports used in a business process.</span></span> <span data-ttu-id="a1bb4-119">El uso de vínculos de servicios constituye un mecanismo eficaz que permite la asignación dinámica a un grupo de puertos en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-119">The use of service links is a powerful mechanism that allows dynamic assignment to a group of ports at run time.</span></span> <span data-ttu-id="a1bb4-120">Esto permite definir un proceso empresarial único que puede utilizarse para interactuar con varios socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="a1bb4-120">This allows you to define a single business process that can be used to interact with multiple trading partners.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bb4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1bb4-121">See Also</span></span>  
 <span data-ttu-id="a1bb4-122">[Instrucciones de XLANG-s](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="a1bb4-122">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="a1bb4-123">[Operadores y Variables de XLANG-s](../core/xlang-s-variables-and-operators.md) </span><span class="sxs-lookup"><span data-stu-id="a1bb4-123">[XLANG-s Variables and Operators](../core/xlang-s-variables-and-operators.md) </span></span>  
 <span data-ttu-id="a1bb4-124">[Expresiones de XLANG-s](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="a1bb4-124">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="a1bb4-125">[Palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="a1bb4-125">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="a1bb4-126">XLANG-s para las conversiones de tipo de BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="a1bb4-126">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)