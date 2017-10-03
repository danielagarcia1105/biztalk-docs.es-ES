---
title: "Apéndice A: métodos de interfaz de componente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cb5b87cb063f22c889291b8eff3b2be50d64a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-a-component-interface-methods"></a><span data-ttu-id="6a7d5-102">Apéndice A: métodos de interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="6a7d5-102">Appendix A: Component Interface Methods</span></span>
<span data-ttu-id="6a7d5-103">El adaptador de Microsoft para PeopleSoft Enterprise proporciona métodos estándar para las interfaces de componentes.</span><span class="sxs-lookup"><span data-stu-id="6a7d5-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise provides standard methods for component interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a7d5-104">El parámetro `interactiveMode`, de la versión Ex de los métodos, proporciona asistencia a la hora de depurar una llamada al servidor (`Create/CreateEx`, `Update/UpdateEx`, and `DeleteOnly`).</span><span class="sxs-lookup"><span data-stu-id="6a7d5-104">The `interactiveMode` parameter, in the Ex-version of the methods, assists in debugging a call to the back-end (`Create/CreateEx`, `Update/UpdateEx`, and `DeleteOnly`).</span></span> <span data-ttu-id="6a7d5-105">La llamada al servidor de cada elemento del método *Ex se efectúa de forma independiente, de manera que es posible saber exactamente en qué elemento se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="6a7d5-105">Each item in the *Ex call to the back-end is called separately, so you know exactly which item failed.</span></span> <span data-ttu-id="6a7d5-106">Hay una disminución del rendimiento cuando se usa un \*Ex método porque el elemento de la propiedad recibe una llamada independiente.</span><span class="sxs-lookup"><span data-stu-id="6a7d5-106">There is a decrease in performance when you use an \*Ex method because each property's item receives a separate call.</span></span> <span data-ttu-id="6a7d5-107">Se pueden desarrollar con \*Ex método y a continuación, cambie al método main (por ejemplo, `Create`) para la producción.</span><span class="sxs-lookup"><span data-stu-id="6a7d5-107">You can develop with \*Ex method and then switch to the main method (for example, `Create`) for production.</span></span> <span data-ttu-id="6a7d5-108">También puede utilizar un modificador de depuración en producción para cambiar entre usar el método y la \*Ex método.</span><span class="sxs-lookup"><span data-stu-id="6a7d5-108">You can also use a debug switch at production to switch between using the method and the \*Ex method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a7d5-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6a7d5-109">In This Section</span></span>  
  
-   [<span data-ttu-id="6a7d5-110">Método CreateEx</span><span class="sxs-lookup"><span data-stu-id="6a7d5-110">CreateEx Method</span></span>](../core/createex-method.md)  
  
-   [<span data-ttu-id="6a7d5-111">Método DeleteOnly</span><span class="sxs-lookup"><span data-stu-id="6a7d5-111">DeleteOnly Method</span></span>](../core/deleteonly-method.md)  
  
-   [<span data-ttu-id="6a7d5-112">Find (método)</span><span class="sxs-lookup"><span data-stu-id="6a7d5-112">Find Method</span></span>](../core/find-method.md)  
  
-   [<span data-ttu-id="6a7d5-113">Get (método)</span><span class="sxs-lookup"><span data-stu-id="6a7d5-113">Get Method</span></span>](../core/get-method.md)  
  
-   [<span data-ttu-id="6a7d5-114">Método UpdateEx</span><span class="sxs-lookup"><span data-stu-id="6a7d5-114">UpdateEx Method</span></span>](../core/updateex-method.md)  
  
-   [<span data-ttu-id="6a7d5-115">Métodos de definidos por el usuario de interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="6a7d5-115">Component Interface User-Defined Methods</span></span>](../core/component-interface-user-defined-methods.md)  
  
-   [<span data-ttu-id="6a7d5-116">Propiedades de fecha efectiva</span><span class="sxs-lookup"><span data-stu-id="6a7d5-116">Effective Date Properties</span></span>](../core/effective-date-properties.md)