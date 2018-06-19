---
title: La clase del Administrador de resolución (ResolverMgr) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89fa551d-0aca-4777-adbc-2bc46ab8664a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6621ad0c6b9edb5bf93950f9b9d05a7655f0e36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294748"
---
# <a name="the-resolver-manager-resolvermgr-class"></a>La clase del Administrador de resolución (ResolverMgr)
La transformación y el uso de servicios de mensajería de enrutamiento la **ResolverMgr** clase para realizar la resolución. La transformación dinámica ESB y agentes de entrega dinámica también usan el **ResolverManager** clase para realizar la resolución de just-in-time (JIT).  
  
 El instalador de ESB Core instala y registra el **Microsoft.Practices.ESB.Resolver.dll** ensamblado con el **ResolverMgr** clase en la memoria caché global de ensamblados.  
  
 Puede utilizar esta clase en su propio código donde necesite realizar resolución dinámica de los puntos de conexión o asignaciones. También puede extender esta clase para utilizar un método de resolución personalizada. Sin embargo, tenga en cuenta que la clase ya es compatible con un mecanismo de resolución que puede utilizar cualquier ensamblado de resolución personalizada, que debe dar cabida a cualquier algoritmo de solución alternativa es posible que necesite.  
  
 En el ejemplo de código siguiente se muestra cómo utilizar el **ResolverMgr** clase para resolver un punto de conexión.  
  
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
  
 Normalmente, la cadena de conexión de resolución especifica los valores de propiedad para la resolución de al menos un método, como una directiva de reglas, ensamblado personalizado, instrucción XPath o Universal Description, Discovery y Integration (UDDI) el nombre de etiqueta y el servidor. Por último, devuelve un objeto de diccionario con una colección de hechos de resolución, que se pueden rellenar fácilmente con los hechos personalizados de una resolución concreta.  
  
 Para obtener más información sobre cómo funciona el mecanismo de resolución ESB, consulte [utilizando resolución dinámica y enrutamiento](../esb-toolkit/using-dynamic-resolution-and-routing.md).