---
title: Error - el Functoid sin vínculo a esquema de destino de bucle de tabla | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingNoLinkToDestSchema
ms.assetid: cf162e6a-5c61-4adc-978b-af641db67ed2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329e6670288f05382acf0ea014ba9ae84c4cb645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a><span data-ttu-id="57b24-102">Error - el Functoid sin vínculo a esquema de destino de bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="57b24-102">Error - Table Looping Functoid Without Link to Destination Schema</span></span>
<span data-ttu-id="57b24-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="57b24-103">**Error Code**</span></span>  
  
 <span data-ttu-id="57b24-104">btm1077</span><span class="sxs-lookup"><span data-stu-id="57b24-104">btm1077</span></span>  
  
 <span data-ttu-id="57b24-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="57b24-105">**Explanation**</span></span>  
  
 <span data-ttu-id="57b24-106">A diferencia de la mayoría de los functoids, la **bucle de tabla** tiene varias salidas.</span><span class="sxs-lookup"><span data-stu-id="57b24-106">Unlike most functoids, the **Table Looping** functoid has multiple outputs.</span></span> <span data-ttu-id="57b24-107">Todas menos una de estas salidas deben estar conectado como primer parámetro de entrada para separar instancias de la **Extractor de tablas** functoid.</span><span class="sxs-lookup"><span data-stu-id="57b24-107">All but one of these outputs must be connected as the first input parameter to separate instances of the **Table Extractor** functoid.</span></span> <span data-ttu-id="57b24-108">La siguiente salida debe estar conectada a un **registro** nodo (con la configuración de periodicidad apropiada) en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="57b24-108">The remaining output must be connected to a **Record** node (with appropriate recurrence settings) in the destination schema.</span></span> <span data-ttu-id="57b24-109">Este error se produce cuando este último vínculo de salida de un **bucle de tabla** functoid es que faltan.</span><span class="sxs-lookup"><span data-stu-id="57b24-109">This error occurs when this latter output link from a **Table Looping** functoid is missing.</span></span>  
  
 <span data-ttu-id="57b24-110">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="57b24-110">**User Action**</span></span>  
  
 <span data-ttu-id="57b24-111">Arrastre el functoid **bucle de tabla** registros correspondientes **registro** nodo del esquema de destino para crear el vínculo que falta.</span><span class="sxs-lookup"><span data-stu-id="57b24-111">Drag the indicated **Table Looping** record to the appropriate **Record** node in the destination schema to create the missing link.</span></span>