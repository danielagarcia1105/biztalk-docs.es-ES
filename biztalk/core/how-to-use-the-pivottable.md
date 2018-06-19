---
title: Cómo utilizar la tabla dinámica | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM views, pivot tables
- BAM views, previewing data
ms.assetid: af34494b-f577-4d36-9a9e-5d6e9c5fafbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aed416f7a04392804c4c031a69940c4229eabe99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256660"
---
# <a name="how-to-use-the-pivottable"></a><span data-ttu-id="3362e-102">Uso de la tabla dinámica</span><span class="sxs-lookup"><span data-stu-id="3362e-102">How to Use the PivotTable</span></span>
<span data-ttu-id="3362e-103">Si ha definido una vista de BAM que incluye dimensiones y medidas, debe actualizar una o más tablas dinámicas asociadas.</span><span class="sxs-lookup"><span data-stu-id="3362e-103">When you have defined a BAM view that includes dimensions and measures, you need to update one or more PivotTables associated with that view.</span></span>  
  
 <span data-ttu-id="3362e-104">Un informe de tabla dinámica en Excel es una tabla interactiva que permite combinar y comparar grandes cantidades de datos fácilmente.</span><span class="sxs-lookup"><span data-stu-id="3362e-104">A PivotTable report in Excel is an interactive table that enables you to easily combine and compare large amounts of data.</span></span> <span data-ttu-id="3362e-105">Puede rotar los valores de sus filas y columnas para ver distintos resúmenes de los datos mostrados.</span><span class="sxs-lookup"><span data-stu-id="3362e-105">The values in its rows and columns can be rotated to look at different summaries of the displayed data.</span></span> <span data-ttu-id="3362e-106">Una tabla dinámica también permite realizar cálculos sobre los datos, como promedios o recuentos de agregados.</span><span class="sxs-lookup"><span data-stu-id="3362e-106">A PivotTable also enables you perform calculations on the data, such as aggregate counts or averages.</span></span>  
  
 <span data-ttu-id="3362e-107">Para usar la tabla dinámica una vez que la ha creado, siga los pasos de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3362e-107">To use the PivotTable after you have created it, follow the steps in this procedure.</span></span> <span data-ttu-id="3362e-108">Para obtener más información sobre cómo usar tablas dinámicas, consulte la documentación de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="3362e-108">For more information about using PivotTables, see the Microsoft Excel documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3362e-109">Cuando se crea una tabla dinámica de agregación en tiempo real, ésta puede contener un máximo de 14 niveles de dimensión.</span><span class="sxs-lookup"><span data-stu-id="3362e-109">When you create a real-time aggregation pivot table, it can contain a maximum of 14 dimension levels.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3362e-110">Si define varias tablas dinámicas en la hoja de cálculo de Excel, es posible que las tablas resultantes crezcan y se superpongan cuando la actividad obtenga un conjunto de datos de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="3362e-110">If you define multiple PivotTables on the Excel Worksheet, it is possible the resulting tables can grow and overlap each other if the Activity returns a large dataset.</span></span> <span data-ttu-id="3362e-111">En este caso, recibirá el mensaje "Un informe de tabla dinámica no puede superponerse a otro informe de PowerPivot" al actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="3362e-111">In this scenario, you will receive "A PivotTable report cannot overlap another PivotTable report" when you refresh the data.</span></span> <span data-ttu-id="3362e-112">Puede corregir este error agregando más columnas o filas entre las tablas dinámicas con el fin de permitir que las tablas aumenten su tamaño sin superponerse.</span><span class="sxs-lookup"><span data-stu-id="3362e-112">You can correct this error by adding addition columns or rows between the pivot tables to allow the tables to grow with out overlapping.</span></span>  
  
### <a name="to-use-the-pivottable"></a><span data-ttu-id="3362e-113">Procedimiento para usar la tabla dinámica</span><span class="sxs-lookup"><span data-stu-id="3362e-113">To use the PivotTable</span></span>  
  
1.  <span data-ttu-id="3362e-114">Cree una vista de BAM para usarla con una tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="3362e-114">Create a BAM view to be used with a PivotTable.</span></span> <span data-ttu-id="3362e-115">Para obtener más información acerca de cómo crear una vista de SAE, vea [definir una vista de actividad de negocio](../core/defining-a-bam-view.md)</span><span class="sxs-lookup"><span data-stu-id="3362e-115">For more information about creating a BAM view, see [Defining a Business Activity View](../core/defining-a-bam-view.md)</span></span>  
  
2.  <span data-ttu-id="3362e-116">Mediante el **lista de campos de tabla dinámica**, arrastrar y colocar dimensiones disponibles uno o más en las áreas de fila y columna de la plantilla de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="3362e-116">Using the **PivotTable Field List**, drag-and-drop one or more available dimensions into the column and row areas of the PivotTable template.</span></span>  
  
3.  <span data-ttu-id="3362e-117">Mediante el **lista de campos de tabla dinámica**, arrastrar y colocar uno o más medidas disponibles en el área de elementos de datos de la plantilla de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="3362e-117">Using the  **PivotTable Field List**, drag-and-drop one or more available measures into the data items area of the PivotTable template.</span></span>  
  
     <span data-ttu-id="3362e-118">A medida que actualice la tabla, observará que se rellena con datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3362e-118">As you are updating the PivotTable, you will notice that it is populated with sample data.</span></span> <span data-ttu-id="3362e-119">Esto le ayudará a decidir cómo configurarla.</span><span class="sxs-lookup"><span data-stu-id="3362e-119">This helps you determine how the PivotTable should be configured.</span></span>  
  
4.  <span data-ttu-id="3362e-120">Mediante el **tabla dinámica** barra de herramientas, asociar un gráfico a la tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="3362e-120">Using the **PivotTable** toolbar, associate a chart with the PivotTable.</span></span>  
  
5.  <span data-ttu-id="3362e-121">Guarde el libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="3362e-121">Save your Excel workbook.</span></span>