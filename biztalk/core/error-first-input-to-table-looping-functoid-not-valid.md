---
title: 'Error: primera entrada de Functoid no válida de bucle de tabla | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9ebecbd92b43dd25e6ff3dde04d942b936f40d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968338"
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a><span data-ttu-id="8b792-102">Error: primera entrada de Functoid no válida de bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="8b792-102">Error - First Input to Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="8b792-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="8b792-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8b792-104">btm1071</span><span class="sxs-lookup"><span data-stu-id="8b792-104">btm1071</span></span>  
  
 <span data-ttu-id="8b792-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="8b792-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8b792-106">El primer parámetro de entrada a la correspondiente **bucle de tabla** functoid no es válido.</span><span class="sxs-lookup"><span data-stu-id="8b792-106">The first input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="8b792-107">Este parámetro debe ser un vínculo desde un nodo del esquema de origen, el número de apariciones del elemento correspondiente en un mensaje de instancia de entrada controlará el número de veces que el conjunto de asociados **Extractor de tablas** functoids se invocará en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8b792-107">This parameter must be a link from a node in the source schema—the number of occurrences of the corresponding element in an input instance message will control the number of times that the set of associated **Table Extractor** functoids will be invoked at run time.</span></span>  
  
 <span data-ttu-id="8b792-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="8b792-108">**User Action**</span></span>  
  
 <span data-ttu-id="8b792-109">Asegúrese de que los parámetros de entrada para el **bucle de tabla** functoid, que se obtiene acceso a través de la **parámetros de entrada** propiedad y el **configurar \<Functoid\> Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8b792-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="8b792-110">Número de parámetro de entrada de functoid de Bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="8b792-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="8b792-111">Description</span><span class="sxs-lookup"><span data-stu-id="8b792-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="8b792-112">1</span><span class="sxs-lookup"><span data-stu-id="8b792-112">1</span></span>|<span data-ttu-id="8b792-113">Vínculo de un registro o campo del esquema de origen, el número de repeticiones de los cuales un mensaje de instancia de entrada controla el número de veces que el conjunto de asociados **Extractor de tablas** functoids se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="8b792-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="8b792-114">2</span><span class="sxs-lookup"><span data-stu-id="8b792-114">2</span></span>|<span data-ttu-id="8b792-115">El número de columnas en la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la correspondiente **bucle de tabla** functoid.</span><span class="sxs-lookup"><span data-stu-id="8b792-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="8b792-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="8b792-116">3 – 100</span></span>|<span data-ttu-id="8b792-117">Constantes y vínculos (del esquema de origen o de salida de otros functoids) que se convertirán en orígenes posibles de datos con la cuadrícula de bucle de tabla.</span><span class="sxs-lookup"><span data-stu-id="8b792-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|