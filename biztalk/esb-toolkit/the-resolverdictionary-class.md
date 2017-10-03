---
title: La clase ResolverDictionary | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46deb8a0-0523-4a5c-ac6b-45c506de7a72
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dfe0082ffc7f7b68c5c56811a28d5ccd20e93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolverdictionary-class"></a><span data-ttu-id="6ad80-102">La clase ResolverDictionary</span><span class="sxs-lookup"><span data-stu-id="6ad80-102">The ResolverDictionary Class</span></span>
<span data-ttu-id="6ad80-103">El **ResolverDictionary** clase es un **diccionario**-según la clase que puede almacenar instancias de la **resolución** de clase como **cadena** nombre / pares de valor.</span><span class="sxs-lookup"><span data-stu-id="6ad80-103">The **ResolverDictionary** class is a **Dictionary**-based class that can store instances of the **Resolver** class as **String** name/value pairs.</span></span> <span data-ttu-id="6ad80-104">Cuando se crean instancias de la **ResolverDictionary** (clase), debe proporcionar una referencia a un archivo **diccionario** instancia.</span><span class="sxs-lookup"><span data-stu-id="6ad80-104">When creating instances of the **ResolverDictionary** class, you must provide a reference to an existing **Dictionary** instance.</span></span> <span data-ttu-id="6ad80-105">El **ResolverDictionary** clase proporciona los datos que la **resolución** clase utiliza mientras se realiza la resolución de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6ad80-105">The **ResolverDictionary** class provides the data that the **Resolver** class uses when it performs run-time resolution.</span></span>  
  
 <span data-ttu-id="6ad80-106">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer instala y registra el **Microsoft.Practices.ESB.Resolver.dll** ensamblado con el **ResolverDictionary** clase en la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6ad80-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with the **ResolverDictionary** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="6ad80-107">El **ResolverDictionary** clase expone un método y una propiedad:</span><span class="sxs-lookup"><span data-stu-id="6ad80-107">The **ResolverDictionary** class exposes one method and one property:</span></span>  
  
-   <span data-ttu-id="6ad80-108">**Elemento (** clave **)**.</span><span class="sxs-lookup"><span data-stu-id="6ad80-108">**Item(** key **)**.</span></span> <span data-ttu-id="6ad80-109">Este método toma un valor de cadena que contiene un nombre de clave.</span><span class="sxs-lookup"><span data-stu-id="6ad80-109">This method takes a string value that contains a key name.</span></span> <span data-ttu-id="6ad80-110">Devuelve el valor correspondiente de la cadena o una cadena vacía si el elemento no existe en subyacente **diccionario** instancia.</span><span class="sxs-lookup"><span data-stu-id="6ad80-110">It returns the corresponding string value or an empty string if the item does not exist in the underlying **Dictionary** instance.</span></span>  
  
-   <span data-ttu-id="6ad80-111">**BaseDictionary**.</span><span class="sxs-lookup"><span data-stu-id="6ad80-111">**BaseDictionary**.</span></span> <span data-ttu-id="6ad80-112">Esta propiedad devuelve una referencia a subyacente **diccionario** instancia.</span><span class="sxs-lookup"><span data-stu-id="6ad80-112">This property returns a reference to the underlying **Dictionary** instance.</span></span>