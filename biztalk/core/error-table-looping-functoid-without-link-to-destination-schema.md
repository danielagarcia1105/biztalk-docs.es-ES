---
title: "Error - el Functoid sin vínculo a esquema de destino de bucle de tabla | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tableLoopingNoLinkToDestSchema
ms.assetid: cf162e6a-5c61-4adc-978b-af641db67ed2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329e6670288f05382acf0ea014ba9ae84c4cb645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a>Error - el Functoid sin vínculo a esquema de destino de bucle de tabla
**Código de error**  
  
 btm1077  
  
 **Explicación**  
  
 A diferencia de la mayoría de los functoids, la **bucle de tabla** tiene varias salidas. Todas menos una de estas salidas deben estar conectado como primer parámetro de entrada para separar instancias de la **Extractor de tablas** functoid. La siguiente salida debe estar conectada a un **registro** nodo (con la configuración de periodicidad apropiada) en el esquema de destino. Este error se produce cuando este último vínculo de salida de un **bucle de tabla** functoid es que faltan.  
  
 **Acción del usuario**  
  
 Arrastre el functoid **bucle de tabla** registros correspondientes **registro** nodo del esquema de destino para crear el vínculo que falta.