---
title: Creación y uso de las reglas de negocios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Editor
- Business Rules Editor
ms.assetid: a15fd09b-ff4e-4c26-8cb6-5ffd258a2182
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9d01e5eaf96c6490c68424fd09e297e0e60ef9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979397"
---
# <a name="creating-and-using-business-rules"></a><span data-ttu-id="82833-102">Crear y usar reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="82833-102">Creating and Using Business Rules</span></span>
<span data-ttu-id="82833-103">Las reglas de negocios (o las directivas empresariales) definen y controlan la estructura, el funcionamiento y la estrategia de una organización.</span><span class="sxs-lookup"><span data-stu-id="82833-103">Business rules (or business policies) define and control the structure, operation, and strategy of an organization.</span></span> <span data-ttu-id="82833-104">Las reglas de negocios pueden estar formalmente definidas en manuales de procedimiento, contratos o acuerdos, o bien pueden existir como conocimiento o experiencia que tienen los empleados.</span><span class="sxs-lookup"><span data-stu-id="82833-104">Business rules may be formally defined in procedure manuals, contracts, or agreements, or may exist as knowledge or expertise embodied in employees.</span></span> <span data-ttu-id="82833-105">Las reglas de negocios son dinámicas, están sujetas a cambios en el tiempo y pueden encontrarse en todo tipo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="82833-105">Business rules are dynamic and subject to change over time, and can be found in all types of applications.</span></span> <span data-ttu-id="82833-106">Finanzas y seguros, negocio electrónico, transporte, telecomunicaciones, servicios basados en Web y personalización son solo algunos de los muchos ámbitos de negocio que controlan las reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="82833-106">Finance and insurance, e-business, transportation, telecommunications, Web-based services, and personalization are just a few of the many business domains that are governed by business rules.</span></span> <span data-ttu-id="82833-107">Todos estos ámbitos de negocio comparten la necesidad de transmitir estrategias, directivas y regulaciones empresariales al personal de tecnologías de la información (TI) para su inclusión en aplicaciones de software.</span><span class="sxs-lookup"><span data-stu-id="82833-107">Each of these business domains shares the need to convey business strategies, policies, and regulations to information technology (IT) personnel for inclusion into software applications.</span></span>  
  
 <span data-ttu-id="82833-108">Los lenguajes de programación orientada a objetos o de procedimiento tradicional, como C, C++ y Microsoft Visual Basic, están orientados a los programadores.</span><span class="sxs-lookup"><span data-stu-id="82833-108">Traditional procedural and object-oriented programming languages, such as C, C++, and Microsoft Visual Basic, are oriented towards programmers.</span></span> <span data-ttu-id="82833-109">Incluso los lenguajes avanzados de programación orientada a objetos, como Java y C#, siguen siendo principalmente lenguajes de programadores.</span><span class="sxs-lookup"><span data-stu-id="82833-109">Even advanced object-oriented languages, such as Java and C#, are still primarily programmers' languages.</span></span> <span data-ttu-id="82833-110">El ciclo de desarrollo tradicional de software basado en diseño, desarrollo, compilación y comprobación requiere mucho tiempo y coordinación, y no permite a quienes no son programadores participar en el mantenimiento de directivas empresariales automatizadas.</span><span class="sxs-lookup"><span data-stu-id="82833-110">The traditional software development cycle of design, develop, compile, and test requires substantial time and coordination, and does not enable nonprogrammers to participate in the maintenance of automated business policies.</span></span> <span data-ttu-id="82833-111">El marco de trabajo de reglas de negocios corrige este problema, facilitando un entorno de desarrollo que permite la rápida creación de aplicaciones sin el extenso ciclo de programación tradicional de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="82833-111">The Business Rules Framework addresses this problem by providing a development environment that allows rapid application creation without the lengthy cycle of traditional application programming.</span></span> <span data-ttu-id="82833-112">Por ejemplo, las directivas empresariales que se construyen en este marco de trabajo pueden actualizarse sin necesidad de volver a compilar o implementar las orquestaciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="82833-112">For example, business policies constructed by using this framework can be updated without recompiling and redeploying the associated orchestrations.</span></span>  
  
 <span data-ttu-id="82833-113">El marco de trabajo de reglas de negocios está directamente integrado en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y los programadores pueden usar las siguientes características para generar y administrar reglas de negocios:</span><span class="sxs-lookup"><span data-stu-id="82833-113">The Business Rules Framework is tightly integrated with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and developers can use the following features to build and manage business rules:</span></span>  
  
- <span data-ttu-id="82833-114">Un motor de reglas de alto rendimiento que implementa un mecanismo de inferencia para evaluar las reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="82833-114">A high-performance rule engine that implements an inference mechanism to evaluate the business rules.</span></span>  
  
- <span data-ttu-id="82833-115">Un amplio conjunto de interfaces de programación de aplicaciones (API) para desarrollar aplicaciones basadas en reglas.</span><span class="sxs-lookup"><span data-stu-id="82833-115">A rich set of application programming interfaces (APIs) for developing rule-based applications.</span></span>  
  
- <span data-ttu-id="82833-116">Una interfaz de usuario gráfica, el Compositor de reglas de negocio, que los programadores, los analistas de negocios y los administradores pueden usar de varias maneras para desarrollar y aplicar eficazmente las reglas y directivas.</span><span class="sxs-lookup"><span data-stu-id="82833-116">A graphical user interface, the Business Rule Composer, which developers, business analysts, and administrators can use in various ways to efficiently develop and apply rules and policies.</span></span>  
  
- <span data-ttu-id="82833-117">Una perfecta integración con las orquestaciones de BizTalk, lo que permite invocar una directiva empresarial o un conjunto de reglas de negocios desde una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="82833-117">A seamless integration with BizTalk orchestrations, which enables you to invoke a business policy or a set of business rules from a BizTalk orchestration.</span></span>  
  
- <span data-ttu-id="82833-118">El Asistente para implementar el motor de reglas, que permite importar o exportar rápidamente reglas de negocios o los vocabularios que utilizan las reglas, así como implementar o anular la implementación de esas reglas.</span><span class="sxs-lookup"><span data-stu-id="82833-118">The Rule Engine Deployment Wizard, which enables you to rapidly import or export business rules or the vocabularies used by the rules, as well as to deploy or undeploy these rules.</span></span>  
  
  <span data-ttu-id="82833-119">Las reglas de negocios (o las directivas empresariales) creadas en el marco de trabajo de reglas de negocios se pueden usar en un proceso empresarial de orquestaciones, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="82833-119">The business rules (policy) you create by using the Business Rules Framework can be used in an orchestrated business process, as shown in the following figure.</span></span>  
  
  <span data-ttu-id="82833-120">![Diagrama que muestra una directiva empresarial en proceso. ] (../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")</span><span class="sxs-lookup"><span data-stu-id="82833-120">![Diagram showing buisness policy in process.](../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")</span></span>  
  <span data-ttu-id="82833-121">Directiva empresarial</span><span class="sxs-lookup"><span data-stu-id="82833-121">Business Policy</span></span>  
  
  <span data-ttu-id="82833-122">Esta sección proporciona información conceptual acerca de cómo puede aprovechar el marco de trabajo de reglas de negocios y usar las herramientas que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona para desarrollar reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="82833-122">This section provides conceptual information about how you can leverage the Business Rules Framework and use the tools that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides to develop business rules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82833-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="82833-123">In This Section</span></span>  
  
-   [<span data-ttu-id="82833-124">Creación de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="82833-124">Creating Business Rules</span></span>](../core/creating-business-rules-using-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="82833-125">Seguridad del marco de trabajo de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="82833-125">Business Rules Framework Security</span></span>](../core/business-rules-framework-security.md)  
  
-   [<span data-ttu-id="82833-126">Programación con el marco de trabajo de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="82833-126">Programming with Business Rules Framework</span></span>](../core/programming-with-business-rules-framework.md)  
  
-   [<span data-ttu-id="82833-127">Parámetros de configuración y ajuste del motor de reglas</span><span class="sxs-lookup"><span data-stu-id="82833-127">Rule Engine Configuration and Tuning Parameters</span></span>](../core/rule-engine-configuration-and-tuning-parameters.md)