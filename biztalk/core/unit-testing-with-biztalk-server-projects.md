---
title: Pruebas unitarias con proyectos de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2594f29-fc34-4dda-9316-2afd4e0056d7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da7147f4c2500946fb97c47592a2a4a35d3dcf62
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="unit-testing-with-biztalk-server-projects"></a><span data-ttu-id="55d53-102">Pruebas de unidades con proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="55d53-102">Unit Testing with BizTalk Server Projects</span></span>
<span data-ttu-id="55d53-103">BizTalk Server introdujo un característica que se puede habilitar en de pruebas unitarias la **implementación** página de propiedades de un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="55d53-103">BizTalk Server introduced a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="55d53-104">Captura de pantalla siguiente muestra esta configuración del proyecto que se tiene acceso desde el Diseñador de proyectos cuando haga clic en un proyecto y haga clic en el **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="55d53-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click the **Properties**.</span></span>  
  
 <span data-ttu-id="55d53-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span><span class="sxs-lookup"><span data-stu-id="55d53-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span></span>  
  
 <span data-ttu-id="55d53-106">**Captura de pantalla de la pestaña implementación en el Diseñador de proyectos que expone la propiedad de proyecto habilitar pruebas de unidades.**</span><span class="sxs-lookup"><span data-stu-id="55d53-106">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property.**</span></span>  
  
 <span data-ttu-id="55d53-107">Esta característica permite crear pruebas de unidades para los esquemas, asignaciones y canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="55d53-107">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="55d53-108">Los temas de esta sección proporcionan algunos métodos de ejemplo sobre cómo usar la característica de prueba de unidades.</span><span class="sxs-lookup"><span data-stu-id="55d53-108">The topics in this section provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="55d53-109">Si se habilita esta característica y se vuelve a generar el proyecto, las clases de artefacto se derivan de las siguientes clases base para admitir las pruebas de unidades.</span><span class="sxs-lookup"><span data-stu-id="55d53-109">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="55d53-110">Tipo de artefacto</span><span class="sxs-lookup"><span data-stu-id="55d53-110">Artifact type</span></span>|<span data-ttu-id="55d53-111">Clase base</span><span class="sxs-lookup"><span data-stu-id="55d53-111">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="55d53-112">esquema</span><span class="sxs-lookup"><span data-stu-id="55d53-112">Schema</span></span>|<span data-ttu-id="55d53-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="55d53-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="55d53-114">Mapa</span><span class="sxs-lookup"><span data-stu-id="55d53-114">Map</span></span>|<span data-ttu-id="55d53-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="55d53-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="55d53-116">Canalización</span><span class="sxs-lookup"><span data-stu-id="55d53-116">Pipeline</span></span>|<span data-ttu-id="55d53-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="55d53-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="55d53-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="55d53-118">In This Section</span></span>  
  
-   [<span data-ttu-id="55d53-119">Uso de la característica con esquemas y asignaciones de pruebas de unidades</span><span class="sxs-lookup"><span data-stu-id="55d53-119">Using the Unit Testing Feature with Schemas and Maps</span></span>](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [<span data-ttu-id="55d53-120">Uso de la característica con canalizaciones de pruebas de unidades</span><span class="sxs-lookup"><span data-stu-id="55d53-120">Using the Unit Testing Feature with Pipelines</span></span>](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a><span data-ttu-id="55d53-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="55d53-121">Related Sections</span></span>  
 [<span data-ttu-id="55d53-122">Trabajar con pruebas unitarias (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="55d53-122">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)