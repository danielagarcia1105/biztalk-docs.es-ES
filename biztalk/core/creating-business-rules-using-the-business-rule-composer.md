---
title: Crear reglas de negocio mediante el Compositor de reglas de negocios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, business rules
- business rules, creating
ms.assetid: 0600a2b2-36a2-4496-8ba1-c5f6e2fa4760
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5b1281acab139159dd837f63cf80af56d388c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-business-rules-using-the-business-rule-composer"></a><span data-ttu-id="5bc2a-102">Crear reglas de negocio mediante el Compositor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="5bc2a-102">Creating Business Rules Using the Business Rule Composer</span></span>
<span data-ttu-id="5bc2a-103">El Compositor de reglas de negocio le permite crear directivas empresariales con una o varias reglas de negocio, así como implementar dichas directivas.</span><span class="sxs-lookup"><span data-stu-id="5bc2a-103">The Business Rule Composer allows you to create business policies with one or more business rules, and it allows you to deploy these policies.</span></span> <span data-ttu-id="5bc2a-104">También le permite buscar hechos (XML, base de datos y .NET) y usar los hechos en reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="5bc2a-104">It also allows you to browse for facts (XML, database, and .NET), and use the facts in business rules.</span></span> <span data-ttu-id="5bc2a-105">Además, le permite crear vocabularios de empresa basados en hechos, así como usar los vocabularios en reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="5bc2a-105">In addition, it allows you to create business vocabularies based on facts, and to use the vocabularies in business rules.</span></span>  
  
 <span data-ttu-id="5bc2a-106">En esta sección se proporciona información específica de tarea sobre el uso del Compositor de reglas de negocio para crear reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="5bc2a-106">This section provides task-specific information about using the Business Rule Composer to create business rules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bc2a-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5bc2a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="5bc2a-108">Cómo iniciar el Compositor de reglas de negocio y cargar una directiva</span><span class="sxs-lookup"><span data-stu-id="5bc2a-108">How to Start the Business Rule Composer and Load a Policy</span></span>](../core/how-to-start-the-business-rule-composer-and-load-a-policy.md)  
  
-   [<span data-ttu-id="5bc2a-109">Ventanas del compositor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="5bc2a-109">Windows of the Business Rule Composer</span></span>](../core/windows-of-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="5bc2a-110">Seleccionar hechos</span><span class="sxs-lookup"><span data-stu-id="5bc2a-110">Selecting Facts</span></span>](../core/selecting-facts.md)  
  
-   [<span data-ttu-id="5bc2a-111">Cómo crear directivas y reglas</span><span class="sxs-lookup"><span data-stu-id="5bc2a-111">How to Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)  
  
-   [<span data-ttu-id="5bc2a-112">Cómo modificar reglas</span><span class="sxs-lookup"><span data-stu-id="5bc2a-112">How to Modify Rules</span></span>](../core/how-to-modify-rules.md)  
  
-   [<span data-ttu-id="5bc2a-113">Cómo mantener versiones de directivas</span><span class="sxs-lookup"><span data-stu-id="5bc2a-113">How to Maintain Policy Versions</span></span>](../core/how-to-maintain-policy-versions.md)  
  
-   [<span data-ttu-id="5bc2a-114">Cómo configurar un administrador de almacenes de una directiva</span><span class="sxs-lookup"><span data-stu-id="5bc2a-114">How to Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)  
  
-   [<span data-ttu-id="5bc2a-115">Cómo desarrollar vocabularios</span><span class="sxs-lookup"><span data-stu-id="5bc2a-115">How to Develop Vocabularies</span></span>](../core/how-to-develop-vocabularies.md)  
  
-   [<span data-ttu-id="5bc2a-116">Cómo controlar valores Null y DBNull</span><span class="sxs-lookup"><span data-stu-id="5bc2a-116">How to Handle Null and DBNull</span></span>](../core/how-to-handle-null-and-dbnull.md)  
  
-   [<span data-ttu-id="5bc2a-117">Cómo analizar varios objetos del mismo tipo en una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="5bc2a-117">How to Analyze Multiple Objects of the Same Type in a Business Rule</span></span>](../core/how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule.md)  
  
-   [<span data-ttu-id="5bc2a-118">Probar las directivas</span><span class="sxs-lookup"><span data-stu-id="5bc2a-118">Testing Policies</span></span>](../core/testing-policies.md)  
  
-   [<span data-ttu-id="5bc2a-119">Cómo implementar y anular la implementación de directivas y vocabularios</span><span class="sxs-lookup"><span data-stu-id="5bc2a-119">How to Deploy and Undeploy Policies and Vocabularies</span></span>](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)  
  
-   [<span data-ttu-id="5bc2a-120">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="5bc2a-120">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)  
  
-   [<span data-ttu-id="5bc2a-121">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="5bc2a-121">Logical Operators</span></span>](../core/logical-operators.md)  
  
-   [<span data-ttu-id="5bc2a-122">Invocar una directiva desde otra directiva</span><span class="sxs-lookup"><span data-stu-id="5bc2a-122">Invoking a Policy from Another Policy</span></span>](../core/invoking-a-policy-from-another-policy.md)  
  
-   [<span data-ttu-id="5bc2a-123">Cómo se devuelven True o False de una directiva</span><span class="sxs-lookup"><span data-stu-id="5bc2a-123">How to Return True or False from a Policy</span></span>](../core/how-to-return-true-or-false-from-a-policy.md)