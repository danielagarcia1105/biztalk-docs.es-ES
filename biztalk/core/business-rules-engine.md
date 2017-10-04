---
title: Motor de reglas de negocios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Engine
- Business Rules Engine
- Business Rules Engine, rules
- Business Rules Engine, about Business Rules Engine
ms.assetid: 87b38507-9f6d-4863-88a6-9c20f15a4e55
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d99cff10324f1cf1ba97d99431524474ed5f039b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-engine"></a><span data-ttu-id="92c5d-102">motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="92c5d-102">Business Rules Engine</span></span>
<span data-ttu-id="92c5d-103">El marco de trabajo de reglas de trabajo es una biblioteca de clases compatible con Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="92c5d-103">The Business Rules Framework is a Microsoft .NET-compliant class library.</span></span> <span data-ttu-id="92c5d-104">Proporciona un motor de inferencia eficiente que puede vincular reglas de gran riqueza semántica, declarativas y muy legibles con cualquier objeto de negocios (componentes .NET), documento XML o tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="92c5d-104">It provides an efficient inference engine that can link highly readable, declarative, semantically rich rules to any business objects (.NET components), XML documents, or database tables.</span></span> <span data-ttu-id="92c5d-105">Los programadores de aplicaciones pueden crear reglas de negocio mediante la generación de reglas a partir de bloques pequeños de lógica de negocios (conjuntos de reglas pequeños) que funciones en información (hechos) incluida en objetos .NET, tablas de base de datos y documentos XML.</span><span class="sxs-lookup"><span data-stu-id="92c5d-105">Application developers can build business rules by constructing rules from small building blocks of business logic (small rule sets) that operate on information (facts) contained in .NET objects, database tables, and XML documents.</span></span> <span data-ttu-id="92c5d-106">Este patrón de diseño fomenta la reutilización de código, la sencillez del diseño y la modularidad de la lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="92c5d-106">This design pattern promotes code reuse, design simplicity, and modularity of business logic.</span></span> <span data-ttu-id="92c5d-107">Además, el motor de reglas no se impone en la arquitectura o el diseño de las aplicaciones de negocios.</span><span class="sxs-lookup"><span data-stu-id="92c5d-107">In addition, the rule engine does not impose on the architecture or design of business applications.</span></span> <span data-ttu-id="92c5d-108">De hecho, se puede agregar tecnología de reglas a una aplicación de negocios mediante la invocación directa del motor de reglas o bien mediante la lógica externa que invoque los objetos de negocios sin modificarlos.</span><span class="sxs-lookup"><span data-stu-id="92c5d-108">In fact, you can add rule technology to a business application by directly invoking the rule engine, or you can have external logic that invokes your business objects without modifying them.</span></span> <span data-ttu-id="92c5d-109">En resumen, la tecnología permite a los programadores crear y mantener aplicaciones con el mínimo de esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="92c5d-109">In short, the technology enables developers to create and maintain applications with minimal effort.</span></span>  
  
 <span data-ttu-id="92c5d-110">Al planear el desarrollo de una aplicación basada en reglas, debe determinar primero cómo se ajustarán las reglas a sus procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="92c5d-110">In planning development of a rule-based application, you first need to determine how rules will fit into your business processes.</span></span> <span data-ttu-id="92c5d-111">La aplicación creará una instancia de una directiva y le suministrará datos, o hechos, en los que funcionar.</span><span class="sxs-lookup"><span data-stu-id="92c5d-111">Your application will create an instance of a policy and supply it with data, or facts, on which to operate.</span></span> <span data-ttu-id="92c5d-112">El objeto de directiva encapsula el motor de reglas y suministra un único punto de entrada a través del que ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="92c5d-112">The policy object encapsulates the rule engine and provides a single point of entry through which to run it.</span></span>  
  
 <span data-ttu-id="92c5d-113">También debe planear el desarrollo y la realización de pruebas de su diseño de reglas.</span><span class="sxs-lookup"><span data-stu-id="92c5d-113">You also will need to plan for the development and testing of your rules design.</span></span> <span data-ttu-id="92c5d-114">Debe considerar cómo va a implementar y actualizar sus directivas.</span><span class="sxs-lookup"><span data-stu-id="92c5d-114">You must consider how you are going to deploy and update your policies.</span></span> <span data-ttu-id="92c5d-115">Debería realizar un seguimiento del progreso de la ejecución de su motor de reglas y la supervisión de su estado actual.</span><span class="sxs-lookup"><span data-stu-id="92c5d-115">You will likely want to track the progress of your rule engine's execution and monitor its current state.</span></span>  
  
 <span data-ttu-id="92c5d-116">Tenga en cuenta los siguientes pasos a la hora de planear el desarrollo de sus reglas:</span><span class="sxs-lookup"><span data-stu-id="92c5d-116">Account for the following steps as you plan your rules development:</span></span>  
  
1.  <span data-ttu-id="92c5d-117">Planee cómo incorporar sus reglas en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="92c5d-117">Plan how to incorporate your rules into your application.</span></span>  
  
2.  <span data-ttu-id="92c5d-118">Identifique la lógica de negocios que desea representar con reglas en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="92c5d-118">Identify the business logic that you want to represent with rules in your application.</span></span> <span data-ttu-id="92c5d-119">El término "lógica de negocios" puede hacer referencia a varios conceptos. Un ejemplo de lógica de negocios sería "Los pedidos de compra por valor de más de quinientos dólares deben ser aprobados por un supervisor".</span><span class="sxs-lookup"><span data-stu-id="92c5d-119">The term "business logic" can refer to many things; an example of business logic is "Purchase orders for more than five hundred dollars must be approved by a manager."</span></span>  
  
3.  <span data-ttu-id="92c5d-120">Identifique los orígenes de datos para los elementos de su regla.</span><span class="sxs-lookup"><span data-stu-id="92c5d-120">Identify data sources for your rule elements.</span></span> <span data-ttu-id="92c5d-121">También puede definir y publicar vocabularios (nomenclatura específica de dominio que representa los enlaces subyacentes)..</span><span class="sxs-lookup"><span data-stu-id="92c5d-121">You can optionally define and publish vocabularies (domain-specific nomenclature that represents underlying bindings).</span></span>  
  
4.  <span data-ttu-id="92c5d-122">Defina reglas a partir de definiciones de vocabulario o directamente desde enlaces de datos y, a partir de estos, componga una directiva que represente su lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="92c5d-122">Define rules from vocabulary definitions or directly from data bindings, and from them compose a policy that represents your business logic.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92c5d-123">Para poder aplicarse en las reglas, los vocabularios deben publicarse.</span><span class="sxs-lookup"><span data-stu-id="92c5d-123">Vocabularies must be published before they can be applied in rules.</span></span>  
  
5.  <span data-ttu-id="92c5d-124">Pruebe y depure la directiva con hechos de prueba.</span><span class="sxs-lookup"><span data-stu-id="92c5d-124">Test and debug the policy with sample facts.</span></span> <span data-ttu-id="92c5d-125">Puede usar la funcionalidad de directiva de prueba en el Compositor de reglas de negocios o usar **directiva** o **PolicyTester** clases para ejecutar desde una aplicación, el programa de línea de comandos o la orquestación.</span><span class="sxs-lookup"><span data-stu-id="92c5d-125">You can either use the Test Policy functionality in the Business Rule Composer or use **Policy** or **PolicyTester** classes to execute from an application, command-line program, or orchestration.</span></span>  
  
6.  <span data-ttu-id="92c5d-126">Publique la versión de la directiva en el almacén de reglas.</span><span class="sxs-lookup"><span data-stu-id="92c5d-126">Publish the policy version to the rule store.</span></span>  
  
7.  <span data-ttu-id="92c5d-127">Implemente la versión de la directiva.</span><span class="sxs-lookup"><span data-stu-id="92c5d-127">Deploy the policy version.</span></span>  
  
8.  <span data-ttu-id="92c5d-128">Cree una instancia y genere la lista de hechos a corto plazo en la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="92c5d-128">Instantiate and build the short-term fact list in the hosting application.</span></span> <span data-ttu-id="92c5d-129">Use la **reglas de llamada** forma de una orquestación para ejecutar la directiva empresarial o crear una instancia de una versión de directiva en la aplicación host mediante programación.</span><span class="sxs-lookup"><span data-stu-id="92c5d-129">Use the **Call Rules** shape in an orchestration to execute your business policy or programmatically instantiate a policy version in your hosting application.</span></span>  
  
9. <span data-ttu-id="92c5d-130">Supervise y realice un seguimiento de la ejecución de reglas si es necesario.</span><span class="sxs-lookup"><span data-stu-id="92c5d-130">Monitor and track rule execution as needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92c5d-131">El interceptor de seguimiento predeterminado funciona con orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="92c5d-131">The default tracking interceptor works with orchestrations.</span></span> <span data-ttu-id="92c5d-132">Si su aplicación host no es una orquestación, deberá escribir su propio interceptor de seguimiento para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="92c5d-132">If your hosting application is not an orchestration, you must write your own tracking interceptor to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92c5d-133">En esta sección</span><span class="sxs-lookup"><span data-stu-id="92c5d-133">In This Section</span></span>  
  
-   [<span data-ttu-id="92c5d-134">Reglas</span><span class="sxs-lookup"><span data-stu-id="92c5d-134">Rules</span></span>](../core/rules.md)  
  
-   [<span data-ttu-id="92c5d-135">Directivas</span><span class="sxs-lookup"><span data-stu-id="92c5d-135">Policies</span></span>](../core/policies.md)  
  
-   [<span data-ttu-id="92c5d-136">Vocabularios</span><span class="sxs-lookup"><span data-stu-id="92c5d-136">Vocabularies</span></span>](../core/vocabularies.md)  
  
-   [<span data-ttu-id="92c5d-137">Arquitectura del marco de trabajo de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="92c5d-137">Business Rules Framework Architecture</span></span>](../core/business-rules-framework-architecture.md)  
  
-   [<span data-ttu-id="92c5d-138">Hechos</span><span class="sxs-lookup"><span data-stu-id="92c5d-138">Facts</span></span>](../core/facts.md)  
  
-   [<span data-ttu-id="92c5d-139">Motor de reglas</span><span class="sxs-lookup"><span data-stu-id="92c5d-139">Rule Engine</span></span>](../core/rule-engine.md)