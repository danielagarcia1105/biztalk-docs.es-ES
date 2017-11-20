---
title: "Agregar avanzada Functoids a una asignación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbec5e9c-65b3-4734-a7fc-4ee66cf26eee
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fad75ed2c5c6779801e38f0c4b8f4505696bb476
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-advanced-functoids-to-a-map"></a><span data-ttu-id="d81b1-102">Agregar functoids avanzados a una asignación</span><span class="sxs-lookup"><span data-stu-id="d81b1-102">Adding Advanced Functoids to a Map</span></span>
<span data-ttu-id="d81b1-103">Functoids de la **avanzadas** categoría son más complejos para comprender y usar que los functoids en el resto de categorías, clasificados como functoids básicos.</span><span class="sxs-lookup"><span data-stu-id="d81b1-103">Functoids in the **Advanced** category are more complex to understand and use than the functoids in the other categories, together classified as basic functoids.</span></span> <span data-ttu-id="d81b1-104">Los functoids avanzados se utilizan cuando necesita asignaciones más complejas.</span><span class="sxs-lookup"><span data-stu-id="d81b1-104">You use advanced functoids when you need more complex maps.</span></span> <span data-ttu-id="d81b1-105">Estas asignaciones pueden necesitar contar registros, recorrer en bucle registros con un número variable de subregistros o ejecutar secuencias de comandos complejas arbitrariamente.</span><span class="sxs-lookup"><span data-stu-id="d81b1-105">These maps might need to count records, loop through records with a variable number of subrecords, or run an arbitrarily complex script.</span></span>  
  
 <span data-ttu-id="d81b1-106">Esta sección proporciona instrucciones paso a paso para agregar functoids de la **avanzadas** categoría a asignaciones, incluida la correcta configuración sus parámetros de entrada y salidos.</span><span class="sxs-lookup"><span data-stu-id="d81b1-106">This section provides step-by-step instructions for adding functoids in the **Advanced** category to your maps, including correctly setting their input and output parameters.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d81b1-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d81b1-107">In This Section</span></span>  
  
-   [<span data-ttu-id="d81b1-108">Cómo agregar Functoids a una asignación de bucle</span><span class="sxs-lookup"><span data-stu-id="d81b1-108">How to Add Looping Functoids to a Map</span></span>](../core/how-to-add-looping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-109">Cómo agregar la asignación de valores (sin formato) Functoids a una asignación</span><span class="sxs-lookup"><span data-stu-id="d81b1-109">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-110">Cómo agregar Functoids a una asignación de aserción</span><span class="sxs-lookup"><span data-stu-id="d81b1-110">How to Add Assert Functoids to a Map</span></span>](../core/how-to-add-assert-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-111">Cómo agregar el bucle de tabla y Functoids de Extractor de tabla a un mapa</span><span class="sxs-lookup"><span data-stu-id="d81b1-111">How to Add Table Looping and Table Extractor Functoids to a Map</span></span>](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-112">Cómo agregar Functoids de Scripting a un mapa</span><span class="sxs-lookup"><span data-stu-id="d81b1-112">How to Add Scripting Functoids to a Map</span></span>](../core/how-to-add-scripting-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-113">Cómo agregar Functoids de valor nulo a un mapa</span><span class="sxs-lookup"><span data-stu-id="d81b1-113">How to Add Nil Value Functoids to a Map</span></span>](../core/how-to-add-nil-value-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-114">Cómo agregar Functoids de asignación a una asignación de valores</span><span class="sxs-lookup"><span data-stu-id="d81b1-114">How to Add Value Mapping Functoids to a Map</span></span>](../core/how-to-add-value-mapping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-115">Cómo agregar Functoids de copia masiva a un mapa</span><span class="sxs-lookup"><span data-stu-id="d81b1-115">How to Add Mass Copy Functoids to a Map</span></span>](../core/how-to-add-mass-copy-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-116">Cómo agregar Functoids de iteración a un mapa</span><span class="sxs-lookup"><span data-stu-id="d81b1-116">How to Add Iteration Functoids to a Map</span></span>](../core/how-to-add-iteration-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-117">Cómo agregar Functoids de índice a un mapa</span><span class="sxs-lookup"><span data-stu-id="d81b1-117">How to Add Index Functoids to a Map</span></span>](../core/how-to-add-index-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="d81b1-118">Cómo agregar Functoids de número de registros a un mapa</span><span class="sxs-lookup"><span data-stu-id="d81b1-118">How to Add Record Count Functoids to a Map</span></span>](../core/how-to-add-record-count-functoids-to-a-map.md)