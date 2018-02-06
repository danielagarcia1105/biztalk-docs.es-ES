---
title: Crear reglas mediante el Compositor de reglas de negocios | Documentos de Microsoft
ms.custom: 
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0600a2b2-36a2-4496-8ba1-c5f6e2fa4760
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74a4ccb0a4cdb7592dabfeb4dae96530c04cea38
ms.sourcegitcommit: 78376935362715684b451eb6da9f2b1e8c129c2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="create-business-rules-using-the-business-rule-composer"></a><span data-ttu-id="1cdb0-102">Crear reglas de negocios mediante el Compositor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="1cdb0-102">Create Business Rules Using the Business Rule Composer</span></span>

## <a name="overview"></a><span data-ttu-id="1cdb0-103">Información general</span><span class="sxs-lookup"><span data-stu-id="1cdb0-103">Overview</span></span>
<span data-ttu-id="1cdb0-104">El Compositor de reglas de negocio le permite crear directivas empresariales con una o varias reglas de negocio, así como implementar dichas directivas.</span><span class="sxs-lookup"><span data-stu-id="1cdb0-104">The Business Rule Composer allows you to create business policies with one or more business rules, and it allows you to deploy these policies.</span></span> <span data-ttu-id="1cdb0-105">También le permite buscar hechos (XML, base de datos y .NET) y usar los hechos en reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="1cdb0-105">It also allows you to browse for facts (XML, database, and .NET), and use the facts in business rules.</span></span> <span data-ttu-id="1cdb0-106">Además, le permite crear vocabularios de empresa basados en hechos, así como usar los vocabularios en reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="1cdb0-106">In addition, it allows you to create business vocabularies based on facts, and to use the vocabularies in business rules.</span></span>  
  
 <span data-ttu-id="1cdb0-107">En esta sección se proporciona información específica de tarea sobre el uso del Compositor de reglas de negocio para crear reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="1cdb0-107">This section provides task-specific information about using the Business Rule Composer to create business rules.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1cdb0-108">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1cdb0-108">Next steps</span></span>
  
-   [<span data-ttu-id="1cdb0-109">Iniciar el Compositor de reglas de negocio y cargar una directiva</span><span class="sxs-lookup"><span data-stu-id="1cdb0-109">Start the Business Rule Composer and Load a Policy</span></span>](../core/how-to-start-the-business-rule-composer-and-load-a-policy.md)  
  
-   [<span data-ttu-id="1cdb0-110">Ventanas del compositor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="1cdb0-110">Windows of the Business Rule Composer</span></span>](../core/windows-of-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="1cdb0-111">Selección de hechos</span><span class="sxs-lookup"><span data-stu-id="1cdb0-111">Selecting Facts</span></span>](../core/selecting-facts.md)  
  
-   [<span data-ttu-id="1cdb0-112">Crear directivas y reglas</span><span class="sxs-lookup"><span data-stu-id="1cdb0-112">Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)  
  
-   [<span data-ttu-id="1cdb0-113">Modificar reglas</span><span class="sxs-lookup"><span data-stu-id="1cdb0-113">Modify Rules</span></span>](../core/how-to-modify-rules.md)  
  
-   [<span data-ttu-id="1cdb0-114">Mantener versiones de directivas</span><span class="sxs-lookup"><span data-stu-id="1cdb0-114">Maintain Policy Versions</span></span>](../core/how-to-maintain-policy-versions.md)  
  
-   [<span data-ttu-id="1cdb0-115">Configurar un administrador de almacenes de datos para una directiva</span><span class="sxs-lookup"><span data-stu-id="1cdb0-115">Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)  
  
-   [<span data-ttu-id="1cdb0-116">Desarrollar vocabularios</span><span class="sxs-lookup"><span data-stu-id="1cdb0-116">Develop Vocabularies</span></span>](../core/how-to-develop-vocabularies.md)  
  
-   [<span data-ttu-id="1cdb0-117">Controlar valores Null y DBNull</span><span class="sxs-lookup"><span data-stu-id="1cdb0-117">Handle Null and DBNull</span></span>](../core/how-to-handle-null-and-dbnull.md)  
  
-   [<span data-ttu-id="1cdb0-118">Analizar varios objetos del mismo tipo en una regla de negocio</span><span class="sxs-lookup"><span data-stu-id="1cdb0-118">Analyze Multiple Objects of the Same Type in a Business Rule</span></span>](../core/how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule.md)  
  
-   [<span data-ttu-id="1cdb0-119">Probar las directivas</span><span class="sxs-lookup"><span data-stu-id="1cdb0-119">Testing Policies</span></span>](../core/testing-policies.md)  
  
-   [<span data-ttu-id="1cdb0-120">mplementar y anular la implementación de directivas y vocabularios</span><span class="sxs-lookup"><span data-stu-id="1cdb0-120">eploy and Undeploy Policies and Vocabularies</span></span>](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)  
  
-   [<span data-ttu-id="1cdb0-121">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="1cdb0-121">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)  
  
-   [<span data-ttu-id="1cdb0-122">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="1cdb0-122">Logical Operators</span></span>](../core/logical-operators.md)  
  
-   [<span data-ttu-id="1cdb0-123">Invocar una directiva desde otra directiva</span><span class="sxs-lookup"><span data-stu-id="1cdb0-123">Invoke a Policy from Another Policy</span></span>](../core/invoking-a-policy-from-another-policy.md)  
  
-   [<span data-ttu-id="1cdb0-124">Devolver un valor True o False desde una directiva</span><span class="sxs-lookup"><span data-stu-id="1cdb0-124">Return True or False from a Policy</span></span>](../core/how-to-return-true-or-false-from-a-policy.md)
