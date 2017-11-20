---
title: "La clase del Administrador de resolución (ResolverMgr) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89fa551d-0aca-4777-adbc-2bc46ab8664a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6621ad0c6b9edb5bf93950f9b9d05a7655f0e36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-manager-resolvermgr-class"></a><span data-ttu-id="e72f1-102">La clase del Administrador de resolución (ResolverMgr)</span><span class="sxs-lookup"><span data-stu-id="e72f1-102">The Resolver Manager (ResolverMgr) Class</span></span>
<span data-ttu-id="e72f1-103">La transformación y el uso de servicios de mensajería de enrutamiento la **ResolverMgr** clase para realizar la resolución.</span><span class="sxs-lookup"><span data-stu-id="e72f1-103">The Transform and Routing messaging services use the **ResolverMgr** class to perform resolution.</span></span> <span data-ttu-id="e72f1-104">La transformación dinámica ESB y agentes de entrega dinámica también usan el **ResolverManager** clase para realizar la resolución de just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="e72f1-104">The ESB dynamic transformation and dynamic delivery agents also use the **ResolverManager** class to perform just-in-time (JIT) resolution.</span></span>  
  
 <span data-ttu-id="e72f1-105">El instalador de ESB Core instala y registra el **Microsoft.Practices.ESB.Resolver.dll** ensamblado con el **ResolverMgr** clase en la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e72f1-105">The ESB Core installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with the **ResolverMgr** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="e72f1-106">Puede utilizar esta clase en su propio código donde necesite realizar resolución dinámica de los puntos de conexión o asignaciones.</span><span class="sxs-lookup"><span data-stu-id="e72f1-106">You can use this class in your own code where you need to perform dynamic resolution of endpoints or maps.</span></span> <span data-ttu-id="e72f1-107">También puede extender esta clase para utilizar un método de resolución personalizada.</span><span class="sxs-lookup"><span data-stu-id="e72f1-107">You can also extend this class to use a custom resolution method.</span></span> <span data-ttu-id="e72f1-108">Sin embargo, tenga en cuenta que la clase ya es compatible con un mecanismo de resolución que puede utilizar cualquier ensamblado de resolución personalizada, que debe dar cabida a cualquier algoritmo de solución alternativa es posible que necesite.</span><span class="sxs-lookup"><span data-stu-id="e72f1-108">However, keep in mind that the class already supports a resolution mechanism that can use any custom resolver assembly, which should accommodate any alternative resolution algorithm you may require.</span></span>  
  
 <span data-ttu-id="e72f1-109">En el ejemplo de código siguiente se muestra cómo utilizar el **ResolverMgr** clase para resolver un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e72f1-109">The following code example shows how to use the **ResolverMgr** class to resolve an endpoint.</span></span>  
  
```csharp  
// Move to retrieve the first resolver.  
resolvers = itineraryStep.ResolverCollection;  
resolver = resolvers.Current;  
  
// Pass the resolver configuration to the Resolver Manager for resolution.  
resolverDictionary = Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage, resolver);  
  
// Set transport properties.  
transportLocation = resolverDictionary.Item("Resolver.TransportLocation");  
transportType = resolverDictionary.Item("Resolver.TransportType");  
```  
  
 <span data-ttu-id="e72f1-110">Normalmente, la cadena de conexión de resolución especifica los valores de propiedad para la resolución de al menos un método, como una directiva de reglas, ensamblado personalizado, instrucción XPath o Universal Description, Discovery y Integration (UDDI) el nombre de etiqueta y el servidor.</span><span class="sxs-lookup"><span data-stu-id="e72f1-110">Usually, your resolver connection string specifies the property values for at least one resolution method, such as a rules policy, custom assembly, XPath statement, or Universal Description, Discovery, and Integration (UDDI) label and server name.</span></span> <span data-ttu-id="e72f1-111">Por último, devuelve un objeto de diccionario con una colección de hechos de resolución, que se pueden rellenar fácilmente con los hechos personalizados de una resolución concreta.</span><span class="sxs-lookup"><span data-stu-id="e72f1-111">Finally, it returns a dictionary object with a collection of resolver facts, which can be easily populated with custom facts from a concrete resolver.</span></span>  
  
 <span data-ttu-id="e72f1-112">Para obtener más información sobre cómo funciona el mecanismo de resolución ESB, consulte [utilizando resolución dinámica y enrutamiento](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e72f1-112">For more information about how the ESB resolution mechanism works, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>