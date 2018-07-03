---
title: Definir dimensiones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- BAM, dimensions
- BAM views, dimensions
- Excel add-in [BAM], creating dimensions
- dimensions [BAM]
ms.assetid: c00e0c45-eef2-42d9-832c-4be08d79203f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be3c55298b58d2d5ca51652ed9911c901235863e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013661"
---
# <a name="defining-dimensions"></a><span data-ttu-id="f329e-102">Definir dimensiones</span><span class="sxs-lookup"><span data-stu-id="f329e-102">Defining Dimensions</span></span>
<span data-ttu-id="f329e-103">Microsoft Excel define las dimensiones como categorías que se emplean para organizar los datos de una tabla en niveles que se usarán para realizar análisis.</span><span class="sxs-lookup"><span data-stu-id="f329e-103">Microsoft Excel defines dimensions as categories used to organize data in a table into levels that will be used for analysis.</span></span> <span data-ttu-id="f329e-104">Por ejemplo, una dimensión de datos de ubicación podría contener niveles como ciudad, estado o provincia y región o país.</span><span class="sxs-lookup"><span data-stu-id="f329e-104">For example, a location data dimension might contain levels such as city, state/province, and country/region.</span></span> <span data-ttu-id="f329e-105">Al crear vistas de BAM en el Asistente para vistas de BAM, puede agregar uno o más de los siguientes tipos de dimensión:</span><span class="sxs-lookup"><span data-stu-id="f329e-105">When creating BAM Views in the BAM View wizard, you can add one or more of the following dimension types:</span></span>  
  
- [<span data-ttu-id="f329e-106">Dimensión de progreso</span><span class="sxs-lookup"><span data-stu-id="f329e-106">Progress Dimension</span></span>](../core/progress-dimension.md)  
  
- [<span data-ttu-id="f329e-107">Dimensión de datos</span><span class="sxs-lookup"><span data-stu-id="f329e-107">Data Dimension</span></span>](../core/data-dimension.md)  
  
- [<span data-ttu-id="f329e-108">Dimensión de tiempo</span><span class="sxs-lookup"><span data-stu-id="f329e-108">Time Dimension</span></span>](../core/time-dimension.md)  
  
- [<span data-ttu-id="f329e-109">Dimensión de rango numérico</span><span class="sxs-lookup"><span data-stu-id="f329e-109">Numeric Range Dimension</span></span>](../core/numeric-range-dimension.md)  
  
  <span data-ttu-id="f329e-110">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span><span class="sxs-lookup"><span data-stu-id="f329e-110">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span></span>  
  <span data-ttu-id="f329e-111">Datos de agregación precalculados</span><span class="sxs-lookup"><span data-stu-id="f329e-111">Pre-calculated Aggregation Data</span></span>  
  
  <span data-ttu-id="f329e-112">Puede agregar nuevas dimensiones en el Asistente para vistas de BAM.</span><span class="sxs-lookup"><span data-stu-id="f329e-112">You add new dimensions in the BAM View wizard.</span></span> <span data-ttu-id="f329e-113">Antes de agregar dimensiones, debe usar el asistente para crear vistas de actividades económicas.</span><span class="sxs-lookup"><span data-stu-id="f329e-113">Before you can add dimensions, you need to use the wizard to create business activity views.</span></span> <span data-ttu-id="f329e-114">Para obtener más información sobre cómo usar el asistente, consulte [definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="f329e-114">For more information about using the wizard, see [Define Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
### <a name="to-add-new-dimensions"></a><span data-ttu-id="f329e-115">Para agregar nuevas dimensiones</span><span class="sxs-lookup"><span data-stu-id="f329e-115">To add new dimensions</span></span>  
  
1.  <span data-ttu-id="f329e-116">En el Asistente para la vista de BAM, haga clic en **siguiente** hasta que vea el **nueva vista de BAM: agregación de dimensiones y medidas** página.</span><span class="sxs-lookup"><span data-stu-id="f329e-116">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="f329e-117">Haga clic en **nuevas dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="f329e-117">Click **New Dimensions**.</span></span>  
  
2.  <span data-ttu-id="f329e-118">Escriba el nombre de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="f329e-118">Type a name for the dimension.</span></span>  
  
3.  <span data-ttu-id="f329e-119">En la lista desplegable, seleccione un tipo de dimensión.</span><span class="sxs-lookup"><span data-stu-id="f329e-119">From the drop-down list, select a dimension type.</span></span>  
  
4.  <span data-ttu-id="f329e-120">Según el tipo de dimensión seleccionado, rellene los datos apropiados y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f329e-120">Based on the dimension type you selected, fill in the appropriate data, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f329e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f329e-121">See Also</span></span>  
 [<span data-ttu-id="f329e-122">Dimensión de progreso</span><span class="sxs-lookup"><span data-stu-id="f329e-122">Progress Dimension</span></span>](../core/progress-dimension.md)