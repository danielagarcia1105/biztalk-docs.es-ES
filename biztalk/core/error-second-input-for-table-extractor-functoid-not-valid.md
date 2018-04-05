---
title: 'Error: segunda entrada de Functoid de tabla extractor de tablas no válida | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e674ad6777ebff53fefe053e1b6af46ebc54ef3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a><span data-ttu-id="b7344-102">Error: segunda entrada de Functoid de tabla extractor de tablas no válida</span><span class="sxs-lookup"><span data-stu-id="b7344-102">Error - Second Input for Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="b7344-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="b7344-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b7344-104">btm1073</span><span class="sxs-lookup"><span data-stu-id="b7344-104">btm1073</span></span>  
  
 <span data-ttu-id="b7344-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="b7344-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b7344-106">El segundo parámetro a la correspondiente de entrada **Extractor de tablas** functoid no es válido.</span><span class="sxs-lookup"><span data-stu-id="b7344-106">The second input parameter to the relevant **Table Extractor** functoid is not valid.</span></span> <span data-ttu-id="b7344-107">Este parámetro debe ser una constante de número entero positivo que indica una columna válida de la tabla configurada para cuadrícula de bucle la **bucle de tabla** functoid indicado por el primer parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="b7344-107">This parameter must be a positive integer constant that indicates a valid column in the table looping grid configured for the **Table Looping** functoid that is indicated by the first input parameter.</span></span>  
  
 <span data-ttu-id="b7344-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="b7344-108">**User Action**</span></span>  
  
 <span data-ttu-id="b7344-109">Asegúrese de que los parámetros de entrada a la correspondiente **Extractor de tablas** functoid, que se obtiene acceso a través de su **parámetros de entrada** propiedad y el **configurar \<Functoid\> Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b7344-109">Ensure that the input parameters to the relevant **Table Extractor** functoid, as accessed through its **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="b7344-110">Número de parámetro de entrada del functoid de Extractor de tablas</span><span class="sxs-lookup"><span data-stu-id="b7344-110">Table Extractor functoid input parameter number</span></span>|<span data-ttu-id="b7344-111">Description</span><span class="sxs-lookup"><span data-stu-id="b7344-111">Description</span></span>|  
|-----------------------------------------------------|-----------------|  
|<span data-ttu-id="b7344-112">1</span><span class="sxs-lookup"><span data-stu-id="b7344-112">1</span></span>|<span data-ttu-id="b7344-113">Vincular desde el **bucle de tabla** functoid a partir del cual **Extractor de tablas** functoid extraerá los datos de la columna tal y como indica su segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="b7344-113">Link from the **Table Looping** functoid from which this **Table Extractor** functoid will pull column data as indicated by its second parameter.</span></span>|  
|<span data-ttu-id="b7344-114">2</span><span class="sxs-lookup"><span data-stu-id="b7344-114">2</span></span>|<span data-ttu-id="b7344-115">El número de una columna válida de la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la **bucle de tabla** especificado por el primer parámetro de entrada de functoid.</span><span class="sxs-lookup"><span data-stu-id="b7344-115">The number of a valid column in the data table configured through the **Table Looping Grid** property of the **Table Looping** functoid specified by the first input parameter.</span></span>|