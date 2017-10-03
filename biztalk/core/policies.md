---
title: Directivas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, policies
- policies, about policies
- policies, deploying
- policies, Business Rules Engine
- policies
- business rules, policies
- policies, versioning
- policies, testing
- policies, creating
- policies, updating
ms.assetid: 2e0ae081-938d-4e2a-947e-1c0ecfebb4b8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd05d6cf67d89ee811cac45ac3950697db74f59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="policies"></a><span data-ttu-id="14d11-102">Directivas</span><span class="sxs-lookup"><span data-stu-id="14d11-102">Policies</span></span>
<span data-ttu-id="14d11-103">Una directiva es una agrupación lógica de reglas.</span><span class="sxs-lookup"><span data-stu-id="14d11-103">A policy is a logical grouping of rules.</span></span> <span data-ttu-id="14d11-104">Componga una versión de una directiva, guárdela, pruébela aplicándola a datos y, cuando esté satisfecho con los resultados, publíquela e impleméntela en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="14d11-104">You compose a version of a policy, save it, test it by applying it to facts, and, when you are satisfied with the results, publish it and deploy it to a production environment.</span></span>  
  
## <a name="policy-composition"></a><span data-ttu-id="14d11-105">Composición de directivas</span><span class="sxs-lookup"><span data-stu-id="14d11-105">Policy Composition</span></span>  
 <span data-ttu-id="14d11-106">Puede componer directivas en el Compositor de reglas de negocio mediante la construcción de reglas basadas en datos y definiciones.</span><span class="sxs-lookup"><span data-stu-id="14d11-106">You can compose policies in the Business Rule Composer by constructing rules from facts and definitions.</span></span> <span data-ttu-id="14d11-107">Una directiva puede contener un conjunto de reglas arbitrariamente grande, pero normalmente una directiva se crea a partir de reglas pertenecientes a un dominio de negocio específico dentro del contexto de la aplicación que utilizará la directiva.</span><span class="sxs-lookup"><span data-stu-id="14d11-107">A policy can contain an arbitrarily large set of rules, but typically you compose a policy from rules that pertain to a specific business domain within the context of the application that will be using the policy.</span></span>  
  
## <a name="policy-testing"></a><span data-ttu-id="14d11-108">Comprobar directivas</span><span class="sxs-lookup"><span data-stu-id="14d11-108">Policy Testing</span></span>  
 <span data-ttu-id="14d11-109">Puede realizar de forma eficaz una ejecución de prueba de la directiva antes de publicarla e implementarla en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="14d11-109">You can effectively perform a test run of your policy before it is published and deployed in a production environment.</span></span> <span data-ttu-id="14d11-110">El Compositor de reglas de negocio permite suministrar instancias de datos a una directiva, ejecutarla y ver su resultado.</span><span class="sxs-lookup"><span data-stu-id="14d11-110">The Business Rule Composer allows you to supply instances of facts to a policy, run the policy, and view its output.</span></span> <span data-ttu-id="14d11-111">El resultado incluye la actividad de datos, la ejecución de reglas, la evaluación de condiciones y las actualizaciones a la agenda.</span><span class="sxs-lookup"><span data-stu-id="14d11-111">The output includes fact activity, rule execution, condition evaluation, and updates to the agenda.</span></span>  
  
## <a name="policy-versions"></a><span data-ttu-id="14d11-112">Versiones de directivas</span><span class="sxs-lookup"><span data-stu-id="14d11-112">Policy Versions</span></span>  
 <span data-ttu-id="14d11-113">Después de haber definido todas las reglas en la directiva, puede publicar esta versión.</span><span class="sxs-lookup"><span data-stu-id="14d11-113">After you have defined all the rules in your policy, you can publish the policy version.</span></span> <span data-ttu-id="14d11-114">De esta forma, la directiva queda bloqueada y su comportamiento está bien definido.</span><span class="sxs-lookup"><span data-stu-id="14d11-114">In this way the policy is locked down, and its behavior is well-defined.</span></span>  
  
 <span data-ttu-id="14d11-115">La versión de una directiva puede utilizarse bajo una serie de circunstancias en el entorno empresarial y sustituirse por otra versión cuando cambien dichas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="14d11-115">A given policy version can be used under a given set of circumstances in your business environment, and replaced by another version when those circumstances change.</span></span> <span data-ttu-id="14d11-116">Además, distintas aplicaciones pueden utilizar simultáneamente tanto la versión antigua como la nueva.</span><span class="sxs-lookup"><span data-stu-id="14d11-116">Also, both new and old versions can be used simultaneously by different applications.</span></span>  
  
## <a name="policy-deployment"></a><span data-ttu-id="14d11-117">Implementación de directivas</span><span class="sxs-lookup"><span data-stu-id="14d11-117">Policy Deployment</span></span>  
 <span data-ttu-id="14d11-118">Cuando la directiva está preparada para ejecutarse en un entorno de producción, puede implementarla para que esté disponible para una aplicación host.</span><span class="sxs-lookup"><span data-stu-id="14d11-118">When your policy is ready to be run in a production environment, you can deploy it to make it available to a hosting application.</span></span>  
  
## <a name="dynamic-policy-updates"></a><span data-ttu-id="14d11-119">Actualizaciones dinámicas de directivas</span><span class="sxs-lookup"><span data-stu-id="14d11-119">Dynamic Policy Updates</span></span>  
 <span data-ttu-id="14d11-120">Las actualizaciones dinámicas de directivas le permiten modificar directivas independientemente de un proceso comercial que se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="14d11-120">Dynamic policy updates allow you to modify policies independently of a running business process.</span></span> <span data-ttu-id="14d11-121">Puede crear e implementar una versión actualizada de la directiva y la aplicación host puede incorporar la actualización casi en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="14d11-121">You can create and deploy an updated version of the policy, and the hosting application can incorporate the update in near real time.</span></span> <span data-ttu-id="14d11-122">Esta actualización no requiere que cambie ningún código y, por tanto, se evita tener que volver a desarrollar la aplicación una y otra vez.</span><span class="sxs-lookup"><span data-stu-id="14d11-122">This update does not require you to change any code, and thus you can avoid the overhead of redeveloping and redeploying the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d11-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="14d11-123">See Also</span></span>  
 [<span data-ttu-id="14d11-124">Motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="14d11-124">Business Rules Engine</span></span>](../core/business-rules-engine.md)