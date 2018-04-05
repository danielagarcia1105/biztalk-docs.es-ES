---
title: 'Error: datos no válidos de bucle de tabla | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingDataNotValid
ms.assetid: 19c38e79-bab0-4899-ae24-e1485327e891
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9478026980ecaf3e2049773737250c56d18262c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---table-looping-data-not-valid"></a><span data-ttu-id="73059-102">Error: datos no válidos de bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="73059-102">Error - Table Looping Data Not Valid</span></span>
<span data-ttu-id="73059-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="73059-103">**Error Code**</span></span>  
  
 <span data-ttu-id="73059-104">btm1065</span><span class="sxs-lookup"><span data-stu-id="73059-104">btm1065</span></span>  
  
 <span data-ttu-id="73059-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="73059-105">**Explanation**</span></span>  
  
 <span data-ttu-id="73059-106">La tabla de datos asociados con la correspondiente **bucle de tabla** functoid no es válido, probablemente porque no está configurado correctamente segundo parámetro de entrada del functoid o a una cuadrícula de bucle de tabla no está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="73059-106">The table of data associated with the relevant **Table Looping** functoid is not valid, probably due to an incorrectly configured second input parameter to the functoid, or an incorrectly configured table looping grid.</span></span>  
  
 <span data-ttu-id="73059-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="73059-107">**User Action**</span></span>  
  
 <span data-ttu-id="73059-108">Asegúrese de que los parámetros de entrada para el **bucle de tabla** functoid, que se obtiene acceso a través de la **parámetros de entrada** propiedad y el **configurar \<Functoid\> Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="73059-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="73059-109">Número de parámetro de entrada de functoid de Bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="73059-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="73059-110">Description</span><span class="sxs-lookup"><span data-stu-id="73059-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="73059-111">1</span><span class="sxs-lookup"><span data-stu-id="73059-111">1</span></span>|<span data-ttu-id="73059-112">Vínculo de un registro o campo del esquema de origen, el número de repeticiones de los cuales un mensaje de instancia de entrada controla el número de veces que el conjunto de asociados **Extractor de tablas** functoids se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="73059-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="73059-113">2</span><span class="sxs-lookup"><span data-stu-id="73059-113">2</span></span>|<span data-ttu-id="73059-114">El número de columnas en la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la correspondiente **bucle de tabla** functoid.</span><span class="sxs-lookup"><span data-stu-id="73059-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="73059-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="73059-115">3 – 100</span></span>|<span data-ttu-id="73059-116">Constantes y vínculos (del esquema de origen o de salida de otros functoids) que se convertirán en orígenes posibles de datos con la cuadrícula de bucle de tabla.</span><span class="sxs-lookup"><span data-stu-id="73059-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|  
  
 <span data-ttu-id="73059-117">Además, asegúrese de configurar correctamente la cuadrícula de bucle de tabla que se obtiene acceso a través de la **cuadrícula de bucle de tabla** propiedad y el **configuración de bucle de tabla** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="73059-117">Also, ensure that you properly configure the table looping grid, as accessed through the **Table Looping Grid** property and the **Table Looping Configuration** dialog box.</span></span> <span data-ttu-id="73059-118">Se debe elegir un valor constante o un vínculo para cada celda que vayan a tener acceso por un asociado **Extractor de tablas** functoid.</span><span class="sxs-lookup"><span data-stu-id="73059-118">A constant or link value must be chosen for every cell that will be accessed by an associated **Table Extractor** functoid.</span></span>