---
title: "La clase de resolución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1359bcbb9c6c918fc0ee6d5e67bacb8e3559c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-class"></a><span data-ttu-id="7c19d-102">La clase de resolución</span><span class="sxs-lookup"><span data-stu-id="7c19d-102">The Resolver Class</span></span>
<span data-ttu-id="7c19d-103">El **resolución** clase es una estructura simple que expone un par nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="7c19d-103">The **Resolver** class is a simple structure that exposes a name/value pair.</span></span> <span data-ttu-id="7c19d-104">El servicio Web de resolución, devuelve una colección genérica de instancias de esta clase de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="7c19d-104">The Resolver Web service returns a generic collection of instances of this class from its methods.</span></span>  
  
 <span data-ttu-id="7c19d-105">El instalador de ESB Core instala y registra el **Microsoft.Practices.ESB.Resolver.dll** ensamblado con la clase de resolución de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7c19d-105">The ESB Core installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with Resolver class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="7c19d-106">El uso de un nombre/valor basada en diccionario aproximarse hace más fácil agregar nuevos elementos en el futuro libera y reduce el tamaño del resultado de la resolución al evitar la inclusión de propiedades no pertinentes que varían en función del método de resolución y el tipo de resolución actual.</span><span class="sxs-lookup"><span data-stu-id="7c19d-106">The use of a dictionary-based name/value approach makes it easier to add new items in future releases and minimizes the size of the resolution result by avoiding inclusion of non-relevant properties that depend on the resolution method and the current resolver type.</span></span>  
  
 <span data-ttu-id="7c19d-107">El **resolución** clase expone dos propiedades:</span><span class="sxs-lookup"><span data-stu-id="7c19d-107">The **Resolver** class exposes two properties:</span></span>  
  
-   <span data-ttu-id="7c19d-108">**Nombre**.</span><span class="sxs-lookup"><span data-stu-id="7c19d-108">**Name**.</span></span> <span data-ttu-id="7c19d-109">Este es el nombre de un par de nombre/valor que contiene información que se devuelve después de que se resuelve una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="7c19d-109">This is the name of a name/value pair that contains information that is returned after a connection string is resolved.</span></span>  
  
-   <span data-ttu-id="7c19d-110">**Valor**.</span><span class="sxs-lookup"><span data-stu-id="7c19d-110">**Value**.</span></span> <span data-ttu-id="7c19d-111">Este es el valor que corresponde al nombre del par nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="7c19d-111">This is the value that corresponds to the name of the name/value pair.</span></span>