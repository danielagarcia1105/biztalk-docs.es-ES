---
title: "Cómo modificar una agregación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], modifying
- BAM portal, aggregations
ms.assetid: dd5ce211-32d3-4e1d-8ee0-1225ec2c45fb
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6f5f157da15cb53da41d6735524ed502cd35156
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-an-aggregation"></a><span data-ttu-id="61342-102">Cómo modificar una agregación</span><span class="sxs-lookup"><span data-stu-id="61342-102">How to Modify an Aggregation</span></span>
<span data-ttu-id="61342-103">Los informes de tabla dinámica de Office Web Components se utilizan de la misma forma que los informes de tabla dinámica de Excel.</span><span class="sxs-lookup"><span data-stu-id="61342-103">You use PivotTable reports in Office Web Components the same way you use PivotTable reports in Excel.</span></span> <span data-ttu-id="61342-104">Puede agregar y eliminar filas, columnas y filtros para generar vistas de datos agregados, en las que podrá crear alertas.</span><span class="sxs-lookup"><span data-stu-id="61342-104">You can add and remove rows, columns, and filters to generate views of the aggregated data on which you can create alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61342-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="61342-105">Prerequisites</span></span>  
 <span data-ttu-id="61342-106">Para llevar a cabo este procedimiento, deberá disponer de una vista implementada que contenga una agregación.</span><span class="sxs-lookup"><span data-stu-id="61342-106">To perform this procedure, you must have a deployed view that contains an aggregation.</span></span>  
  
### <a name="to-modify-an-aggregation"></a><span data-ttu-id="61342-107">Procedimiento para modificar una agregación</span><span class="sxs-lookup"><span data-stu-id="61342-107">To modify an aggregation</span></span>  
  
1.  <span data-ttu-id="61342-108">En el **agregaciones** página, desde el **lista de campos de tabla dinámica** ventana, arrastre los campos con datos que se van a mostrar en filas y colóquelos en la columna izquierda de la cuadrícula para agregar campos de fila.</span><span class="sxs-lookup"><span data-stu-id="61342-108">On the **Aggregations** page, from the **PivotTable Field List** window, drag the fields with data that you want to display in rows and drop them onto the left column of the grid to add row fields.</span></span> <span data-ttu-id="61342-109">Si no consigue ver la lista de campos, haga clic dentro del contorno de las áreas de colocación de la tabla dinámica, y asegúrese de que aparece Mostrar lista de campos.</span><span class="sxs-lookup"><span data-stu-id="61342-109">If you don't see the field list, click within the outlines of the PivotTable drop areas, and make sure Show Field List appears.</span></span> <span data-ttu-id="61342-110">Para ver los niveles de detalle disponibles en los campos que permiten la selección de niveles, haga clic en el signo MÁS (+) situado junto al campo en cuestión.</span><span class="sxs-lookup"><span data-stu-id="61342-110">To see what levels of detail are available in fields that have levels, click the plus sign (+) next to the appropriate field.</span></span>  
  
2.  <span data-ttu-id="61342-111">Arrastre los campos con datos que se van a mostrar en columnas hasta el área de colocación denominada **Coloque aquí los campos de columna**.</span><span class="sxs-lookup"><span data-stu-id="61342-111">Drag fields with data that you want to display across columns to the drop area labeled **Drop Column Fields Here**.</span></span> <span data-ttu-id="61342-112">Solo podrá arrastrar hasta ella los campos designados como campos de cuenta o de progreso.</span><span class="sxs-lookup"><span data-stu-id="61342-112">Only fields that are designated as counts or progress fields can be dragged to this area.</span></span>  
  
3.  <span data-ttu-id="61342-113">Si agrega más de un campo de datos, distribúyalos en el orden que desee: haga clic en un campo de datos, seleccione **orden** en el menú contextual y utilizar los comandos en el **orden** menú para mover el campo.</span><span class="sxs-lookup"><span data-stu-id="61342-113">If you add more than one data field, arrange these fields in the order you want: right-click a data field, point to **Order** on the shortcut menu, and use the commands on the **Order** menu to move the field.</span></span>  
  
4.  <span data-ttu-id="61342-114">Para reorganizar los campos, arrástrelos de una área a otra.</span><span class="sxs-lookup"><span data-stu-id="61342-114">To rearrange fields, drag them from one area to another.</span></span> <span data-ttu-id="61342-115">Para eliminar un campo, arrástrelo al exterior del informe de tabla dinámica, hasta el marco de exploración.</span><span class="sxs-lookup"><span data-stu-id="61342-115">To remove a field, drag it out of the PivotTable report onto the navigation frame.</span></span>  
  
5.  <span data-ttu-id="61342-116">En la columna de totales del informe de tabla dinámica, haga clic con el botón secundario en la celda que contenga el total en el que desea crear una alerta.</span><span class="sxs-lookup"><span data-stu-id="61342-116">From the totals column in the PivotTable report, right-click the cell containing the total on which you are going to set an alert.</span></span> <span data-ttu-id="61342-117">Seleccione **crear alertas** para abrir la página de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="61342-117">Select **Create Alert** to open the Alert Management page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61342-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="61342-118">See Also</span></span>  
 <span data-ttu-id="61342-119">[Las agregaciones en el Portal de BAM página](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="61342-119">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="61342-120">Cómo establecer una alerta</span><span class="sxs-lookup"><span data-stu-id="61342-120">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)