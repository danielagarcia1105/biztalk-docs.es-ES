---
title: Tipos de variables de orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 34990be2-35b6-40ec-b107-42a1c7b45aca
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d3128d8cb3298dbab7e2394d55f6c2d6ff6ac3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971741"
---
# <a name="orchestration-variable-types"></a><span data-ttu-id="af843-102">Tipos de variables de orquestación</span><span class="sxs-lookup"><span data-stu-id="af843-102">Orchestration Variable Types</span></span>
<span data-ttu-id="af843-103">Puede declarar variables de los tipos predefinidos siguientes:</span><span class="sxs-lookup"><span data-stu-id="af843-103">You can declare variables of the following predefined types:</span></span>  

|||||  
|-|-|-|-|  
|<span data-ttu-id="af843-104">boolean</span><span class="sxs-lookup"><span data-stu-id="af843-104">boolean</span></span>|<span data-ttu-id="af843-105">byte</span><span class="sxs-lookup"><span data-stu-id="af843-105">byte</span></span>|<span data-ttu-id="af843-106">char</span><span class="sxs-lookup"><span data-stu-id="af843-106">char</span></span>|<span data-ttu-id="af843-107">DATETIME</span><span class="sxs-lookup"><span data-stu-id="af843-107">datetime</span></span>|  
|<span data-ttu-id="af843-108">Decimal</span><span class="sxs-lookup"><span data-stu-id="af843-108">decimal</span></span>|<span data-ttu-id="af843-109">double</span><span class="sxs-lookup"><span data-stu-id="af843-109">double</span></span>|<span data-ttu-id="af843-110">int16</span><span class="sxs-lookup"><span data-stu-id="af843-110">int16</span></span>|<span data-ttu-id="af843-111">int32</span><span class="sxs-lookup"><span data-stu-id="af843-111">int32</span></span>|  
|<span data-ttu-id="af843-112">int64</span><span class="sxs-lookup"><span data-stu-id="af843-112">int64</span></span>|<span data-ttu-id="af843-113">long</span><span class="sxs-lookup"><span data-stu-id="af843-113">long</span></span>|<span data-ttu-id="af843-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="af843-114">sbyte</span></span>|<span data-ttu-id="af843-115">sola</span><span class="sxs-lookup"><span data-stu-id="af843-115">single</span></span>|  
|<span data-ttu-id="af843-116">string</span><span class="sxs-lookup"><span data-stu-id="af843-116">string</span></span>|<span data-ttu-id="af843-117">timespan</span><span class="sxs-lookup"><span data-stu-id="af843-117">timespan</span></span>|<span data-ttu-id="af843-118">uint16</span><span class="sxs-lookup"><span data-stu-id="af843-118">uint16</span></span>|<span data-ttu-id="af843-119">uint32</span><span class="sxs-lookup"><span data-stu-id="af843-119">uint32</span></span>|  
|<span data-ttu-id="af843-120">uint64</span><span class="sxs-lookup"><span data-stu-id="af843-120">uint64</span></span>||||  

 <span data-ttu-id="af843-121">También puede declarar variables de algunos tipos basados en .NET a los que se hace referencia en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="af843-121">You can also declare variables of any .NET-based types that are referenced in your project.</span></span>  

## <a name="considerations-for-declare-orchestration-variables"></a><span data-ttu-id="af843-122">Consideraciones para declarar variables de orquestación</span><span class="sxs-lookup"><span data-stu-id="af843-122">Considerations for Declare Orchestration Variables</span></span>  
 <span data-ttu-id="af843-123">Cuando declare variables de orquestación, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af843-123">When declare orchestration variables, consider the following:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="af843-124"> propiedades de contexto con varios valores de es compatible con determinados enrutamiento por contenidos escenarios, pero no pueden usar estas propiedades en las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="af843-124"> supports multivalued context properties for certain content-based routing scenarios, but you cannot use such properties in orchestrations.</span></span>  

- <span data-ttu-id="af843-125">Para que se admitan la suspensión y la rehidratación de las orquestaciones, todas las variables de orquestación deben ser almacenar su estado de forma persistente.</span><span class="sxs-lookup"><span data-stu-id="af843-125">In order to support suspension and re-hydration of orchestrations, all orchestration variables must be capable of having their state persisted.</span></span>  <span data-ttu-id="af843-126">Normalmente, esto se consigue por el tipo o clase de la variable que sea serializable o que permita secuencias.</span><span class="sxs-lookup"><span data-stu-id="af843-126">Typically, this is accomplished by the variable's type or class being serializable or streamable.</span></span>  

- <span data-ttu-id="af843-127">Estos tipos basados en .NET (clases) deben ser clases serializables.</span><span class="sxs-lookup"><span data-stu-id="af843-127">These .NET-based types (classes) must be serializable classes.</span></span>  <span data-ttu-id="af843-128">Pueden implementar esto al ser declarados con el atributo “[Serializable]” o al implementar de forma explícita la interfaz .NET ISerializable (en el espacio de nombres System.Runtime.Serialization).</span><span class="sxs-lookup"><span data-stu-id="af843-128">They may either implement this by being declared with the "[Serializable]” attribute or by explicitly implementing the ISerializable .NET interface (in the System.Runtime.Serialization namespace).</span></span>  

- <span data-ttu-id="af843-129">Si el tipo basado en .NET es realmente un contenedor al que se puede llamar en tiempo de ejecución (RCW) de un componente COM subyacente, ese componente debe implementar las interfaces necesarias para que el RCW sea una clase de .NET serializable (por ejemplo, IPersistStream, IPersistStreamInit).</span><span class="sxs-lookup"><span data-stu-id="af843-129">If the .NET-based type is actually a runtime callable wrapper (RCW) of an underlying COM component, then that COM component must implement the interface(s) required for the RCW to be a serializable .NET class (e.g. IPersistStream, IPersistStreamInit).</span></span>  

- <span data-ttu-id="af843-130">Debido a que los tipos basados en .NET (o de COM subyacente) se ejecutan dentro del flujo de una orquestación, los métodos de estos tipos no deben retrasar la ejecución de la orquestación (por ejemplo, a través de la contención de recursos, etc.).</span><span class="sxs-lookup"><span data-stu-id="af843-130">Because any .NET-based (or underlying COM) types are executing within the flow of an orchestration, methods in these types must not delay execution of the orchestration (e.g. through contention for resources, etc.).</span></span>  <span data-ttu-id="af843-131">Y todo uso que estas implementaciones de tipos hagan de los recursos afectará a la instancia de host en la que se ejecute la orquestación que llama.</span><span class="sxs-lookup"><span data-stu-id="af843-131">And any consumption of resources by these type implementations will affect the host instance in which the calling orchestration runs.</span></span>
