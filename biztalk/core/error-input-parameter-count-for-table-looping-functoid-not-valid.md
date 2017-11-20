---
title: "Error: número de parámetros de entrada no es válido el Functoid de bucle de tabla | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.badParamCountForTableLooping
ms.assetid: 616e54aa-f6e3-4a49-afe2-278a0724e226
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 137ee97363adce49bfce6e74c3e154832e70471e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a><span data-ttu-id="42a49-102">Error: número de parámetros de entrada no es válido el Functoid de bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="42a49-102">Error - Input Parameter Count for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="42a49-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="42a49-103">**Error Code**</span></span>  
  
 <span data-ttu-id="42a49-104">btm1070</span><span class="sxs-lookup"><span data-stu-id="42a49-104">btm1070</span></span>  
  
 <span data-ttu-id="42a49-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="42a49-105">**Explanation**</span></span>  
  
 <span data-ttu-id="42a49-106">El número de parámetros de entrada especificados para la correspondiente **bucle de tabla** functoid no es válido.</span><span class="sxs-lookup"><span data-stu-id="42a49-106">The number of input parameters specified for the relevant **Table Looping** functoid is not valid.</span></span>  
  
 <span data-ttu-id="42a49-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="42a49-107">**User Action**</span></span>  
  
 <span data-ttu-id="42a49-108">Asegúrese de que los parámetros de entrada para el **bucle de tabla** functoid, que se obtiene acceso a través de la **parámetros de entrada** propiedad y el **configurar \<Functoid > Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="42a49-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="42a49-109">Número de parámetro de entrada de functoid de Bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="42a49-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="42a49-110">Description</span><span class="sxs-lookup"><span data-stu-id="42a49-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="42a49-111">1</span><span class="sxs-lookup"><span data-stu-id="42a49-111">1</span></span>|<span data-ttu-id="42a49-112">Vínculo de un registro o campo del esquema de origen, el número de repeticiones de los cuales un mensaje de instancia de entrada controla el número de veces que el conjunto de asociados **Extractor de tablas** functoids se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="42a49-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="42a49-113">2</span><span class="sxs-lookup"><span data-stu-id="42a49-113">2</span></span>|<span data-ttu-id="42a49-114">El número de columnas en la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la correspondiente **bucle de tabla** functoid.</span><span class="sxs-lookup"><span data-stu-id="42a49-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="42a49-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="42a49-115">3 – 100</span></span>|<span data-ttu-id="42a49-116">Constantes y vínculos (del esquema de origen o de salida de otros functoids) que se convertirán en orígenes posibles de datos con la cuadrícula de bucle de tabla.</span><span class="sxs-lookup"><span data-stu-id="42a49-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|