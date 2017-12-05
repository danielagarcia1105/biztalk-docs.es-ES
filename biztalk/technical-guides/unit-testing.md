---
title: Pruebas unitarias | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c40e5b82-dbb2-4767-8286-88e2de4129f3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f792adf73fb1e3791f0dfe6c8c5f60a3bb81e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="unit-testing"></a><span data-ttu-id="6e41d-102">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="6e41d-102">Unit Testing</span></span>
<span data-ttu-id="6e41d-103">BizTalk Server introduce un característica que se puede habilitar en de pruebas unitarias la **implementación** página de propiedades de un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="6e41d-103">BizTalk Server introduces a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="6e41d-104">Captura de pantalla siguiente muestra el acceso desde el Diseñador de proyectos cuando haga clic en un proyecto y haga clic en la configuración de este proyecto **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6e41d-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click **Properties**.</span></span>  
  
 <span data-ttu-id="6e41d-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span><span class="sxs-lookup"><span data-stu-id="6e41d-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span></span>  
  
 <span data-ttu-id="6e41d-106">**Captura de pantalla de la pestaña implementación en el Diseñador de proyectos que expone la propiedad de proyecto habilitar pruebas de unidades**</span><span class="sxs-lookup"><span data-stu-id="6e41d-106">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property**</span></span>  
  
 <span data-ttu-id="6e41d-107">Esta característica permite crear pruebas de unidades para los esquemas, asignaciones y canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="6e41d-107">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="6e41d-108">Los temas de la documentación de BizTalk Server proporciona algunos métodos de ejemplo para usar la característica de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="6e41d-108">The topics in the BizTalk Server documentation provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="6e41d-109">Si se habilita esta característica y se vuelve a generar el proyecto, las clases de artefacto se derivan de las siguientes clases base para admitir las pruebas de unidades.</span><span class="sxs-lookup"><span data-stu-id="6e41d-109">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="6e41d-110">Tipo de artefacto</span><span class="sxs-lookup"><span data-stu-id="6e41d-110">Artifact type</span></span>|<span data-ttu-id="6e41d-111">Clase base</span><span class="sxs-lookup"><span data-stu-id="6e41d-111">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="6e41d-112">esquema</span><span class="sxs-lookup"><span data-stu-id="6e41d-112">Schema</span></span>|<span data-ttu-id="6e41d-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="6e41d-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="6e41d-114">Mapa</span><span class="sxs-lookup"><span data-stu-id="6e41d-114">Map</span></span>|<span data-ttu-id="6e41d-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="6e41d-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="6e41d-116">Canalización</span><span class="sxs-lookup"><span data-stu-id="6e41d-116">Pipeline</span></span>|<span data-ttu-id="6e41d-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="6e41d-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
 <span data-ttu-id="6e41d-118">Para obtener más información acerca de la característica que se introdujo con BizTalk Server de pruebas unitarias, vea los temas siguientes en la Ayuda de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="6e41d-118">For more information about the unit testing feature introduced with BizTalk Server, see the following topics in the BizTalk Server Help:</span></span>  
  
-   <span data-ttu-id="6e41d-119">[Uso de la característica con esquemas y asignaciones de pruebas de unidades](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span><span class="sxs-lookup"><span data-stu-id="6e41d-119">[Using the Unit Testing Feature with Schemas and Maps](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span></span>  
  
-   <span data-ttu-id="6e41d-120">[Uso de la característica con canalizaciones de pruebas de unidades](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span><span class="sxs-lookup"><span data-stu-id="6e41d-120">[Using the Unit Testing Feature with Pipelines](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e41d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e41d-121">See Also</span></span>  
 [<span data-ttu-id="6e41d-122">Implementación de pruebas automatizadas</span><span class="sxs-lookup"><span data-stu-id="6e41d-122">Implementing Automated Testing</span></span>](../technical-guides/implementing-automated-testing.md)