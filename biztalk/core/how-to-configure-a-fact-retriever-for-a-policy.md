---
title: "Cómo configurar un administrador de almacenes de una directiva | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, policies
- Business Rule Composer, facts
- policies, facts
ms.assetid: a7bcf3e5-3f28-4f0e-b112-8c97dee072a1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18572af1323de817b3c934866af917d2601332f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a><span data-ttu-id="3f5f4-102">Cómo configurar un administrador de almacenes de una directiva</span><span class="sxs-lookup"><span data-stu-id="3f5f4-102">How to Configure a Fact Retriever for a Policy</span></span>
<span data-ttu-id="3f5f4-103">Puede almacenar hechos que no cambien con frecuencia y, posteriormente, antes del primer ciclo de ejecución de la aplicación de host, puede recuperar esos hechos desde donde se encuentren almacenados, presentarlos una vez al motor de reglas para su almacenamiento en caché y volver a utilizarlos en múltiples ciclos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3f5f4-103">You can store facts that do not change frequently, and then before the first execution cycle of your host application, you can retrieve these facts from storage, present them once to the rule engine for caching, and reuse them over multiple execution cycles.</span></span>  
  
 <span data-ttu-id="3f5f4-104">Existen dos modos para asociar un administrador de almacenes de datos con una directiva.</span><span class="sxs-lookup"><span data-stu-id="3f5f4-104">There are two ways to associate a fact retriever with a policy.</span></span> <span data-ttu-id="3f5f4-105">Puede hacerlo mediante el Compositor de reglas de negocio o mediante programación utilizando la **RuleSetExecutionConfiguration** objeto.</span><span class="sxs-lookup"><span data-stu-id="3f5f4-105">You can do this by using the Business Rule Composer or programmatically by using the **RuleSetExecutionConfiguration** object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f5f4-106">Sólo se puede asociar una implementación de administrador de almacenes de datos con una versión de directiva.</span><span class="sxs-lookup"><span data-stu-id="3f5f4-106">Only one fact retriever implementation can be associated with a policy version.</span></span>  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="3f5f4-107">Para asociar un administrador de almacenes de datos con una directiva en el Compositor de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="3f5f4-107">To associate a fact retriever with a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="3f5f4-108">En la ventana Explorador de directivas, haga clic en la versión de directiva con la que desee asociar el administrador de almacenes de datos.</span><span class="sxs-lookup"><span data-stu-id="3f5f4-108">In the Policy Explorer window, click the policy version with which you want to associate the fact retriever.</span></span>  
  
2.  <span data-ttu-id="3f5f4-109">En la ventana Propiedades, haga clic en el **puntos suspensivos** botón (…) en el **FactRetriever** propiedad que se va a buscar en la caché global de ensamblados para un objeto de almacenes de datos de hechos.</span><span class="sxs-lookup"><span data-stu-id="3f5f4-109">In the Properties window, click the **ellipsis** button (…) in the **FactRetriever** property to browse in the global assembly cache for a fact retriever object.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3f5f4-110">El **puntos suspensivos** botón (...) no aparece hasta que haga clic en el **FactRetriever** fila en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="3f5f4-110">The **ellipsis** button (…) does not appear until you click the **FactRetriever** row in the Property Window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5f4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f5f4-111">See Also</span></span>  
 [<span data-ttu-id="3f5f4-112">Cómo crear un administrador de almacenes</span><span class="sxs-lookup"><span data-stu-id="3f5f4-112">How to Create a Fact Retriever</span></span>](../core/how-to-create-a-fact-retriever.md)