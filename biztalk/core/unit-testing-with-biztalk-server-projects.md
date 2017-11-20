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
ms.openlocfilehash: 15f73b9c343e62e0a0a83bf76f8c762b9ce9ede9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unit-testing-with-biztalk-server-projects"></a><span data-ttu-id="8a6b1-102">Pruebas de unidades con proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8a6b1-102">Unit Testing with BizTalk Server Projects</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="8a6b1-103">introdujo una unidad de probar la característica que se puede habilitar en el **implementación** página de propiedades de un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8a6b1-103"> introduced a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="8a6b1-104">Captura de pantalla siguiente muestra esta configuración del proyecto que se tiene acceso desde el Diseñador de proyectos cuando haga clic en un proyecto y haga clic en el **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8a6b1-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click the **Properties**.</span></span>  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 <span data-ttu-id="8a6b1-105">**Captura de pantalla de la pestaña implementación en el Diseñador de proyectos que expone la propiedad de proyecto habilitar pruebas de unidades.**</span><span class="sxs-lookup"><span data-stu-id="8a6b1-105">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property.**</span></span>  
  
 <span data-ttu-id="8a6b1-106">Esta característica permite crear pruebas de unidades para los esquemas, asignaciones y canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="8a6b1-106">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="8a6b1-107">Los temas de esta sección proporcionan algunos métodos de ejemplo sobre cómo usar la característica de prueba de unidades.</span><span class="sxs-lookup"><span data-stu-id="8a6b1-107">The topics in this section provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="8a6b1-108">Si se habilita esta característica y se vuelve a generar el proyecto, las clases de artefacto se derivan de las siguientes clases base para admitir las pruebas de unidades.</span><span class="sxs-lookup"><span data-stu-id="8a6b1-108">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="8a6b1-109">Tipo de artefacto</span><span class="sxs-lookup"><span data-stu-id="8a6b1-109">Artifact type</span></span>|<span data-ttu-id="8a6b1-110">Clase base</span><span class="sxs-lookup"><span data-stu-id="8a6b1-110">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="8a6b1-111">esquema</span><span class="sxs-lookup"><span data-stu-id="8a6b1-111">Schema</span></span>|<span data-ttu-id="8a6b1-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="8a6b1-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="8a6b1-113">Mapa</span><span class="sxs-lookup"><span data-stu-id="8a6b1-113">Map</span></span>|<span data-ttu-id="8a6b1-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="8a6b1-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="8a6b1-115">Canalización</span><span class="sxs-lookup"><span data-stu-id="8a6b1-115">Pipeline</span></span>|<span data-ttu-id="8a6b1-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="8a6b1-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="8a6b1-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8a6b1-117">In This Section</span></span>  
  
-   [<span data-ttu-id="8a6b1-118">Uso de la característica con esquemas y asignaciones de pruebas de unidades</span><span class="sxs-lookup"><span data-stu-id="8a6b1-118">Using the Unit Testing Feature with Schemas and Maps</span></span>](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [<span data-ttu-id="8a6b1-119">Uso de la característica con canalizaciones de pruebas de unidades</span><span class="sxs-lookup"><span data-stu-id="8a6b1-119">Using the Unit Testing Feature with Pipelines</span></span>](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a><span data-ttu-id="8a6b1-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8a6b1-120">Related Sections</span></span>  
 [<span data-ttu-id="8a6b1-121">Trabajar con pruebas unitarias (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="8a6b1-121">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)