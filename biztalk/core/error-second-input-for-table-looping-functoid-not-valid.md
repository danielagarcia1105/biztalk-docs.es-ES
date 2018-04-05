---
title: 'Error: segunda entrada de tabla no es válido el Functoid de bucle | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableLoopingNotValid
ms.assetid: 22771f36-5969-40b1-a957-3ca67e19c3fd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abb321a26300a514357225713db1b197fb828851
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a><span data-ttu-id="363ad-102">Error: segunda entrada de tabla no es válido el Functoid de bucle</span><span class="sxs-lookup"><span data-stu-id="363ad-102">Error - Second Input for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="363ad-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="363ad-103">**Error Code**</span></span>  
  
 <span data-ttu-id="363ad-104">btm1072</span><span class="sxs-lookup"><span data-stu-id="363ad-104">btm1072</span></span>  
  
 <span data-ttu-id="363ad-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="363ad-105">**Explanation**</span></span>  
  
 <span data-ttu-id="363ad-106">El segundo parámetro a la correspondiente de entrada **bucle de tabla** functoid no es válido.</span><span class="sxs-lookup"><span data-stu-id="363ad-106">The second input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="363ad-107">Este parámetro debe ser un número entero positivo que indique el número de columnas de la cuadrícula de bucle de tabla asociada.</span><span class="sxs-lookup"><span data-stu-id="363ad-107">This parameter must be a positive integer that indicates the number of columns in the associated table looping grid.</span></span>  
  
 <span data-ttu-id="363ad-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="363ad-108">**User Action**</span></span>  
  
 <span data-ttu-id="363ad-109">Asegúrese de que los parámetros de entrada para el **bucle de tabla** functoid, que se obtiene acceso a través de la **parámetros de entrada** propiedad y el **configurar \<Functoid\> Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="363ad-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="363ad-110">Número de parámetro de entrada de functoid de Bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="363ad-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="363ad-111">Description</span><span class="sxs-lookup"><span data-stu-id="363ad-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="363ad-112">1</span><span class="sxs-lookup"><span data-stu-id="363ad-112">1</span></span>|<span data-ttu-id="363ad-113">Vínculo de un registro o campo del esquema de origen, el número de repeticiones de los cuales un mensaje de instancia de entrada controla el número de veces que el conjunto de asociados **Extractor de tablas** functoids se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="363ad-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="363ad-114">2</span><span class="sxs-lookup"><span data-stu-id="363ad-114">2</span></span>|<span data-ttu-id="363ad-115">El número de columnas en la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la correspondiente **bucle de tabla** functoid.</span><span class="sxs-lookup"><span data-stu-id="363ad-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="363ad-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="363ad-116">3 – 100</span></span>|<span data-ttu-id="363ad-117">Constantes y vínculos (del esquema de origen o de salida de otros functoids) que se convertirán en orígenes posibles de datos con la cuadrícula de bucle de tabla.</span><span class="sxs-lookup"><span data-stu-id="363ad-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|