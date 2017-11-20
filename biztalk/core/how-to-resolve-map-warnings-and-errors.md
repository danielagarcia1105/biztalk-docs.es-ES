---
title: "Cómo resolver errores y advertencias de asignaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a3e7f3-c96c-4d3d-9f7c-d2bfd9ace4fd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2983a53bb47aa66d1564772d0f8e033132e5a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-map-warnings-and-errors"></a><span data-ttu-id="8f782-102">Cómo resolver errores y advertencias de asignaciones</span><span class="sxs-lookup"><span data-stu-id="8f782-102">How to Resolve Map Warnings and Errors</span></span>
<span data-ttu-id="8f782-103">Cuando compila una asignación, se pueden producir errores y advertencias como resultado del proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="8f782-103">When you compile a map, you may find that warnings and errors result from the compilation process.</span></span>  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a><span data-ttu-id="8f782-104">Resolver errores y advertencias al generar un mapa</span><span class="sxs-lookup"><span data-stu-id="8f782-104">Resolve warnings and errors when building a map</span></span>  
  
1.  <span data-ttu-id="8f782-105">Si hay errores de vínculos y functoids, en la **lista de errores** ventana, haga doble clic en cualquier descripción.</span><span class="sxs-lookup"><span data-stu-id="8f782-105">For link and functoid errors, in the **Error List** window, double-click any description.</span></span>  
  
     <span data-ttu-id="8f782-106">Se resalta el vínculo, functoid o nodo de esquema asociado con el error.</span><span class="sxs-lookup"><span data-stu-id="8f782-106">The link, functoid, or the schema node associated with the error is highlighted.</span></span> <span data-ttu-id="8f782-107">Resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="8f782-107">Resolve the issue.</span></span>  
  
2.  <span data-ttu-id="8f782-108">Revise el **descripción** área en el **lista de errores** ventana para determinar si hay errores adicionales.</span><span class="sxs-lookup"><span data-stu-id="8f782-108">Review the **Description** area in the **Error List** window to determine additional errors.</span></span>  
  
3.  <span data-ttu-id="8f782-109">Haga clic en el **salida** pestaña de ventana para ver información adicional de mensaje de advertencia y error.</span><span class="sxs-lookup"><span data-stu-id="8f782-109">Click the **Output** window tab to view additional warning and error message information.</span></span>  
  
4.  <span data-ttu-id="8f782-110">Después de haber resuelto todos los problemas, haga clic en el nombre de archivo de asignación en el Explorador de soluciones y, a continuación, haga clic en **comprobar asignación** o **generar solución**, pueda tener.</span><span class="sxs-lookup"><span data-stu-id="8f782-110">After you have resolved all issues, right-click the map file name in Solution Explorer, and then click **Test Map** or **Build Solution**, as the case may be.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8f782-111">Si aparece una advertencia, el problema puede existir en varias páginas de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8f782-111">If a warning appears, the problem might exist over several grid pages.</span></span> <span data-ttu-id="8f782-112">Por ejemplo, tiene la página de cuadrícula 1 con un registro (denominado **elemento**) en el árbol de esquema de origen vinculado a un registro (denominado **número**) en el árbol de esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8f782-112">For example, you have grid page 1 with a record (named **Item**) in the source schema tree linked to a record (named **Number**) in the destination schema tree.</span></span> <span data-ttu-id="8f782-113">En la página de cuadrícula 2 tiene un registro (denominado **producto**) en el árbol de esquema de origen vinculado a la misma **número** registros en el árbol de esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8f782-113">On grid page 2 you have a record (named **Product**) in the source schema tree linked to the same **Number** record in the destination schema tree.</span></span> <span data-ttu-id="8f782-114">En este escenario, se genera un mensaje de advertencia que indica que tiene varias entradas para el mismo registro.</span><span class="sxs-lookup"><span data-stu-id="8f782-114">In this scenario, a warning message is generated stating that you have multiple inputs to the same record.</span></span> <span data-ttu-id="8f782-115">Sin embargo si se muestra una página de cuadrícula 1, verá solo una entrada en el **número** registro.</span><span class="sxs-lookup"><span data-stu-id="8f782-115">However if you view grid page 1, you see only one input into the **Number** record.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8f782-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f782-116">See Also</span></span>  
 <span data-ttu-id="8f782-117">[Compilar y probar las asignaciones](../core/compiling-and-testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="8f782-117">[Compiling and Testing Maps](../core/compiling-and-testing-maps.md) </span></span>  
 <span data-ttu-id="8f782-118">[Errores del asignador de BizTalk](../core/biztalk-mapper-errors.md) </span><span class="sxs-lookup"><span data-stu-id="8f782-118">[BizTalk Mapper Errors](../core/biztalk-mapper-errors.md) </span></span>  
 [<span data-ttu-id="8f782-119">Solucionar problemas de asignaciones</span><span class="sxs-lookup"><span data-stu-id="8f782-119">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)