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
ms.openlocfilehash: faa6dd215aee23f49442e614649fa33f7321d42e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unit-testing"></a><span data-ttu-id="7b611-102">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="7b611-102">Unit Testing</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="7b611-103">presenta un característica que se puede habilitar en de pruebas unitarias la **implementación** página de propiedades de un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7b611-103"> introduces a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="7b611-104">Captura de pantalla siguiente muestra el acceso desde el Diseñador de proyectos cuando haga clic en un proyecto y haga clic en la configuración de este proyecto **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7b611-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click **Properties**.</span></span>  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 <span data-ttu-id="7b611-105">**Captura de pantalla de la pestaña implementación en el Diseñador de proyectos que expone la propiedad de proyecto habilitar pruebas de unidades**</span><span class="sxs-lookup"><span data-stu-id="7b611-105">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property**</span></span>  
  
 <span data-ttu-id="7b611-106">Esta característica permite crear pruebas de unidades para los esquemas, asignaciones y canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="7b611-106">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="7b611-107">Los temas de la [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] documentación proporciona algunos métodos de ejemplo para usar la característica de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="7b611-107">The topics in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] documentation provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="7b611-108">Si se habilita esta característica y se vuelve a generar el proyecto, las clases de artefacto se derivan de las siguientes clases base para admitir las pruebas de unidades.</span><span class="sxs-lookup"><span data-stu-id="7b611-108">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="7b611-109">Tipo de artefacto</span><span class="sxs-lookup"><span data-stu-id="7b611-109">Artifact type</span></span>|<span data-ttu-id="7b611-110">Clase base</span><span class="sxs-lookup"><span data-stu-id="7b611-110">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="7b611-111">esquema</span><span class="sxs-lookup"><span data-stu-id="7b611-111">Schema</span></span>|<span data-ttu-id="7b611-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="7b611-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="7b611-113">Mapa</span><span class="sxs-lookup"><span data-stu-id="7b611-113">Map</span></span>|<span data-ttu-id="7b611-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="7b611-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="7b611-115">Canalización</span><span class="sxs-lookup"><span data-stu-id="7b611-115">Pipeline</span></span>|<span data-ttu-id="7b611-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="7b611-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
 <span data-ttu-id="7b611-117">Para obtener más información acerca de la unidad de la característica de pruebas introducidos con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], vea los temas siguientes en la [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda:</span><span class="sxs-lookup"><span data-stu-id="7b611-117">For more information about the unit testing feature introduced with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], see the following topics in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help:</span></span>  
  
-   <span data-ttu-id="7b611-118">[Uso de la característica con esquemas y asignaciones de pruebas de unidades](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span><span class="sxs-lookup"><span data-stu-id="7b611-118">[Using the Unit Testing Feature with Schemas and Maps](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span></span>  
  
-   <span data-ttu-id="7b611-119">[Uso de la característica con canalizaciones de pruebas de unidades](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span><span class="sxs-lookup"><span data-stu-id="7b611-119">[Using the Unit Testing Feature with Pipelines](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b611-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b611-120">See Also</span></span>  
 [<span data-ttu-id="7b611-121">Implementación de las pruebas automatizadas</span><span class="sxs-lookup"><span data-stu-id="7b611-121">Implementing Automated Testing</span></span>](../technical-guides/implementing-automated-testing.md)